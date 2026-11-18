# CGL Mock Tracker — installable offline PWA

## What this package does
- Preserves the uploaded 53-shift tracker and its filters, notes, and completion ticks.
- Removes the external Google Fonts dependency.
- Adds a web app manifest and service worker for offline caching.
- Keeps progress in the browser's local storage on the installed app's origin.

## Important: local HTML files cannot install as a PWA
Do not open `index.html` from Android File Manager and expect the Install App option.
A service worker requires HTTPS (or localhost). Upload the *contents* of this folder to an HTTPS static host.

## Install on Android
1. Upload this folder's contents to an HTTPS static host (for example, a static-site host).
2. Open the resulting `https://...` address in Chrome.
3. Wait for the page to finish loading while online.
4. Open Chrome's menu and choose **Install app** or **Add to Home screen**.
5. Open the installed app once while online. Then test it in airplane mode.

## Data notes
- Ticks and notes are stored locally in that browser/app installation.
- Clearing site data or uninstalling the app can erase that local progress. Export/backup is not currently built in.
- This tracker does not contain the 53 question papers; it tracks completion and notes only.
- Any optional account sync from the original environment is not available on a normal static host. Local saving remains available.

## Updating
When the app files change, increment `CACHE_NAME` in `sw.js` so installed copies fetch the new version.
