# Google AdSense Integration with Next.js: A Developer's Guide

This repository contains comprehensive documentation for integrating Google AdSense into Next.js applications. It is designed to help developers monetize their Next.js sites effectively while maintaining performance and user experience.

## Overview

Google AdSense is a powerful tool for website monetization, and Next.js’s high-performance framework makes it an ideal platform for maximizing ad revenue. This guide covers everything from AdSense basics to advanced integration techniques, tailored for Next.js developers.

## Documentation Structure

Detailed documentation is located in the `docs/` directory, organized into the following sections:

- [Introduction](docs/introduction.md): Understand AdSense, its value for Next.js, and core mechanics.
- [Preparation](docs/preparation.md): Eligibility, account setup, and policy compliance.
- [Integration](docs/integration.md): Methods to integrate AdSense into Next.js, including `@next/third-parties` and manual scripts.
- [Ad Units](docs/ad-units.md): Creating, configuring, and placing ad units, including Auto Ads.
- [Best Practices](docs/best-practices.md): Optimize performance, ensure compliance, and handle privacy.
- [Troubleshooting](docs/troubleshooting.md): Diagnose and fix common AdSense issues in Next.js.
- [Advanced Considerations](docs/advanced.md): APIs, Privacy Sandbox, and scaling with Google Ad Manager.
- [Conclusion](docs/conclusion.md): Key takeaways and next steps.

## Example Application

The `examples/minimal-adsense-app/` directory contains a fully functional Next.js application demonstrating AdSense integration:
- Supports both App Router and Pages Router.
- Includes `@next/third-parties` with Google Tag Manager (GTM) and manual script implementations.
- Features a reusable `AdUnit` component.
- Optimized for Core Web Vitals and client-side navigation.

To run the example:
```bash
cd examples/minimal-adsense-app
npm install
cp .env.example .env.local
# Edit .env.local with your AdSense/GTM IDs
npm run dev
```

## Getting Started

To use this documentation with Context7:
1. Add this repository to Context7 via the [Add Library](https://context7.com/add-library?tab=github) page, using the GitHub URL: `https://github.com/your-username/nextjs-adsense-docs`.
2. Configure Context7 to pull markdown files from the `docs/` directory and optionally include the `examples/` directory for code samples.
3. Explore the documentation in Context7’s interface or directly in this repository.

## Contributing

Contributions are welcome! Please review our [CONTRIBUTING.md](CONTRIBUTING.md) (to be added) for guidelines on submitting updates or new content.
