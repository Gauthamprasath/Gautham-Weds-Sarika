# Gautham & Sarika

Wedding e-invitation for **Gautham Prasath** and **Sarika**, 12–13 November 2026, Avinashi, Tamil Nadu.

The whole invite is one static page, `index.html`. Its artwork, styles and script are embedded, and there's no build step, so it can be served by GitHub Pages or any other static host.

## What's on the page

| Section | What guests see |
|---|---|
| Opening | Guests tap the G & S seal. Burgundy velvet curtains draw back into gold tie-backs, and blush-beige curtains with tasselled tie-backs open behind them. A candle-lit crystal chandelier lowers into the centre, then the scene fades as the names rise and marigold petals fall. |
| Hero | Ganesha symbol (உ), the couple's names and parents, the chandelier resting between the marigold garlands, and a G S monogram between the diyas |
| Save the date | Muhurtham date and a Google Calendar button |
| Countdown | Live countdown to 13 Nov 2026, 9:00 AM IST |
| Programme | Both days' events on a timeline that draws in as you scroll, with a gold icon per event, under a mango-leaf and marigold toran |
| Venues | Line-art of the temple gopuram and the marriage hall, each with a Google Maps button |
| Closing | Blessings, the families' sign-off and a second monogram |

A replay button (bottom right) runs the opening again. Visitors who have reduced motion turned on skip the animations.

## Repository layout

```
index.html    the invitation (everything is inline)
preview.jpg   link-preview image for WhatsApp and other apps (add this, 1200 × 630)
CNAME         your custom domain, one line (created when you set up the domain)
README.md
```

## Preview locally

Open `index.html` in a browser. To test on a phone on the same Wi-Fi, serve the folder:

```bash
python -m http.server 8000
```

Then open `http://<your-computer's-IP>:8000` on the phone.

## Publish with GitHub Pages

1. Push this folder to a GitHub repository.
2. In the repository, go to **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, and save.
3. After a minute the invite is live at `https://<username>.github.io/<repository>/`.

## Use your own domain

1. In **Settings → Pages → Custom domain**, enter your domain (for example `invite.example.com`) and save. GitHub adds a `CNAME` file to the repository.
2. At your domain registrar, add the DNS records:
   - **Subdomain** (such as `invite.example.com` or `www.example.com`): a `CNAME` record pointing to `<username>.github.io`.
   - **Root domain** (such as `example.com`): `A` records pointing to `185.199.108.153`, `185.199.109.153`, `185.199.110.153` and `185.199.111.153`.
3. When the DNS check passes, tick **Enforce HTTPS**.

DNS changes can take anywhere from a few minutes to a day to take effect.

## Before sharing the link

1. Add `preview.jpg` (1200 × 630) to the repository root.
2. In the `<head>` of `index.html`, change these two tags to your final address. Link previews need full `https://` URLs:
   ```html
   <meta property="og:image" content="https://YOUR-DOMAIN/preview.jpg">
   <meta property="og:url" content="https://YOUR-DOMAIN/">
   ```
3. Open the link on a phone and tap the seal to check the opening.
4. Send the link to yourself on WhatsApp and check that the preview card shows the image and title. WhatsApp caches previews, so fix the tags before you share the link with guests.

## Editing the details

All text is in `index.html`:

- **Events and times:** the `<ol class="timeline">` list in the Programme section.
- **Venues and map links:** the `<div class="venue">` cards.
- **Save the date:** the `href` of the `#save-date` button, a Google Calendar link with the date in UTC.
- **Countdown target:** `Date.UTC(2026, 10, 13, 3, 30, 0)` in the script. Months count from 0, and the time is in UTC (9:00 AM IST is 3:30 UTC).

The page uses two Google Fonts, Cormorant Garamond and Jost, and links out to Google Maps and Google Calendar. Everything else is self-contained.
