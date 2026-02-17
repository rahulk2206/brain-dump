# Brain Dump – Add to Home Screen on iPhone

This is a single-page web app that works on iPhone and can be saved to your home screen.

## How to use on iPhone

1. **Serve the app over HTTP**  
   Your iPhone needs to open the app via a URL (e.g. `http://your-computer-ip:8000`), not as a local file.

2. **On your Mac (same Wi‑Fi as iPhone):**
   ```bash
   cd /Users/rahul/Desktop/brain-dump
   python3 -m http.server 8000
   ```
   Then on your iPhone, in Safari, go to: `http://YOUR_MAC_IP:8000`  
   (Find your Mac’s IP: System Settings → Network → Wi‑Fi → Details, or run `ipconfig getifaddr en0` in Terminal.)

3. **Add to Home Screen**  
   In Safari on iPhone: tap the Share button (square with arrow) → **Add to Home Screen** → name it (e.g. “Brain Dump”) → Add.

4. **Open like an app**  
   Tap the new icon on your home screen. It will open in full-screen (no Safari UI). Your notes are stored in the browser on the device.

## Optional: custom icon

To use your own icon instead of a screenshot:

- Add `icon-192.png` (192×192) and optionally `icon-512.png` (512×512) in this folder.
- Uncomment or add in `index.html` inside `<head>`:
  ```html
  <link rel="apple-touch-icon" href="icon-192.png">
  ```

## Deploying online (optional)

To use it from anywhere (not just your home network), upload this folder to any static host (e.g. GitHub Pages, Netlify, or your own server) over HTTPS. Then open that URL on your iPhone in Safari and use **Add to Home Screen** as above.

---

## Publish on App Store & Google Play

This project is set up with **Capacitor** so you can build native iOS and Android apps and publish them on the **Apple App Store** and **Google Play Store**.

**👉 See [PUBLISHING_GUIDE.md](PUBLISHING_GUIDE.md) for full step-by-step instructions** (developer accounts, Xcode, Android Studio, signing, store listings, and submission).

**Quick start for native builds:**

```bash
npm install
npx cap add ios
npx cap add android
npx cap sync
npx cap open ios      # build & submit from Xcode
npx cap open android  # build & submit from Android Studio
```

The app that gets packaged is in the **`www`** folder. After changing `www/index.html` or other files, run `npx cap sync` before building again.
