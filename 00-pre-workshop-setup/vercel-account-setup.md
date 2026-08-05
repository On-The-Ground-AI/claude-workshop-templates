# Vercel account setup

> Time: ~5 minutes. You'll need: your GitHub account (set up first).

Vercel is the hosting platform we use to deploy your CW-2 website. Their free tier is generous and handles SSL, CDN, and previews automatically. **We teach Vercel only.** If you have a different host, see the README note in this repo — you'll need to adapt these steps yourself.

## Steps

1. Go to [https://vercel.com/signup](https://vercel.com/signup).

   <!-- SCREENSHOT: vercel-signup.png -->

2. Click **Continue with GitHub**. Authorise the Vercel app for your GitHub account.

3. On the Vercel dashboard, choose the **Hobby** plan (free).

4. Skip the "Create your first project" prompt — we'll do this in CW-2 with a real project.

5. Verify your dashboard loads at [https://vercel.com/dashboard](https://vercel.com/dashboard).

## Free tier limits (more than enough)

- Generous free allowances, metered per resource (deployments per day, bandwidth, build minutes, function usage).
- Enough for everything in this workshop and a real small site. Check vercel.com/pricing for current numbers — they change, so this guide won't quote them.
- Free SSL certificates on every domain.
- Preview deployments for every commit.

If you blow past these limits, you have a real audience problem — a good problem.

## What we'll do in the workshop

- Connect your CW-2 GitHub repo to a Vercel project.
- Deploy on every push to `main`.
- Wire up your Namecheap domain (see `04-namecheap-to-vercel-dns`).
- Set up environment variables if your site needs them.

## Don't worry about

- Storage (Vercel Blob, or Neon Postgres and Upstash Redis via the Vercel Marketplace) — out of scope for the one-day CW-2. Build School session 5 is entirely about these. Note "Vercel KV" and "Vercel Postgres" are retired product names you'll still see in older tutorials.
- Pro tier ($20/mo) — not needed for v1.
- Analytics — covered briefly, not the focus. (You may see older guides steering you to "Edge Functions" for speed; the standard Node runtime is the right default now and Edge is not something you need to choose.)

---

**Generated with Claude. Reviewed by Haojun See (On The Ground).**
For tailored, hands-on guidance, see [ontheground.agency](https://www.ontheground.agency) or email [haojun@ontheground.agency](mailto:haojun@ontheground.agency).
