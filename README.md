# Noob's 8 Ball Pool

A self-contained 8-ball pool game in a single HTML file. Canvas rendering, custom
2D physics, procedural audio, and no external requests of any kind — built to be
packaged offline with Capacitor.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole game. No build step, no dependencies. |
| `privacy.html` | Privacy policy, for hosting publicly. |
| `terms.html` | Terms of use, for hosting publicly. |

## Legal

Published as **Z Sphere**, contact `itsjimlive@gmail.com`, terms governed by the
laws of Bangladesh, effective 7 September 2026.

The legal wording appears **twice** — inlined in `index.html` and again in the
standalone pages. Edit both, or they will drift apart. If a future build adds
analytics, ads, crash reporting, or saved preferences, the privacy policy stops
being accurate and must be updated before that build ships.

## Hosting the policy

Google Play requires a publicly reachable privacy policy URL for every app,
including ones that collect no data. GitHub Pages will serve these files:

1. Settings → Pages → deploy from the `main` branch, root folder.
2. Your URL becomes `https://<user>.github.io/<repo>/privacy.html`.
3. Paste that into the Play Console listing.

In the Play Console **Data safety** form, declare that no data is collected and
no data is shared. That declaration is accurate for this build — the app has no
networking code and needs no `INTERNET` permission.

## Packaging with Capacitor

```bash
npm install @capacitor/core @capacitor/cli @capacitor/android
npx cap init
# point webDir at the folder holding index.html
npx cap add android
npx cap copy
npx cap open android
```

Recommended: lock the orientation to portrait in `AndroidManifest.xml`. The
landscape layout is a fallback rather than a designed mode.

## Rules note

Pocketing the 8 on the same stroke as your last group ball is scored as a
**loss**, following WPA rules. Many bar rules score it as a win. See the
`resolveShot` function to change it.
