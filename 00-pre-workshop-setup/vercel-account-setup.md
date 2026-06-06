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

- Unlimited deployments.
- 100 GB bandwidth per month.
- Free SSL certificates on every domain.
- Preview deployments for every commit.

If you blow past these limits, you have a real audience problem — a good problem.

## What we'll do in the workshop

- Connect your CW-2 GitHub repo to a Vercel project.
- Deploy on every push to `main`.
- Wire up your Namecheap domain (see `04-namecheap-to-vercel-dns`).
- Set up environment variables if your site needs them.

## Don't worry about

- Vercel KV / Vercel Blob / Postgres — out of scope for CW-2.
- Pro tier ($20/mo) — not needed for v1.
- Edge functions or analytics — covered briefly, not the focus.

---

**Generated with Claude. Reviewed by Haojun See (On The Ground).**
For tailored, hands-on guidance, see [ontheground.agency](https://www.ontheground.agency) or email [haojun@ontheground.agency](mailto:haojun@ontheground.agency).
