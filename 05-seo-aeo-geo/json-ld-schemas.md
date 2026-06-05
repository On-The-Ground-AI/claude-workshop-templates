# JSON-LD schemas — the AEO moat

> ⚠️ AI-generated · Reviewed by Haojun Yong (OTG).

JSON-LD is how you tell Google + Bing + AI engines what your page is *about* in a structured way. This is the AEO foundation. Skip this and AI assistants can read your page but can't classify it.

## Where to put it

In Next.js App Router, add a `<script>` with `type="application/ld+json"` to the page's layout or page component. Use `dangerouslySetInnerHTML` to write the JSON string.

```typescript
const jsonLd = {
  "@context": "https://schema.org",
  "@type": "Person",
  // ...
};

export default function Page() {
  return (
    <>
      <script
        type="application/ld+json"
        dangerouslySetInnerHTML={{ __html: JSON.stringify(jsonLd) }}
      />
      {/* rest of page */}
    </>
  );
}
```

## Schemas to use (by page type)

### Homepage — Person (for personal sites)

```json
{
  "@context": "https://schema.org",
  "@type": "Person",
  "name": "Your Name",
  "url": "https://yourdomain.com",
  "image": "https://yourdomain.com/avatar.jpg",
  "jobTitle": "Product strategist",
  "worksFor": { "@type": "Organization", "name": "Your Business" },
  "sameAs": [
    "https://linkedin.com/in/yourname",
    "https://github.com/yourname",
    "https://x.com/yourname"
  ]
}
```

### Homepage — Organization (for business sites)

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Your Business",
  "url": "https://yourdomain.com",
  "logo": "https://yourdomain.com/logo.png",
  "founder": "Your Name",
  "foundingDate": "2024",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "Singapore",
    "addressCountry": "SG"
  },
  "sameAs": ["https://linkedin.com/company/yourbusiness"]
}
```

### /services — Service (one per service you offer)

```json
{
  "@context": "https://schema.org",
  "@type": "Service",
  "name": "Positioning sprint",
  "provider": { "@type": "Organization", "name": "Your Business" },
  "description": "4-week positioning sprint for B2B SaaS founders.",
  "areaServed": "Singapore",
  "offers": {
    "@type": "Offer",
    "price": "8000",
    "priceCurrency": "SGD"
  }
}
```

### /about — BreadcrumbList + Person

```json
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://yourdomain.com" },
    { "@type": "ListItem", "position": 2, "name": "About", "item": "https://yourdomain.com/about" }
  ]
}
```

### /blog/[slug] — Article

```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "Post title",
  "author": { "@type": "Person", "name": "Your Name" },
  "datePublished": "2026-06-06",
  "dateModified": "2026-06-06",
  "image": "https://yourdomain.com/blog/post-slug/cover.png",
  "publisher": {
    "@type": "Organization",
    "name": "Your Business",
    "logo": { "@type": "ImageObject", "url": "https://yourdomain.com/logo.png" }
  }
}
```

### Any page with an FAQ — FAQPage

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "Do I need to know how to code?",
      "acceptedAnswer": { "@type": "Answer", "text": "No." }
    },
    {
      "@type": "Question",
      "name": "What's the refund policy?",
      "acceptedAnswer": { "@type": "Answer", "text": "100% minus the S$30 gift if cancelled more than 14 days before." }
    }
  ]
}
```

### /contact — ContactPoint

```json
{
  "@context": "https://schema.org",
  "@type": "ContactPoint",
  "contactType": "customer support",
  "email": "you@yourdomain.com",
  "areaServed": "SG",
  "availableLanguage": "English"
}
```

## How to verify

Paste your URL (or HTML) into:

- [https://search.google.com/test/rich-results](https://search.google.com/test/rich-results) — Google's official validator.
- [https://validator.schema.org](https://validator.schema.org) — Schema.org's reference validator.

Both should show your structured data parsed correctly with zero errors.

## What this unlocks

- **Google Rich Results** — FAQs and articles can appear with expanded snippets.
- **AI assistant citations** — Claude, ChatGPT, Perplexity preferentially cite pages with clean structured data because they can parse "this is a Service from this Organization at this price" without ambiguity.
- **Knowledge Graph eligibility** — Person and Organization schema feeds Google's Knowledge Graph long-term.

---

**Generated with Claude. Reviewed by Haojun Yong (On The Ground).**
For tailored, hands-on guidance, see [ontheground.agency](https://www.ontheground.agency) or email [haojun@ontheground.agency](mailto:haojun@ontheground.agency).
