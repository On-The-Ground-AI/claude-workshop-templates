# Point Namecheap nameservers at Vercel

> ⚠️ AI-generated · Reviewed by Haojun Yong (OTG). Time: ~5 minutes + 24h DNS propagation.

This is the core step. After this, Vercel owns the DNS for your domain and SSL issues automatically.

## Step 1 — In Vercel, add the domain

1. Open your Vercel project → **Settings** → **Domains**.
2. Type your domain (e.g. `yourname.com`). Click **Add**.

   <!-- SCREENSHOT: vercel-domains-add.png -->

3. Vercel will show you two options. Pick **Nameservers** (not "A Record" or "CNAME") — Vercel will display:
   ```
   ns1.vercel-dns.com
   ns2.vercel-dns.com
   ```

   <!-- SCREENSHOT: vercel-nameservers-shown.png -->

4. Vercel will mark the domain as **Invalid Configuration** for now. That's fine — we'll fix it at Namecheap.

## Step 2 — At Namecheap, change the nameservers

1. Sign in at [https://namecheap.com](https://namecheap.com).
2. **Domain List** → click **Manage** on your domain.

   <!-- SCREENSHOT: namecheap-domain-list.png -->

3. Scroll to the **Nameservers** section. By default it's set to **Namecheap BasicDNS**.
4. Change the dropdown to **Custom DNS**.
5. Enter exactly:
   ```
   ns1.vercel-dns.com
   ns2.vercel-dns.com
   ```
6. Click the **green checkmark** to save.

   <!-- SCREENSHOT: namecheap-custom-dns.png -->

## Step 3 — Wait for propagation

DNS propagation takes anywhere from 30 minutes to 24 hours. Most domains propagate in under an hour.

Check progress at [https://dnschecker.org](https://dnschecker.org):
- Enter your domain.
- Set type to **NS** (nameserver).
- Click **Search**.
- You want most regions to show `ns1.vercel-dns.com` + `ns2.vercel-dns.com`.

   <!-- SCREENSHOT: dnschecker-ns.png -->

## Step 4 — Verify on Vercel

Once DNS propagates:

1. Go back to Vercel **Settings** → **Domains**.
2. Your domain status should flip from **Invalid Configuration** to **Valid Configuration** automatically.
3. SSL issues automatically (Let's Encrypt). Takes 1–5 minutes.

If it doesn't flip after 24 hours, click **Refresh** on the domain row in Vercel. If still failing, see [verify-and-issue-ssl.md](./verify-and-issue-ssl.md).

## Step 5 — Test

Open `https://yourdomain.com` in a fresh browser tab. You should see your site with a valid SSL padlock.

Try `https://www.yourdomain.com` — Vercel auto-redirects it to the non-www version (or vice versa, depending on which you set as primary).

---

**Generated with Claude. Reviewed by Haojun Yong (On The Ground).**
For tailored, hands-on guidance, see [ontheground.agency](https://www.ontheground.agency) or email [haojun@ontheground.agency](mailto:haojun@ontheground.agency).
