# Fidelity Bank Ghana — Mobile Banking Prototype

A high-fidelity, single-file prototype of the Fidelity Bank Ghana mobile app, featuring **Kukua**, an AI banking assistant with both chat and voice ("tap to speak"), a premium animated UI, an anniversary welcome flow, and the **"20 Years · 20 Schools"** Orange Impact giving feature.

Everything — markup, styles, scripts, fonts, and images — is embedded in one `index.html`, so there are no build steps and no dependencies. It is also a fully **installable PWA**: once hosted over HTTPS it can be added to the home screen, launches standalone, and works offline.

---

## Quick start

**View it instantly:** open `index.html` in a desktop browser to click through the full flow.

**For the real experience (and working voice), host it over HTTPS** — see the GitHub Pages steps below. The microphone will *not* work from a local `file://` path; it needs a secure (https) origin.

---

## Deploy to GitHub Pages

1. Create a new repository on GitHub (e.g. `fidelity-kukua-app`).
2. Upload the contents of this folder (`index.html` and `README.md`) to the repository root — either via the GitHub web uploader or with git:
   ```bash
   git init
   git add .
   git commit -m "Fidelity Kukua banking prototype"
   git branch -M main
   git remote add origin https://github.com/<your-username>/fidelity-kukua-app.git
   git push -u origin main
   ```
3. In the repository, go to **Settings → Pages**.
4. Under **Build and deployment**, set **Source** to *Deploy from a branch*, choose branch **main** and folder **/ (root)**, then **Save**.
5. Wait ~1 minute. Your live HTTPS link will appear at the top of the Pages settings, e.g.:
   `https://<your-username>.github.io/fidelity-kukua-app/`

Open that link on your phone in **Chrome (Android)** or **Safari (iOS)** to run the demo.

---

## Using the demo

- The app opens at onboarding → **Account Holder** → **Welcome to the Orange Life** → Login (any password works) → Home.
- **Kukua** is reachable from the floating mic button on Home. Tap the keyboard icon to switch to typed chat; tap the mic icon to switch back to voice.
- The **mic-readiness chip** on the voice screen tells you at a glance whether "tap to speak" will work in your current setup.
- **Orange Impact** ("20 Years · 20 Schools") is the banner on the Home screen — round-up toggle, one-time gifts, and donating O'Spin points.

## Important notes for the demo

**Voice ("tap to speak")** needs all of: a supported browser (Chrome or Safari), an **HTTPS** origin (GitHub Pages provides this), microphone permission, and an internet connection. It will not work from a local file or inside an in-app/preview browser.

**Kukua's understanding:** on a static host like GitHub Pages, Kukua uses an offline keyword engine, which still handles all the demo commands ("what's my balance", "send 200 to Ama", "buy 10 airtime", "show my transactions"). Her full conversational AI requires a backend that proxies an LLM — never put an API key in this static file.

**Kukua's voice** is set to Ghanaian English (en-GH). Most phones don't ship an en-GH voice, so she'll fall back to the closest available voice and the screen will note this.

**Support number** used throughout the app is **0800 00 3355**.

---

## Project structure

```
fidelity-kukua-app/
├── index.html        # the entire app (self-contained)
├── manifest.json     # PWA web app manifest
├── sw.js             # service worker (offline caching)
├── icons/            # app icons (192, 512, maskable, apple-touch)
├── screenshots/      # install-prompt screenshots
└── README.md
```

---

*This is a design/UX prototype, not a production banking client. It performs no real transactions and connects to no real banking systems.*
