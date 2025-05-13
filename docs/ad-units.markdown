# Implementing and Managing Ad Units in Next.js

## AdSense Ad Formats

AdSense offers various formats for web applications:
- **Display Ads**: Graphical banners, responsive or fixed-size.
- **Native Ads**:
  - **In-feed**: Blend with content lists (e.g., articles).
  - **In-article**: Fit within article content.
- **Multiplex Ads**: Grid-based, multi-ad units.
- **Anchor/Vignette Ads** (Auto Ads): Sticky or full-screen ads.

## Creating and Configuring Ad Units

1. Log into the AdSense dashboard.
2. Navigate to “Ads” > “Ad units.”
3. Create a new ad unit (e.g., Display, In-feed).
4. Name it descriptively (e.g., `MyBlog_Article_Sidebar_300x250`).
5. Set options (e.g., responsive size, style for native ads).
6. Copy the generated code (contains `data-ad-client` and `data-ad-slot`).

## Placing Ad Units in Next.js

Use the `AdSenseUnit` component (from `integration.md`) for ad placement. For responsive ads, set `data-ad-format="auto"` and `data-full-width-responsive="true"`.

### Example: Blog Post Ad
```javascript
import AdSenseUnit from '../components/AdSenseUnit';

export default function BlogPost() {
  return (
    <article>
      <h1>Blog Title</h1>
      <p>Content...</p>
      <AdSenseUnit
        publisherId="ca-pub-YOUR_PUBLISHER_ID"
        adSlot="YOUR_AD_SLOT"
        style={{ margin: '20px 0' }}
      />
      <p>More content...</p>
    </article>
  );
}
```

### Strategic Placement
- **Locations**: Above the fold, within content, sidebars, footers.
- **Policy**: Avoid excessive ads or designs encouraging accidental clicks.
- **UX**: Ensure ads don’t disrupt content or load times.

## Implementing Auto Ads

Auto Ads use Google’s AI to place ads automatically.

1. In the AdSense dashboard, enable Auto Ads for your site.
2. Ensure the main AdSense script is in `<head>` (see `integration.md`).
3. Configure options (e.g., ad formats, ad load, page exclusions).

**Pros**: Easy setup, AI-optimized placements.
**Cons**: Less control, potential for poor placements without configuration.

**Hybrid Approach**: Combine manual ad units for key placements (e.g., header) with Auto Ads for additional opportunities.