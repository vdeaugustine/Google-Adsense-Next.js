# Integrating AdSense with Next.js Applications

## Core Concepts

- **Client-Side Ads**: AdSense scripts load ads in the browser post-page load, requiring careful integration with Next.js’s rendering (SSR, SSG, ISR, CSR).
- **Rendering Impact**: Ads load after client-side hydration, potentially affecting Core Web Vitals.
- **NPM Role**: Use NPM for Next.js and helper libraries like `@next/third-parties`, not AdSense itself.

## Method 1: Using `@next/third-parties` (Recommended)

The `@next/third-parties` library optimizes Google script loading.

1. **Install**:
   ```bash
   npm install @next/third-parties@latest next@latest
   ```

2. **Use Google Tag Manager (GTM)**:
   - Set up a GTM account and add an AdSense tag with your publisher ID.
   - Add the `GoogleTagManager` component in `app/layout.tsx` (App Router):
     ```javascript
     import { GoogleTagManager } from '@next/third-parties/google';

     export default function RootLayout({ children }) {
       return (
         <html lang="en">
           <GoogleTagManager gtmId="GTM-YOUR_CONTAINER_ID" />
           <body>{children}</body>
         </html>
       );
     }
     ```

**Benefits**: Optimized script loading, centralized tag management via GTM.

## Method 2: Manual AdSense Code Implementation

1. **Main Script** (in `app/layout.tsx` or `pages/_document.js`):
   ```javascript
   import Script from 'next/script';

   export default function RootLayout({ children }) {
     return (
       <html lang="en">
         <head>
           <Script
             id="adsense-script"
             async
             src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-YOUR_PUBLISHER_ID"
             crossOrigin="anonymous"
             strategy="afterInteractive"
           />
         </head>
         <body>{children}</body>
       </html>
     );
   }
   ```

2. **Ad Unit Component** (`components/AdSenseUnit.js`):
   ```javascript
   import { useEffect } from 'react';
   import { useRouter } from 'next/router';

   export default function AdSenseUnit({ publisherId, adSlot, adFormat = "auto", fullWidthResponsive = true, style }) {
     const router = useRouter();

     useEffect(() => {
       try {
         if (typeof window !== "undefined") {
           (window.adsbygoogle = window.adsbygoogle || []).push({});
         }
       } catch (err) {
         console.error("AdSense push error:", err);
       }
     }, [router.asPath]);

     return (
       <div style={style} key={router.asPath + adSlot}>
         <ins
           className="adsbygoogle"
           style={{ display: 'block', ...style }}
           data-ad-client={publisherId}
           data-ad-slot={adSlot}
           data-ad-format={adFormat}
           data-full-width-responsive={fullWidthResponsive.toString()}
         />
       </div>
     );
   }
   ```

**Note**: Replace `ca-pub-YOUR_PUBLISHER_ID` and `adSlot` with your values.

## Method 3: Community NPM Packages (Caution)

Community packages (e.g., `react-adsense`) simplify setup but risk outdated maintenance or suboptimal performance. Vet packages for compatibility and updates before use. Prefer official methods for production.