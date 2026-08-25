# Wildwood Crow Tracker

A personal checklist PWA for spotting all 30 crow sculptures on Portland's
*Wildwood: Follow the Crows* art trail (Aug 7 – Nov 1, 2026).

This folder is a complete, ready-to-host static site. It's a true installable
PWA: offline-capable via a service worker, with a real app icon and manifest.

## Files

- `index.html` — the app
- `manifest.json` — web app manifest (name, icons, standalone display)
- `sw.js` — service worker (offline caching + auto-update on reconnect)
- `icon-192.png`, `icon-512.png` — app icons (Android/Chrome)
- `icon-180.png` — apple-touch-icon (iOS home screen)

## Hosting it on GitHub Pages (free)

1. Create a new **public** repo under your own GitHub account (e.g. `wildwood-crow-tracker`).
2. Upload all the files in this folder to the repo root — either drag-and-drop
   in the GitHub web UI ("Add file" → "Upload files"), or via git:
   ```
   git init
   git add .
   git commit -m "Wildwood crow tracker"
   git branch -M main
   git remote add origin https://github.com/<your-username>/wildwood-crow-tracker.git
   git push -u origin main
   ```
3. In the repo, go to **Settings → Pages**. Under "Build and deployment",
   set Source to **Deploy from a branch**, branch **main**, folder **/(root)**. Save.
4. Wait about a minute, then visit `https://<your-username>.github.io/wildwood-crow-tracker/`.
5. Open that URL on your phone and use **Add to Home Screen**. It'll now install
   as a real offline-capable app — icon, standalone window, and it works with
   no signal once you've opened it at least once while online.

## Updating it later

Push new commits to `main` (or re-upload changed files) — GitHub Pages
redeploys automatically within a minute or two. The service worker fetches
fresh content whenever you have a connection and falls back to the cached
version when you don't, so you won't get stuck on a stale copy.

## Heads up: photos won't carry over

Your progress and photos in the old `claude.ai` artifact version are stored
in that page's local browser storage, tied to that specific URL. This is a
different URL (a different origin), so it starts with a clean slate — you'll
need to re-photograph any crows you already collected there, or ask for an
export/import feature to move them over.
