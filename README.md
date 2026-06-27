# Master Cut Plan — PWA Setup Guide (GitHub Pages)

This package turns your dashboard into an installable iPhone app using GitHub Pages (free hosting) + PWA features.

## What's in this folder
- `index.html` — your dashboard (now with PWA tags + service worker registration)
- `manifest.json` — tells iOS this is an "app" (name, icon, colors)
- `service-worker.js` — enables offline caching
- `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` — placeholder app icons (red dumbbell on dark background)

---

## Step 1: Create a GitHub Account (skip if you have one)
Go to https://github.com and sign up — it's free.

## Step 2: Create a New Repository
1. Click the **+** icon (top right) → **New repository**
2. Name it something like `cut-plan` (lowercase, no spaces)
3. Set it to **Public** (required for free GitHub Pages)
4. Click **Create repository**

## Step 3: Upload These Files
1. On your new repo page, click **uploading an existing file**
2. Drag in all 6 files from this folder:
   - index.html
   - manifest.json
   - service-worker.js
   - icon-192.png
   - icon-512.png
   - apple-touch-icon.png
3. Scroll down, click **Commit changes**

## Step 4: Enable GitHub Pages
1. In your repo, click **Settings** (top menu)
2. Click **Pages** (left sidebar)
3. Under "Build and deployment" → Source: select **Deploy from a branch**
4. Branch: select **main**, folder: **/ (root)**
5. Click **Save**
6. Wait ~1 minute, refresh the page — you'll see a green box with your live URL:
   `https://yourusername.github.io/cut-plan/`

## Step 5: Install on iPhone
1. Open that URL in **Safari** on your iPhone (must be Safari, not Chrome)
2. Tap the **Share** icon (square with arrow, bottom of screen)
3. Scroll down, tap **Add to Home Screen**
4. Tap **Add** (top right)
5. Done — you now have a "Cut Plan" icon on your home screen that opens fullscreen like a real app

---

## Updating the App Later
Whenever you want to change the file (new meals, workout edits, etc.):
1. Go to your GitHub repo → click `index.html`
2. Click the pencil (✏️) icon to edit, or just re-upload a new version
3. Commit the change
4. On your iPhone, force-close the app and reopen it — changes should appear within a few seconds (the service worker checks for updates on every load)

If changes don't show up: go to iPhone Settings → Safari → Clear History and Website Data (this clears the cache), then reopen the app.

## Notes
- **Your workout history is saved in `localStorage`**, which is tied to the specific URL. As long as you keep using the same GitHub Pages URL, your logged sets/reps will persist across sessions, even after closing the app.
- If you ever change your GitHub repo name or URL, you'll lose access to previously logged data (it's stored per-domain by the browser).
- The icons are placeholders (red dumbbell). If you want a custom icon later, just replace `icon-192.png`, `icon-512.png`, and `apple-touch-icon.png` with your own square images of the same dimensions and re-upload.
