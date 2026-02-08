# قارئ القرآن الكريم - PWA Deployment Guide

## What You Have

A complete Progressive Web App (PWA) that auto-prompts users to install it when they visit your URL — no app store needed. Works on **every platform**: Android, iOS, Windows, macOS, Linux.

### Files:
```
quran-pwa/
├── index.html          ← Your app (with PWA capabilities added)
├── manifest.json       ← App metadata (name, icons, theme)
├── sw.js               ← Service worker (offline caching)
├── icons/
│   ├── icon-72.png
│   ├── icon-96.png
│   ├── icon-128.png
│   ├── icon-144.png
│   ├── icon-152.png
│   ├── icon-180.png    ← Apple touch icon
│   ├── icon-192.png
│   ├── icon-384.png
│   └── icon-512.png
└── README.md
```

---

## How to Deploy (Free Options)

### Option 1: GitHub Pages (Recommended — Free)

1. Create a GitHub account at github.com
2. Create a new repository (e.g., `quran-reader`)
3. Upload ALL files from this folder to the repository
4. Go to **Settings → Pages → Source** → select "main" branch
5. Your app will be live at: `https://yourusername.github.io/quran-reader/`

### Option 2: Cloudflare Pages (Free, Fastest)

1. Sign up at pages.cloudflare.com
2. Create new project → Upload assets
3. Drag and drop the entire `quran-pwa` folder
4. Done! Free custom domain support included.

### Option 3: Netlify (Free)

1. Go to app.netlify.com
2. Drag and drop the `quran-pwa` folder onto the page
3. Instant deploy with a free URL

### Option 4: Vercel (Free)

1. Go to vercel.com
2. Import your GitHub repo or drag & drop files
3. Instant deploy

---

## What Happens for Users

### On Android (Chrome / Samsung Internet / Edge):
- User visits your URL
- After ~2 seconds, a golden install banner appears at the bottom
- They tap **"Install"** → native install dialog appears
- App appears on their home screen with the golden crescent icon
- Opens in standalone mode (no browser chrome — looks like a native app)

### On iOS (Safari):
- User visits your URL
- Install banner appears with **"Install"** button
- Tapping it shows step-by-step instructions:
  1. Tap the Share button
  2. Scroll and tap "Add to Home Screen"
  3. Tap "Add"
- App appears on home screen with the icon

### On Desktop (Chrome / Edge):
- Install icon appears in the address bar
- Or they'll see the banner prompt
- App installs as a standalone window

---

## Features Added

- ✅ **Auto-install prompt** — non-intrusive banner after 2 seconds
- ✅ **iOS instructions** — step-by-step modal for Safari users
- ✅ **Offline support** — previously loaded surahs work without internet
- ✅ **Smart caching** — fonts, Quran API data, and app shell cached
- ✅ **Offline indicator** — bar shows when connection is lost
- ✅ **No nagging** — if dismissed, won't show again for 7 days
- ✅ **Bilingual** — install prompts in Arabic or English based on user's choice
- ✅ **App icons** — beautiful Islamic geometric design at all required sizes
- ✅ **Zero tracking** — no analytics, no cookies beyond localStorage bookmarks

---

## Custom Domain (Optional)

For a professional URL like `quran.yourdomain.com`:
1. Buy a domain (Namecheap, Google Domains, etc.)
2. Point DNS to your hosting (GitHub Pages, Cloudflare, etc.)
3. Enable HTTPS (required for PWA — all free hosts provide this)

**⚠️ Important: PWAs require HTTPS to work. All recommended hosts above provide free SSL.**

---

## Updating the App

When you update `index.html` or any files:
1. Push changes to your host
2. Update the `CACHE_NAME` in `sw.js` (e.g., change `'quran-reader-v1'` to `'quran-reader-v2'`)
3. The service worker will automatically refresh cached files for all users

---

بارك الله فيك 🌙
