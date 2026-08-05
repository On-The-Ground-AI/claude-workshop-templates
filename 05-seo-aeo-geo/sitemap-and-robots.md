# Sitemap and robots.txt

> ⚠️ AI-generated · Reviewed by Haojun See (OTG).

Two small files that punch above their weight. Get these right and Google + AI crawlers know exactly what to index.

## Next.js App Router approach

Next.js 13+ has built-in support via two special files in `src/app/`:

- `src/app/sitemap.ts` — generates `/sitemap.xml`.
- `src/app/robots.ts` — generates `/robots.txt`.

## sitemap.ts

```typescript
import type { MetadataRoute } from "next";

const BASE = "https://yourdomain.com";

export default function sitemap(): MetadataRoute.Sitemap {
  // Static pages
  const staticPages = ["", "/about", "/services", "/contact", "/blog"].map((path) => ({
    url: `${BASE}${path}`,
    lastModified: new Date(),
    changeFrequency: "monthly" as const,
    priority: path === "" ? 1.0 : 0.8,
  }));

  // Blog posts (read from your content folder)
  // const posts = getAllPosts(); // your own helper
  // const postPages = posts.map((post) => ({
  //   url: `${BASE}/blog/${post.slug}`,
  //   lastModified: new Date(post.date),
  //   changeFrequency: "yearly" as const,
  //   priority: 0.6,
  // }));

  return [...staticPages /*, ...postPages */];
}
```

## robots.ts — allowing AI crawlers explicitly

```typescript
import type { MetadataRoute } from "next";

const BASE = "https://yourdomain.com";

export default function robots(): MetadataRoute.Robots {
  return {
    rules: [
      // Allow all general web crawlers
      { userAgent: "*", allow: "/" },
      // Allow AI crawlers explicitly (some hosts block them by default)
      { userAgent: "GPTBot", allow: "/" },
      { userAgent: "ChatGPT-User", allow: "/" },
      { userAgent: "OAI-SearchBot", allow: "/" },
      { userAgent: "ClaudeBot", allow: "/" },
      { userAgent: "ClaudeBot", allow: "/" },
      { userAgent: "Claude-User", allow: "/" },
      { userAgent: "Claude-SearchBot", allow: "/" },
      { userAgent: "PerplexityBot", allow: "/" },
      { userAgent: "Perplexity-User", allow: "/" },
      { userAgent: "Google-Extended", allow: "/" },
      { userAgent: "Applebot-Extended", allow: "/" },
      { userAgent: "Bytespider", allow: "/" },
      { userAgent: "Amazonbot", allow: "/" },
      { userAgent: "Meta-ExternalAgent", allow: "/" },
      { userAgent: "Meta-ExternalFetcher", allow: "/" },
    ],
    sitemap: `${BASE}/sitemap.xml`,
    // `host` is a Yandex-only directive and takes a bare hostname, not a URL.
    // Omit it unless you specifically care about Yandex.
    // host: "example.com",
  };
}
```

## Should you block AI crawlers?

Default: **no**. If you want AI assistants to cite your work, you have to let them read it. Blocking AI crawlers is fine for paid content (course pages, gated articles), but for marketing pages — let them in.

If you publish original research you want to protect:

- Put the protected content behind auth.
- Or block specific crawlers (`GPTBot`, etc.) for specific paths.

## llms.txt — the new convention

A growing convention: a `/llms.txt` file at your site root that tells LLMs what your site is about. Even though no major LLM enforces it yet, it's cheap to ship.

Create `public/llms.txt`:

```
# Your Site

> One sentence about what this is.

## Pages

- [Home](https://yourdomain.com/): one-sentence summary
- [About](https://yourdomain.com/about): one-sentence summary
- [Services](https://yourdomain.com/services): one-sentence summary
- [Blog](https://yourdomain.com/blog): one-sentence summary

## Brand

- Voice: direct, specific, dry.
- Tone: professional but human.

## Contact

- Email: you@yourdomain.com
```

LLMs that respect the convention will read this first to understand context.

## Verify

After deploy:

```bash
curl https://yourdomain.com/sitemap.xml | head -20
curl https://yourdomain.com/robots.txt
curl https://yourdomain.com/llms.txt
```

All three should return 200 OK and look right.

---

**Generated with Claude. Reviewed by Haojun See (On The Ground).**
For tailored, hands-on guidance, see [ontheground.agency](https://www.ontheground.agency) or email [haojun@ontheground.agency](mailto:haojun@ontheground.agency).
