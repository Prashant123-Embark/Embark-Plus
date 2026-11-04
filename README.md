# Embark+ website

A single-page static website. No build step and no dependencies: one `index.html` plus the `img/` folder.

## Preview locally
Open `index.html` in Chrome, or run a local server in this folder:

    python3 -m http.server 8080

then visit http://localhost:8080.

## Publish
Upload the whole folder (index.html and img/) to any static host, for example Netlify (drag and drop the folder), Vercel, Cloudflare Pages, or your existing web server. No server-side code is needed.

## Demo form
On Netlify the form posts to Netlify Forms. Submissions appear in the Netlify dashboard under Forms > demo. Add an email notification there (Forms > Form notifications) so each enquiry reaches Prashant@embark.media.

## Connect the demo form to another backend (optional)
The Book a platform demo form validates every field, but it only reports success after an enquiry has really been saved.

1. Choose where enquiries should go: a CRM webhook (HubSpot, Zoho, Salesforce), a form service (Formspree, Basin, Netlify Forms) or your own endpoint.
2. In `index.html`, find `const LEAD_ENDPOINT='';` and paste the endpoint URL between the quotes. Requests time out after 15 seconds and show a fallback message.
3. The form sends a JSON POST with: name, business, email, phone, website, create, submittedAt.
4. Until this is set, the form shows a clear message asking visitors to email Prashant@embark.media or call instead. It never pretends a request was sent.

Inside the claude.ai preview, the form saves enquiries to the page's own data store instead (for people the page is shared with).

## Before launch
- Favicon: add a square Embark+ icon file (for example the plus mark exported by your designer) as `favicon.png` and a `<link rel="icon" href="favicon.png">` line in the head. It was not created here, so the logo was not redrawn.
- Confirm the phone number +971 50 345 871 (UAE mobiles usually have nine digits after +971).
- Have a native speaker check the Arabic sample creatives.
- Replace the illustrated product scenes with real brand photography when available.
- Images are WebP; all modern browsers support them.

## Overview video
The overview video lives at `video/embark-overview.mp4` (59.5 seconds, 1080p, compressed for the web) with its poster at `img/video-poster.webp`. To swap it, replace that file with a new MP4 of the same name.

## Sharing previews
- `og:image` points to `img/og-image.png`. It is set to https://embark-plus.netlify.app/img/og-image.png. If you move to your own domain, update it to that address, because LinkedIn, WhatsApp and X need an absolute URL.

## Accessibility and QA notes
- Tested at 1440, 1280, 820, 390 and 360 px wide, and with reduced motion switched on.
- Keyboard: arrow keys on the product tabs, Escape closes the menu and the gallery viewer, focus returns to where it came from.
- The hero is a static, one-screen section. Visitors with reduced motion get no autoplay in the creative belt or reels, and counters that show final values.

## Fonts
Sora, Instrument Sans and IBM Plex Mono load from Google Fonts, plus Archivo and Fraunces for the sample creatives.
