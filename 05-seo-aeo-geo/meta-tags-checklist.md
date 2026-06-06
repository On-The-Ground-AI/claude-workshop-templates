# Meta tags checklist

> ⚠️ AI-generated · Reviewed by Haojun See (OTG).

Every page on your site should have these meta tags. In Next.js App Router, you set them via the `Metadata` export.

## The checklist

- [ ] `<title>` — unique per page, 50–60 chars, primary keyword near the front
- [ ] `<meta name="description">` — unique per page, 140–160 chars, action-oriented
- [ ] `<link rel="canonical">` — points to the canonical URL (set automatically by Next.js if you configure `metadataBase`)
- [ ] Open Graph: `og:title`, `og:description`, `og:url`, `og:image`, `og:type`, `og:site_name`, `og:locale`
- [ ] Twitter: `twitter:card`, `twitter:title`, `twitter:description`, `twitter:image`
- [ ] `viewport` — `width=device-width, initial-scale=1`
- [ ] Charset — UTF-8 (Next.js does this automatically)
- [ ] Theme colour — `<meta name="theme-color">` (optional but nice)

## Next.js App Router pattern

```typescript
// src/app/layout.tsx
import type { Metadata } from "next";

export const metadata: Metadata = {
  metadataBase: new URL("https://yourdomain.com"),
  title: {
    default: "Your Site — Tagline",
    template: "%s — Your Site",
  },
  description: "One sentence about what this site is. 140–160 chars.",
  openGraph: {
    title: "Your Site",
    description: "Same or shorter than meta description.",
    type: "website",
    locale: "en_SG",
    siteName: "Your Site",
    images: [{ url: "/og-default.png", width: 1200, height: 630 }],
  },
  twitter: {
    card: "summary_large_image",
    title: "Your Site",
    description: "Same or shorter than meta description.",
    images: ["/og-default.png"],
  },
};
```

## Per-page overrides

```typescript
// src/app/about/page.tsx
import type { Metadata } from "next";

export const metadata: Metadata = {
  title: "About",
  description: "Who I am, what I do, why this site exists. 140–160 chars.",
  openGraph: {
    title: "About — Your Site",
    description: "Short, specific.",
    type: "article",
  },
};
```

The `template: "%s — Your Site"` in your root layout means the about page will render as `<title>About — Your Site</title>` automatically.

## OG image

A single 1200×630 `og-default.png` in `/public` is enough for v1. Later, generate per-page OG images using Next.js's `ImageResponse` API (free, server-rendered).

## Don't bother with

- `<meta name="keywords">` — Google ignores it.
- Bing-specific tags — they cover the same ground.
- Excessive `<link rel="preconnect">` — only matters for sub-second load times you don't need yet.

## How to verify

- View source on each page; confirm tags render.
- Paste a URL into [https://opengraph.dev/](https://opengraph.dev/) or LinkedIn's [Post Inspector](https://www.linkedin.com/post-inspector/) — check the preview.
- Lighthouse → SEO category should hit 100.

---

**Generated with Claude. Reviewed by Haojun See (On The Ground).**
For tailored, hands-on guidance, see [ontheground.agency](https://www.ontheground.agency) or email [haojun@ontheground.agency](mailto:haojun@ontheground.agency).
