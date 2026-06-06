# 04 · Namecheap → Vercel DNS

> ⚠️ AI-generated · Reviewed by Haojun See (OTG).

Buy or point a domain at Namecheap, set the nameservers Vercel needs, verify, issue SSL. **We teach Namecheap + Vercel only — by design.** If you use another registrar or host, the principles transfer but you'll need to adapt these steps yourself.

| File | What it covers |
|---|---|
| [purchase-domain-namecheap.md](./purchase-domain-namecheap.md) | Buying a domain on Namecheap (skip if you already have one) |
| [point-namecheap-nameservers-to-vercel.md](./point-namecheap-nameservers-to-vercel.md) | The DNS step — point Namecheap at Vercel's nameservers |
| [verify-and-issue-ssl.md](./verify-and-issue-ssl.md) | Vercel verifies the domain, SSL issues, you test |

## Why Vercel's nameservers (not just A records)

Two options exist when pointing a Namecheap domain at Vercel:

1. **Use Vercel's nameservers** (`ns1.vercel-dns.com` + `ns2.vercel-dns.com`) — Vercel owns the DNS, you get free SSL, www-redirect, and zero ongoing maintenance. We recommend this.
2. **Keep Namecheap's nameservers + add an A record / CNAME** — you keep DNS at Namecheap and add records pointing at Vercel. Useful if you have email or other services on the same domain.

**For CW-2 graduates with no other DNS needs on the domain, go with option 1.** The walkthroughs in this folder assume option 1.

## Why not Cloudflare DNS?

It's fine. But we don't teach it — we stay narrow so the room time goes into building. Once you've shipped, you can migrate to Cloudflare DNS in 10 minutes if you want.

---

**Generated with Claude. Reviewed by Haojun See (On The Ground).**
For tailored, hands-on guidance, see [ontheground.agency](https://www.ontheground.agency) or email [haojun@ontheground.agency](mailto:haojun@ontheground.agency).
