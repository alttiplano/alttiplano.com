# Favicons

All favicon assets and their manifest live in `public/favicons/`. The shared
`src/layouts/Layout.astro` connects them on every page.

| File | Dimensions | Use |
| --- | --- | --- |
| `favicon.svg` | Scalable, square viewBox | Modern browser tabs and bookmarks |
| `favicon.ico` | 16×16, 32×32, 48×48 embedded | Browser fallback |
| `favicon-96x96.png` | 96×96 px | PNG browser fallback |
| `apple-touch-icon.png` | 180×180 px | Apple home-screen icon |
| `android-chrome-192x192.png` | 192×192 px | Android shortcut icon |
| `android-chrome-512x512.png` | 512×512 px | Higher-resolution shortcut icon |
| `site.webmanifest` | JSON | Declares Android icons and site identity |

The logo source is `src/assets/icons/logos/mark.svg`, the vector version of the
supplied JPG symbol. Each size is rendered directly from this vector; the JPG
and the previous 32 px ICO are not enlarged. The symbol remains black on an
opaque `#f0f0f0` background, matching the supplied reference and keeping it
visible against light and dark browser chrome. Its aspect ratio is preserved.

The browser icons use a 1400×1400 canvas around the 1064×750 symbol (76% width).
The Apple and Android icons use a 1600×1600 canvas (66.5% width), leaving more
space for the home-screen presentation. Backgrounds are square; devices apply
their own corner treatment. Android icons declare `purpose: any`, not
`maskable`.

`public/favicon.ico` is an identical compatibility copy for clients that request
`/favicon.ico` automatically. Update it together with the organized copy when
changing the brand. The manifest keeps normal browser navigation; this favicon
setup does not implement offline support or an app installation flow.

References: [browser icon selection](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Attributes/rel#icon),
[Apple home-screen icons](https://developer.apple.com/library/archive/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html),
and [manifest icons](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Manifest/Reference/icons).
