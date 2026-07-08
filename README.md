# Founder Deal Check

A KV Consulting tool. Installable PWA that helps founders model equity, dilution,
and exit outcomes live during investor conversations.

**Live:** https://founder-deal-check.netlify.app

## Structure

```
index.html          the app (self-contained UI + logic)
manifest.json       PWA install metadata
service-worker.js   offline caching (bump the CACHE constant on each release)
icons/              app icons (192, 512, 512-maskable)
assets/             KV Consulting logo
netlify.toml        cache-control headers + publish config
```

## Deployment

Hosted on Netlify with **continuous deployment**: any push to `master` triggers
an automatic build and deploy — no manual step required.

- Publish directory: repo root, no build command (static site).
- Cache headers (`netlify.toml`): HTML / manifest / service-worker are served
  `no-cache`; icons are cached for a year. Bump the `CACHE` constant in
  `service-worker.js` when releasing new HTML so clients pick up the update.

To deploy manually if ever needed:

```bash
netlify deploy --prod --dir .
```
