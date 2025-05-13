# Preparing for AdSense: Eligibility and Account Setup

## AdSense Eligibility Requirements

To integrate AdSense into a Next.js site, ensure compliance with Google’s requirements:

- **Unique and Interesting Content**: Your site must offer high-quality, original content that engages users. Duplicate or low-value content risks rejection.
- **Site Ownership and HTML Access**: You must own the site and have access to modify its HTML for adding AdSense code. Next.js developers typically meet this requirement.
- **AdSense Program Policies**: Adhere to Google’s policies on content, traffic, and ad implementation.
- **Age Requirement**: Applicants must be 18 or older, or a guardian can manage the account.

## Navigating AdSense Program Policies

Compliance with AdSense Program Policies and Google Publisher Policies is critical. Prohibited content (e.g., adult material, copyrighted content) or invalid traffic (e.g., artificial clicks) can lead to account suspension. Review the AdSense Help Center’s “Beginner’s guide” and policy updates regularly.

## Step-by-Step Guide: Creating and Activating Your AdSense Account

1. **Create an Account**:
   - Visit the AdSense sign-up page.
   - Enter your Next.js site URL and email address.
   - Ensure the site has substantial content.

2. **Activate the Account**:
   - **Enter Payment Information**: Provide accurate payee details.
   - **Connect Your Site**: Add the AdSense JavaScript code to your Next.js site (e.g., in `pages/_document.js` for Pages Router or `app/layout.tsx` for App Router).
     ```javascript
     <Script
       src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-YOUR_PUBLISHER_ID"
       strategy="afterInteractive"
     />
     ```
   - **Wait for Review**: AdSense reviews your site and payment details (a few days to 2-4 weeks). Ads won’t display until approved.

3. **Start Showing Ads**: Once approved, configure and display ads.

**Note**: Plan for the review period to avoid monetization delays.

## What if Your Account Isn’t Approved?

If rejected, AdSense provides a reason (e.g., policy violations, insufficient content). Consult the AdSense Help Center, address issues, and reapply or appeal after ensuring compliance.