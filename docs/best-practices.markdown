# Best Practices for AdSense in Next.js

## Optimizing Performance and Core Web Vitals

AdSense scripts can impact Core Web Vitals (CWV), affecting SEO and revenue.

- **Lazy Loading**: Use `strategy="lazyOnload"` for non-critical ads or Intersection Observer for below-the-fold ads.
- **Minimize CLS**: Reserve space for ads with CSS (`min-height`, `min-width`).
- **LCP/INP**: Use `next/script` with `afterInteractive` to avoid blocking the main thread.

Monitor CWV with Google PageSpeed Insights or Lighthouse.

## Ensuring Policy Compliance

- **Content**: Ensure all pages, including dynamic content, comply with AdSense policies (no prohibited content).
- **Ad Placement**: Avoid misleading placements or excessive ads.
- **UGC**: Implement moderation for user-generated content to prevent violations.

## Handling Client-Side Navigation

In Next.js SPAs, ads may not refresh on route changes. Use the `AdSenseUnit` component with `useEffect` and route dependencies (e.g., `router.asPath`) to re-initialize ads.

## A/B Testing

- Use AdSense’s “Experiments” for testing ad settings.
- Implement custom A/B tests in Next.js (e.g., vary ad placements via feature flags).
- Track metrics: RPM, CTR, viewability, bounce rate, CWV.

## Managing Consent and Privacy (GDPR, CCPA)

- **Privacy Policy**: Disclose cookie and data use.
- **Consent**: Use a Consent Management Platform (CMP) to collect user consent.
- **AdSense Settings**: Adjust personalization based on consent via the AdSense dashboard’s “Privacy & messaging” tab.