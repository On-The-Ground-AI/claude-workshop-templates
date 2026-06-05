# Google Search Console setup

> ⚠️ AI-generated · Reviewed by Haojun Yong (OTG). Time: ~10 minutes.

Search Console is Google's free tool to monitor indexing, search queries, and crawl issues. Setting it up at launch saves you a month of guessing.

## Steps

1. Go to [https://search.google.com/search-console](https://search.google.com/search-console).
2. Sign in with the Google account you want to use (your work Gmail is fine).
3. Click **Add property** → choose **Domain** (not URL prefix).

   <!-- SCREENSHOT: gsc-add-property.png -->

4. Enter your domain (e.g. `yourdomain.com`, no `https://`, no `www.`).
5. Click **Continue**. Google shows you a **TXT record** to add to your DNS.

   <!-- SCREENSHOT: gsc-txt-record.png -->

6. Copy the TXT record value (looks like `google-site-verification=abc123...`).

7. **In Vercel** (since your nameservers point at Vercel):
   - Project → **Settings** → **Domains** → click on your domain.
   - Find the **DNS Records** section.
   - Add a new TXT record:
     - Name: `@`
     - Value: `google-site-verification=abc123...` (the full string from Google)
     - TTL: default (60 seconds is fine)
   - Save.

   <!-- SCREENSHOT: vercel-dns-txt.png -->

8. Wait ~5 minutes for DNS to propagate. Go back to Search Console and click **Verify**.

9. ✅ Verified. You now have access to your domain in Search Console.

## Submit your sitemap

1. In Search Console → **Sitemaps** (left nav).
2. Enter `sitemap.xml` (just that, not the full URL).
3. Click **Submit**.

   <!-- SCREENSHOT: gsc-sitemap-submit.png -->

Google will crawl it within 24 hours. You'll see "Success" once parsed.

## Set up email alerts

Search Console → **Settings** (left nav, bottom) → **Email preferences**:

- Indexing issues: **on**.
- Coverage issues: **on**.
- Performance updates: weekly is enough.

You'll get an email the moment something breaks.

## What to check, weekly

- **Coverage** → are pages getting indexed? Filter for "Not indexed" to see issues.
- **Performance** → which pages get impressions / clicks? Track over time.
- **Sitemaps** → still marked Success?
- **URL Inspection** tool → paste any URL to see what Google sees.

## Bonus: Bing Webmaster Tools

Same idea, smaller share of search but matters for AI engines (ChatGPT search is powered by Bing). Same domain verification flow at [https://www.bing.com/webmasters](https://www.bing.com/webmasters).

---

**Generated with Claude. Reviewed by Haojun Yong (On The Ground).**
For tailored, hands-on guidance, see [ontheground.agency](https://www.ontheground.agency) or email [haojun@ontheground.agency](mailto:haojun@ontheground.agency).
