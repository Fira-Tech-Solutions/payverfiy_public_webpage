# PayVerify — Landing Page

A responsive marketing site for **PayVerify**, a payment-verification app for Ethiopian
merchants (QR / receipt-OCR / transaction-ID checks against CBE, TeleBirr, Awash, Dashen,
Bank of Abyssinia, Amole, HelloCash, and M-Pesa ET).

Built with React 18 + Vite + Tailwind CSS.

## Run it locally

```bash
npm install
npm run dev
```

Open the URL Vite prints (usually `http://localhost:5173`).

## Build for production

```bash
npm run build
npm run preview   # optional, serves the production build locally
```

The static site is output to `dist/` — upload that folder to any static host
(Netlify, Vercel, GitHub Pages, S3, cPanel, etc).

## Project structure

```
src/
  components/
    Navbar.jsx           sticky nav with mobile menu + dark/light toggle
    Hero.jsx             headline + animated verification stamp phone mockup
    StatsBanner.jsx      live stats counter with scroll-triggered animation
    Features.jsx         QR scan, receipt OCR, TeleBirr/CBE, offline queue
    AppGallery.jsx       app screenshot carousel
    RBACSection.jsx      owner vs cashier feature comparison
    DownloadSection.jsx  Android (APK, Galaxy Store, AppGallery, APKPure) + iOS (App Store, TestFlight)
    Footer.jsx           contact info, links, social
  data.js                all copy/content — pricing, features, stats, payment methods
  hooks/
    useCountUp.js        animated number counter hook
    useTheme.js          dark/light mode with system preference detection
  App.jsx                assembles the page
  index.css              Tailwind base + custom utilities
tailwind.config.js       color, font, and animation tokens (design system)
vite.config.js           host 0.0.0.0 + allowedHosts for tunnel access
```

## Design system

Colors and type live in `tailwind.config.js` — brand tokens: `forest`, `gold`, `obsidian`,
`card`, `border`, `mutedForeground`. The palette matches the Flutter mobile app theme
via CSS custom properties.

## Download section

The download section auto-detects the user's platform (Android vs iOS) via user-agent and
shows the appropriate tab. Each platform has primary and secondary download options with badges.

## Customization

- **Payment methods**: edit `paymentMethods` in `data.js`
- **Features**: edit `features` in `data.js`
- **Stats**: edit `stats` in `data.js` (wire to real API endpoints when ready)
- **Download links**: update URLs in `downloadOptions` in `data.js`
- **Contact/team info**: edit `team` in `data.js`
