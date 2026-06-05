# Purchase a domain on Namecheap

> ⚠️ AI-generated · Reviewed by Haojun Yong (OTG). Time: ~10 minutes.

Skip if you already own a domain.

## Steps

1. Sign in at [https://namecheap.com](https://namecheap.com).

2. Use the search bar to look up the domain you want.

   <!-- SCREENSHOT: namecheap-search.png -->

3. Common TLD picks:
   - `.com` — safest, most universally trusted.
   - `.co` — short, modern, good for personal sites.
   - `.io` — tech-leaning, more expensive (~US$30+/year).
   - `.sg` — needs a Singapore presence to register; SG-trusted.
   - `.ai` — most expensive (~US$60+/year), worth it if your brand is AI-focused.

4. Add to cart. Namecheap will try to upsell:
   - **WhoisGuard / Domain Privacy** — already included free; just confirm it's on.
   - **SSL Certificate** — **skip** (Vercel issues SSL for free).
   - **Premium DNS** — skip.
   - **Web hosting** — skip (Vercel does this).
   - **Domain auto-renewal** — turn this **on** so you don't accidentally lose the domain.

   <!-- SCREENSHOT: namecheap-checkout.png -->

5. Check out, pay, confirm. The domain shows up in **Domain List** within ~60 seconds.

## After purchase

You now own the domain but it doesn't point anywhere. Next step: [point Namecheap's nameservers at Vercel](./point-namecheap-nameservers-to-vercel.md).

## Renewal reminders

- Namecheap emails you 60, 30, and 7 days before renewal.
- Auto-renewal is on by default if you ticked the box.
- Keep at least one valid card on file; expired cards = failed renewal = lost domain.

---

**Generated with Claude. Reviewed by Haojun Yong (On The Ground).**
For tailored, hands-on guidance, see [ontheground.agency](https://www.ontheground.agency) or email [haojun@ontheground.agency](mailto:haojun@ontheground.agency).
