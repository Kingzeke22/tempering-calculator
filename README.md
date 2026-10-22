# Grain Tempering Calculator

A small offline-capable web app that tells you how much water to add when tempering wheat or other grain for milling.

Enter the grain weight, its current moisture and your target moisture. The app shows the water to add in grams, millilitres, pounds, ounces, fluid ounces and litres, plus a batch mass balance.

## Formula

```
Water = W1 × (M2 − M1) / (100 − M2)
```

- **W1**: starting grain weight
- **M1**: starting moisture (% wet basis)
- **M2**: target moisture (% wet basis)

The dry matter stays constant; only water is added.

## Features

- Light theme (Flour & Linen) and dark theme (Midnight Amber), with a toggle
- Works offline and installs to a phone home screen (PWA)
- Units: lbs, kg, g, oz
- Quick target buttons: 14.0, 14.5, 15.0 and 15.5%
- Copy a plain-text batch report

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app (page, styles and calculator) |
| `manifest.webmanifest` | Lets phones install it as an app |
| `sw.js` | Service worker that enables offline use |
| `icons/` | App icons (192, 512, maskable 512, Apple touch) |
| `CHANGELOG.md` | Version history |

## Hosting on GitHub Pages

1. Put all files in a public repository, keeping the `icons/` folder.
2. Go to **Settings → Pages**.
3. Set Source to **Deploy from a branch**, Branch **main**, folder **/ (root)**, then Save.
4. The app is live at `https://USERNAME.github.io/REPO-NAME/` after a minute or two.

## Installing on a phone

Open the live address once with a connection, then:

- **iPhone (Safari):** Share → Add to Home Screen
- **Android (Chrome):** menu → Install app

## Updating

1. Make your change.
2. In `sw.js`, raise `CACHE_VERSION` (for example `tempering-v2` to `tempering-v3`) so phones fetch the new files.
3. Add an entry to `CHANGELOG.md`.

No build step and no dependencies.
