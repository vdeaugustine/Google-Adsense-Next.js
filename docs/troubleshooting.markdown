# Troubleshooting Common AdSense Issues in Next.js

## Ads Not Displaying: Diagnostic Checklist

- **Account Status**: Verify the AdSense account is approved (“Ready” status). Check for policy violations or holds.
- **Code Implementation**:
  - Ensure the main script (`adsbygoogle.js`) is in `<head>`.
  - Verify `data-ad-client` and `data-ad-slot` in ad units.
  - Check `(window.adsbygoogle || []).push({})` runs for each ad unit.
- **Ad Blockers**: Test with ad blockers disabled.
- **Console Errors**: Look for JavaScript or HTTP errors in the browser console.
- **CORS/CSP**: Ensure `*.googlesyndication.com` and `*.doubleclick.net` are allowed.
- **Ad Inventory**: Low traffic or niche content may result in no ads.
- **Logged-in Users**: Check for logic hiding ads for certain users.

## Impact of Next.js Rendering

- **SSR/SSG**: Ensure hydration completes without errors, as AdSense is client-side.
- **Client-Side Routing**: Re-initialize ads on route changes using `useEffect` with route dependencies.

## Debugging with Browser Tools

- **Network Tab**: Confirm `adsbygoogle.js` and ad server requests succeed.
- **Elements Tab**: Verify `<ins class="adsbygoogle">` tags and `<iframe>` creation.
- **Console Tab**: Check for AdSense-related errors.

## Next.js-Specific Pitfalls

- **useEffect**: Ensure correct dependencies for ad initialization.
- **Script Conflicts**: Test without other third-party scripts.
- **State Management**: Verify ad components render correctly.
- **Environment Variables**: Use `NEXT_PUBLIC_` for client-side AdSense IDs.