# River Tips from Locals

Mobile-first landing page for the San Marcos river magnet / shuttle-bus campaign.

The site is intentionally designed as a phone-first doom-scroll page because the expected visitor is scanning a QR code from a bus, magnet, or screen.

## Repository structure

```text
.
├── assets/
│   ├── favicon.svg
│   └── og-image.svg
├── src/
│   ├── main.js
│   ├── sponsors.js
│   └── styles.css
├── index.html
├── package.json
├── robots.txt
├── site.webmanifest
├── sitemap.xml
├── netlify.toml
├── wrangler.toml
├── .editorconfig
├── .gitignore
├── .prettierrc
└── README.md
```

## Local development

```bash
npm install
npm run dev
```

Then open the local Vite URL shown in the terminal.

## Static deployment

This site can be deployed as a static site to Cloudflare Pages, Netlify, Vercel, GitHub Pages, or any basic static web host.

For Cloudflare Pages:

- Framework preset: `None` or `Vite`
- Build command: `npm run build`
- Build output directory: `dist`

For a no-build static host, upload these files directly and point the web root at the repository root. The page uses only HTML, CSS, and vanilla JavaScript.

## Sponsor logos

The current implementation pulls favicon-style images from business domains through Google favicon endpoints. This is useful for a fast proof, but production should replace these with approved sponsor logo files in `assets/logos/`.

Recommended production pattern:

```js
{
  name: 'Example Sponsor',
  category: 'Example category',
  url: 'https://example.com',
  logo: '/assets/logos/example-sponsor.svg'
}
```

Then update `src/main.js` to prefer `sponsor.logo` before using favicon fallback.

## Legal / rules content

The rules section is a plain-English summary and links to the City of San Marcos as the source of truth. Verify rules before launch and periodically during river season.

Current referenced official sources:

- City of San Marcos Single-Use Beverage Container Ban
- City of San Marcos Park Rules

## Pre-launch checklist

- Replace `https://example.com` in `robots.txt` and `sitemap.xml` with the production domain.
- Add approved BNI and sponsor logos where available.
- Verify all sponsor links and categories.
- Confirm river rules against current City of San Marcos pages.
- Test QR code destination on iPhone and Android over cellular.
- Test from 3 to 6 feet away, because the scan origin is bus/magnet signage.
