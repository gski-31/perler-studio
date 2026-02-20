# Perler Bead Studio — PWA

Convert any JPG/PNG into a printable multi-page Perler bead pattern PDF.
Installable on any device. Works fully offline once loaded.

---

## Files

```
perler-pwa/
├── index.html      ← The full app
├── manifest.json   ← PWA config (name, icons, colors)
├── sw.js           ← Service worker (offline caching)
├── icon-192.svg    ← App icon (home screen)
├── icon-512.svg    ← App icon (splash screen)
└── README.md       ← This file
```

---

## Hosting Options

### Option A — GitHub Pages (free, easiest)

1. Create a free account at https://github.com
2. Click **New Repository** → name it `perler-studio` → set to **Public**
3. Upload all 5 files (drag them into the GitHub file browser)
4. Go to **Settings → Pages → Source → Deploy from branch → main**
5. Your app URL will be: `https://YOUR-USERNAME.github.io/perler-studio`

### Option B — Netlify (free, instant)

1. Go to https://netlify.com → sign up free
2. Drag the entire `perler-pwa` **folder** onto the Netlify dashboard
3. Done — you get a URL like `https://random-name.netlify.app`
4. Optional: set a custom domain in Netlify settings

### Option C — Vercel (free)

1. Go to https://vercel.com → sign up free
2. Install Vercel CLI: `npm i -g vercel`
3. In the `perler-pwa` folder, run: `vercel`
4. Follow prompts — app is live in ~30 seconds

---

## Installing as an App

### On Android (Chrome)
1. Visit your hosted URL in Chrome
2. Tap the **⋮ menu → Add to Home screen**
3. Or wait for the "Install App" button that appears in the header

### On iPhone/iPad (Safari)
1. Visit your hosted URL in Safari
2. Tap the **Share button (□↑) → Add to Home Screen**
3. Tap **Add** — it appears on your home screen like a real app

### On Desktop (Chrome/Edge)
1. Visit your hosted URL
2. Click the **install icon (⊕)** in the address bar
3. Or click **Install App** in the app header

---

## Running Locally (for testing)

PWAs require HTTPS or localhost — you can't just open index.html directly.

```bash
# Python (built-in)
cd perler-pwa
python3 -m http.server 8080
# Then open http://localhost:8080

# Node.js
npx serve perler-pwa
# Then open the URL it gives you
```

---

## Updating the App

After making changes, bump the cache version in `sw.js`:
```js
const CACHE_NAME = 'perler-studio-v2';  // increment this
```
This forces all installed apps to pick up the new version.
