# Gautham & Sarika

Wedding e-invitation for Gautham Prasath and Sarika, 12–13 November 2026, Avinashi.

The whole invite is one static page, `index.html`. Its artwork is embedded and it has no build step, so it can be served from any static host.

## What's on the page

- **Opening:** guests tap the G & S seal. Burgundy velvet curtains draw back into gold tie-backs, and blush-beige curtains with tasselled tie-backs open behind them. A candle-lit chandelier lowers into the centre, then the scene fades as the names rise and marigold petals fall.
- **Hero:** names and parents, the chandelier resting between the garlands, and a G S monogram between the diyas.
- **Save the date:** a Google Calendar link for the muhurtham.
- **Countdown:** counts down to 13 Nov 2026, 9:00 AM IST.
- **Programme:** both days' events on a timeline that draws in as you scroll, under a mango-leaf and marigold toran.
- **Venues:** line-art of the temple gopuram and the marriage hall, with Google Maps links.
- **Closing:** the families' sign-off and a second monogram.

A replay button (bottom right) runs the opening again. Visitors with reduced motion turned on skip the animations.

## Hosting on your domain

1. Upload `index.html` to the web root, or to the folder you want the invite served from.
2. Add a link-preview image named `preview.jpg` (1200 × 630) next to it. WhatsApp and other apps show this image when the link is shared.
3. In the `<head>` of `index.html`, change these two tags to your real address. Link previews need full `https://` URLs:
   ```html
   <meta property="og:image" content="https://YOUR-DOMAIN/preview.jpg">
   <meta property="og:url" content="https://YOUR-DOMAIN/">
   ```
4. Serve the site over HTTPS, then open the link on a phone and tap the seal to check the opening.
5. Before sharing, paste the link into a WhatsApp chat to yourself and check that the preview card shows the image and title. WhatsApp caches previews, so fix the tags before the first share.

The page loads two Google Fonts (Cormorant Garamond and Jost) and links out to Google Maps and Google Calendar. Everything else is inside `index.html`.
