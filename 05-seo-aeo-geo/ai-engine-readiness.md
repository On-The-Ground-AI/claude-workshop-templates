# AI engine readiness — what ChatGPT, Claude, Perplexity actually cite

> ⚠️ AI-generated · Reviewed by Haojun See (OTG).

You want to be in the sentences that come out of AI engines when someone asks "best [your category] in Singapore" or "how do I [your service]." Here's what we know about how to get there in 2026.

## The two cohorts of AI search

1. **AI engines that are actually search engines** — Perplexity, ChatGPT (with web search), Google AI Overviews, Bing Copilot. They crawl the web in real time or near-real time. They cite. They link.
2. **AI assistants that answer from training + occasional retrieval** — Base ChatGPT, Claude, Gemini in chat mode. They've seen your site during training but won't cite it unless you've nailed structured data.

Both groups reward the same things, in roughly this order.

## What gets cited

### 1. Pages with clean structured data (JSON-LD)

This is the single highest-leverage move. AI engines preferentially parse pages that tell them "this is a `Service` from this `Organization` at this `price`." See [json-ld-schemas.md](./json-ld-schemas.md).

### 2. Pages with a clear answer in the opening 50 words

AI engines look for a direct answer. Your page on "how to point a Namecheap domain at Vercel" should start with the answer ("Set custom nameservers to ns1.vercel-dns.com and ns2.vercel-dns.com…"), not a 300-word intro about DNS.

### 3. Pages with FAQ schema

A `FAQPage` schema with 5–10 common questions gives AI engines pre-extracted Q&A pairs to cite. Use this on service pages, course pages, product pages.

### 4. Pages linked from authoritative sites

Same as classic SEO. The difference: AI engines weight "authoritative in this niche" higher than "authoritative in general."

### 5. Pages with named-entity density

If your page mentions specific people, companies, products, tools by name (e.g. "Claude Code", "Next.js 16", "Vercel"), AI engines connect those entities to the topic and surface you when those entities come up in queries.

### 6. Pages with original data, examples, or claims

"We've run this on 12 SG clients" beats "we help businesses grow." AI engines preferentially cite pages that say something specific because something specific is *citable*.

## What doesn't help

- Keyword stuffing in meta tags.
- Hidden text or cloaking — gets you penalised.
- AI-generated content that reads AI-generated. The irony.
- 10,000-word essays where the answer is in paragraph 47.
- Aggressive interstitials, popups, slow load times.

## How to test if you're being cited

### Perplexity test

Ask Perplexity: "best [your category] in Singapore" or "[specific thing you do]." See if your page appears as a citation. Iterate.

### ChatGPT search test

Same thing in ChatGPT with browsing enabled.

### Brand-mention monitoring

Tools like [Profound](https://www.tryprofound.com/), [AthenaHQ](https://www.athenahq.ai/), or [Otterly](https://otterly.ai/) track when your brand or domain is cited by AI engines. Most have free trials.

### Google AI Overviews

For Google specifically, query your target phrases and see if your domain shows up in the AI Overview at the top of results.

## A pragmatic order of operations

1. **Week 1:** Meta tags + sitemap + robots + GSC verified. (Table stakes.)
2. **Week 2:** JSON-LD schemas everywhere relevant. (AEO foundation.)
3. **Week 3:** Re-write top 5 pages with the "answer in the first 50 words" structure.
4. **Week 4:** Add FAQ schemas to course/service/product pages.
5. **Month 2 onwards:** Publish topic content (one piece per week), monitor citations, iterate.

You won't see AI citations day one. Most sites we've built start showing up in Perplexity within 4–8 weeks of consistent publishing.

## Things to keep doing forever

- Update `dateModified` whenever you refresh content. AI engines weight fresher pages.
- Internal-link new content from existing pages. Helps both Google and AI crawlers.
- Add structured data to every new page type. Don't drift.
- Re-test your top queries in Perplexity / ChatGPT monthly. The space moves fast.

---

**Generated with Claude. Reviewed by Haojun See (On The Ground).**
For tailored, hands-on guidance, see [ontheground.agency](https://www.ontheground.agency) or email [haojun@ontheground.agency](mailto:haojun@ontheground.agency).
