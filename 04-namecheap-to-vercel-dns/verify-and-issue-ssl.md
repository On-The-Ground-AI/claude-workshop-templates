# Verify domain and issue SSL

> ⚠️ AI-generated · Reviewed by Haojun See (OTG).

Once nameservers propagate, Vercel verifies the domain and issues SSL automatically. This file covers what to check, and what to do if something's stuck.

## Normal flow

1. Nameservers updated at Namecheap (see [previous step](./point-namecheap-nameservers-to-vercel.md)).
2. Propagation completes within ~30 min to 24h.
3. Vercel marks the domain **Valid Configuration**.
4. SSL issues within 1–5 minutes of verification.
5. `https://yourdomain.com` shows a valid padlock.

## Troubleshooting

### "Invalid Configuration" persists after 24 hours

- **Check propagation:** [dnschecker.org](https://dnschecker.org) → enter domain → type **NS** → confirm `ns1.vercel-dns.com` + `ns2.vercel-dns.com` show globally. If they don't, the Namecheap change didn't save. Go back to Domain List → Manage → Nameservers → re-enter and save.
- **Click Refresh** on the domain row in Vercel Settings → Domains.
- **Wait another 6 hours** — some ISPs cache DNS aggressively.

### SSL fails to issue ("Pending issuance")

- Usually clears on its own within an hour after verification.
- If stuck for 6+ hours, click **Refresh** in Vercel.
- If still stuck, remove the domain and re-add it (no DNS changes needed). Vercel re-attempts SSL issuance from scratch.

### Site loads on HTTP but not HTTPS

- SSL hasn't issued yet. Wait.
- Don't try to "force HTTPS" in your Next.js config — Vercel handles redirects automatically once SSL is up.

### `www.yourdomain.com` shows an error

- In Vercel **Settings** → **Domains**, add the `www.yourdomain.com` variant explicitly. Vercel will issue a separate SSL cert and set up the redirect.

### My old host is still serving the site

- Probably your browser cache. Open a private window or `curl -I yourdomain.com`. If `curl` shows the right `server: Vercel` header, you're good.

## Confirm everything's good

Run all three at a terminal:

```bash
curl -I https://yourdomain.com
# Expect: HTTP/2 200, server: Vercel

dig yourdomain.com NS +short
# Expect: ns1.vercel-dns.com / ns2.vercel-dns.com

dig yourdomain.com +short
# Expect: an A record / Vercel IP
```

If all three look right, you're done. Time to ship the rest of the site.

---

**Generated with Claude. Reviewed by Haojun See (On The Ground).**
For tailored, hands-on guidance, see [ontheground.agency](https://www.ontheground.agency) or email [haojun@ontheground.agency](mailto:haojun@ontheground.agency).
