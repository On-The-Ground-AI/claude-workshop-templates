# Deploy walkthrough — Claude Code → GitHub → Vercel

> ⚠️ AI-generated · Reviewed by Haojun See (OTG). Time: ~20 minutes assuming accounts are set up.

The first time you go from "I have no code" to "live website on the internet." We do this in CW-2; this file is the written version.

## Pre-requisites

- Claude Pro or Max (`brand-brief.md` and `CLAUDE.md` ready in your `~/Documents/Workshops/` or similar working folder).
- GitHub account, 2FA on.
- Vercel account, connected to GitHub.
- Claude Code installed (`npm install -g @anthropic-ai/claude-code` or the official installer).

## Step 1 — Open Claude Code in an empty folder

```bash
mkdir my-site
cd my-site
claude
```

   <!-- SCREENSHOT: claude-code-empty-folder.png -->

## Step 2 — The scaffold prompt

Type this into Claude Code:

```
Scaffold a new Next.js 16 + TypeScript + Tailwind 4 site for my personal/business website.

Read CLAUDE.md and brand-brief.md (they're in this folder once you create them; I'll paste them in if you ask).

Pages: home, about, services, contact, blog (with 3 sample MDX posts).

Single accent colour, one heading font, mobile-first responsive. No client-side animation libraries. SEO meta on every page.

Use git init and create the first commit. Don't push yet — I'll do GitHub next.
```

Claude Code will write the files. Watch what it generates. If it suggests Cloudflare or another host, redirect: "Vercel only. Don't suggest other hosts."

## Step 3 — Push to GitHub

```bash
gh repo create my-site --private --source=. --remote=origin --push
```

(If you don't have `gh`, install it: `brew install gh && gh auth login`.)

   <!-- SCREENSHOT: gh-repo-create.png -->

## Step 4 — Connect Vercel

1. Go to [https://vercel.com/new](https://vercel.com/new).
2. Click **Import** next to your new GitHub repo.
3. Framework: **Next.js** (auto-detected).
4. Click **Deploy**.

   <!-- SCREENSHOT: vercel-import.png -->

You'll get a `https://my-site-[hash].vercel.app` URL in ~60 seconds. Open it on your phone to verify.

## Step 5 — Iterate from Claude Code

Keep Claude Code open. Tell it:

```
The homepage hero copy is too generic. Rewrite it three times, each with a different angle from brand-brief.md. I'll pick.
```

Once you pick, commit:

```bash
git add -A
git commit -m "Hero copy v2"
git push
```

Vercel auto-deploys on push. ~60 seconds later your live URL has the new copy.

## Step 6 — Wire your real domain (Namecheap → Vercel)

See [`04-namecheap-to-vercel-dns`](../04-namecheap-to-vercel-dns/) for the screenshots and exact steps.

## Step 7 — SEO + AEO + GEO

See [`05-seo-aeo-geo`](../05-seo-aeo-geo/) for the structured pass we run before considering the site "shipped."

## Common pitfalls

- **Claude Code suggests Cloudflare Pages.** Override: "Vercel only — don't suggest other hosts."
- **Repo is public by accident.** Make sure you used `--private`. You can flip later with `gh repo edit --visibility public`.
- **Build fails on Vercel but passes locally.** Usually a missing env var or Node version mismatch. Add the env in Vercel Project Settings → Environment Variables.
- **You can't find your CSS changes on the live site.** Vercel deploys are atomic; you might be looking at an old preview URL. Use the production URL (`yourdomain.com` or the canonical `.vercel.app`).

---

**Generated with Claude. Reviewed by Haojun See (On The Ground).**
For tailored, hands-on guidance, see [ontheground.agency](https://www.ontheground.agency) or email [haojun@ontheground.agency](mailto:haojun@ontheground.agency).
