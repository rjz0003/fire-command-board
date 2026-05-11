# Fire Command Board — PWA

A Progressive Web App (PWA) for fire scene incident command. Works fully offline once installed. Optimized for iPad and large tablets in landscape mode.

## Features

- Unit roster with drag & drop to sectors
- Structure fire building diagram (floors, attic, roof, basement)
- Dynamic layouts for Vehicle Fire, Wildland, HazMat, Medical, MVA
- MAYDAY and 10-minute report checklists
- SCBA and sector timers
- Incident history with unit movement log
- Whiteboard for scene sketching
- New York and Durham unit badge styles
- Fully offline — no internet required after first load

---

## Deploy to GitHub Pages (free hosting)

### Step 1 — Create a GitHub repository

1. Go to [github.com](https://github.com) and sign in (create a free account if needed)
2. Click **New repository**
3. Name it: `fire-command-board` (or anything you like)
4. Set to **Public**
5. Click **Create repository**

### Step 2 — Upload the files

**Option A — Upload via GitHub web interface (easiest):**
1. In your new repo, click **Add file → Upload files**
2. Drag the entire contents of this folder into the upload area:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icons/` folder (all 4 PNG files)
   - `.github/workflows/deploy.yml`
3. Click **Commit changes**

**Option B — Via Git command line:**
```bash
git init
git add .
git commit -m "Initial deploy"
git remote add origin https://github.com/YOUR_USERNAME/fire-command-board.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages

1. In your repo, go to **Settings → Pages**
2. Under **Source**, select **GitHub Actions**
3. Click **Save**

The GitHub Action will run automatically and deploy your app. It takes about 60 seconds.

### Step 4 — Your app URL

Your app will be live at:
```
https://YOUR_USERNAME.github.io/fire-command-board/
```

Replace `YOUR_USERNAME` with your actual GitHub username.

---

## Install as an App on iPad

1. Open the URL above in **Safari** on your iPad
2. Tap the **Share button** (box with arrow)
3. Tap **Add to Home Screen**
4. Tap **Add**

The app will now appear on your home screen and launch fullscreen with no browser UI. It works completely offline after the first load.

---

## Updating the app

When you get an updated `index.html`:
1. Upload the new file to your GitHub repo (replacing the old one)
2. The GitHub Action deploys it automatically in ~60 seconds
3. On the iPad, pull down to refresh once — the service worker will cache the new version
4. All incident data saved in the app is preserved between updates

---

## File structure

```
fire-command-board/
├── index.html              ← The entire app (single file)
├── manifest.json           ← PWA config (name, icons, display mode)
├── sw.js                   ← Service worker (offline caching)
├── icons/
│   ├── icon-192.png        ← Home screen icon (Android/Chrome)
│   ├── icon-512.png        ← Splash screen icon
│   ├── apple-touch-icon.png ← Home screen icon (iPad/iPhone)
│   └── favicon-32.png      ← Browser tab icon
└── .github/
    └── workflows/
        └── deploy.yml      ← Auto-deploy to GitHub Pages
```
