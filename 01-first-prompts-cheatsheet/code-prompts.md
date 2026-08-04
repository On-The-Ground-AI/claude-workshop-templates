# Code prompts (CW-2)

> ⚠️ AI-generated · Reviewed by Haojun See (OTG).

10 prompts for Claude Code building your CW-2 website on Next.js + Vercel + Namecheap.

---

## 1. Scaffold the project

**Use it when:** Day one, empty repo.

**The prompt:**
```
Scaffold a new Next.js 16 + TypeScript + Tailwind 4 project for my personal/business website. Pages I need: home, about, services, contact, blog (with at least 3 sample posts in MDX or plain markdown).

Read CLAUDE.md and brand-brief.md for tone, target audience, and what we sell. Match the design described there. Use a single accent colour and one heading font.

Push to GitHub under my own account at [my-username]/[my-slug]. Set up the repo with a minimal README.
```

**Output:** Working project, deployed locally, pushed to GitHub.

**Try this next:** Ship it to Vercel.

---

## 2. The brand voice gate

**Use it when:** Generated content reads "AI-generated."

**The prompt:**
```
Re-read CLAUDE.md and brand-brief.md. Then look at the homepage hero. Rewrite it three times, each in a different voice from my brand voice principles. I'll pick. Keep specifics, kill generic SaaS phrases like "leverage", "unlock potential", "revolutionise."
```

**Output:** Three options with real personality.

**Try this next:** Apply the same prompt to /about and /services.

---

## 3. SEO foundations pass

**Use it when:** Before first deploy.

**The prompt:**
```
For every page in /src/app/*, ensure there's:
- A unique <title> via Next.js Metadata API, 50–60 chars.
- A unique meta description, 140–160 chars.
- Open Graph tags (title, description, image, url).
- Twitter card tags.
- A canonical URL.

Read 05-seo-aeo-geo/meta-tags-checklist.md for the format I prefer. Apply once across the whole site.
```

**Output:** Every page has proper meta. View source to verify.

**Try this next:** Run a Lighthouse audit and ask Claude to fix what fails.

---

## 4. JSON-LD schemas for AEO

**Use it when:** SEO is done; you want AI engines to cite you.

**The prompt:**
```
Add JSON-LD schemas to:
- Homepage: Person (if personal) or Organization (if business). Include sameAs links for LinkedIn, GitHub, X.
- /services: Service for each thing I sell.
- /about: BreadcrumbList + Person/Organization.
- /blog/[slug]: Article schema with author, datePublished, dateModified.
- /contact: ContactPoint.

Read 05-seo-aeo-geo/json-ld-schemas.md for the structures. Insert with next/script tags in each layout/page as appropriate.
```

**Output:** Structured data ChatGPT, Claude, Perplexity, and Google can parse.

**Try this next:** Validate at https://search.google.com/test/rich-results.

---

## 5. Sitemap + robots

**Use it when:** Ready to deploy publicly.

**The prompt:**
```
Generate app/sitemap.ts using Next.js's MetadataRoute.Sitemap. Include every page + every blog post. priority: 1.0 for /, 0.8 for /services and /about, 0.6 for blog posts.

Generate app/robots.ts that allows all crawlers, points to the sitemap, and explicitly allows the AI crawlers (GPTBot, ChatGPT-User, ClaudeBot, Anthropic-AI, PerplexityBot, OAI-SearchBot).
```

**Output:** /sitemap.xml and /robots.txt at root, automatically updated on each build.

**Try this next:** Submit /sitemap.xml in Google Search Console.

---

## 6. Deploy to Vercel

**Use it when:** Ready to go live.

**The prompt:**
```
Walk me through deploying this Next.js site to Vercel:
1. Connect the GitHub repo to a Vercel project.
2. Confirm the build settings (Next.js auto-detected).
3. Add any environment variables I need.
4. Deploy and give me the .vercel.app URL.

Don't suggest Cloudflare, Netlify, or any other host — Vercel only.
```

**Output:** Live URL at *.vercel.app. SSL automatic.

**Try this next:** Wire your Namecheap domain.

---

## 7. Namecheap → Vercel custom domain

**Use it when:** Your *.vercel.app URL is working and you want your real domain.

**The prompt:**
```
Walk me through pointing my Namecheap domain [DOMAIN] at this Vercel project.

I want to use Vercel's nameservers (cleanest). Tell me exactly what to:
1. Type in Vercel (Project → Settings → Domains).
2. Change at Namecheap (Domain List → Manage → Nameservers).
3. Verify (DNS propagation, SSL issuance).
4. Test once it's live.

Read 04-namecheap-to-vercel-dns/ in the templates repo for the screenshots.
```

**Output:** Live HTTPS site at your real domain.

**Try this next:** Add www subdomain + redirect.

---

## 8. Blog post that doesn't read AI-generated

**Use it when:** You want to ship blog content that actually sounds like you.

**The prompt:**
```
Read CLAUDE.md and 3 of my existing blog posts (or my LinkedIn posts). Match that voice.

Write a 700-word blog post titled "[YOUR TITLE]". Include:
- A specific opening (not "in today's fast-paced world").
- One personal example from my real work (ask me if you don't know one).
- Three concrete tactics, each with a real-world consequence.
- A closing that resists the urge to summarise.
- No emoji. No "let's dive in."

Save as src/content/blog/[slug].mdx with proper frontmatter (title, date, description).
```

**Output:** A post that survives a reader skim.

**Try this next:** Add internal links from this post to 2 related ones.

---

## 9. Google Search Console connection

**Use it when:** Site is live; you want indexing.

**The prompt:**
```
Walk me through verifying my domain in Google Search Console:
1. Add property at https://search.google.com/search-console.
2. Verify via DNS TXT record (Namecheap).
3. Submit the /sitemap.xml.
4. Configure email alerts for indexing issues.

Tell me what to paste, where to paste it, and how long to wait.
```

**Output:** Search Console verified; sitemap submitted; alerts on.

**Try this next:** Wait 48 hours and check coverage.

---

## 10. Post-launch debug loop

**Use it when:** Something on the live site is broken.

**The prompt:**
```
The site at [URL] has a problem: [DESCRIBE]. Walk me through:
1. Reproducing it locally with npm run dev.
2. Finding the responsible file by reading the build output.
3. The smallest possible fix.
4. Pushing the fix and verifying the Vercel deploy.

Don't refactor unrelated code. Don't change the design. Just fix the bug.
```

**Output:** A clean diff that fixes the bug.

**Try this next:** Keep this prompt as your "bug fix" macro.

---

**Generated with Claude. Reviewed by Haojun See (On The Ground).**
For tailored, hands-on guidance, see [ontheground.agency](https://www.ontheground.agency) or email [haojun@ontheground.agency](mailto:haojun@ontheground.agency).
