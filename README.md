# Multiwave Analyzer

A browser-based audio visualizer with MP4 export. No installation, no backend — one HTML file.

![Multiwave Analyzer](icons/icon-512.png)

## Features

- **4 visualization modes** — Waveform, Spectrum, Circular, Phase scope (combinable)
- **Solar flares** — particle effects that react to audio peaks
- **Per-mode parameters** — amp, glow, intensity, gravity, fade per mode
- **Dual LFO** — modulate any parameter with 6 waveform shapes, BPM sync
- **3-color gradient** with LFO-modulatable blend
- **Graticule** — CRT-style grid overlay
- **Image import** — blend a photo behind or in front of the visualization
- **Export formats** — 16:9, 4:5 (Instagram feed), 9:16 (Stories/Reels)
- **Direct MP4 export** — no conversion needed (file mode)
- **Live recording** — microphone, system audio, or both
- **Audio fade in/out**, trim scrubber, BPM detection
- **PWA** — installable on Mac, iPhone, Android

---

## Install as app

### Mac (Chrome)
1. Open the GitHub Pages URL in Chrome
2. Click the **⊕** icon in the address bar (right side)
3. Click **Install app**
4. App appears in your Applications folder and Dock

### iPhone / iPad (Safari)
1. Open the URL in Safari
2. Tap the **Share** button (box with arrow)
3. Tap **Add to Home Screen**
4. Tap **Add**

### Android (Chrome)
1. Open the URL in Chrome
2. Tap the **⋮** menu → **Add to home screen**
3. Tap **Install**

---

## Usage

### File mode (recommended for DJ sets)
1. Select **Bestand** in the Bron section
2. Drop your audio file (AIFF, WAV, MP3, FLAC, OGG, M4A)
3. Set trim points if needed
4. Choose format (16:9 / 4:5 / 9:16)
5. Click **● Record** — exports directly to MP4

### Live mode (mic / system audio)
1. Select **Microfoon**, **Systeem**, or **Beide**
2. Click **● Record**
3. Grant browser permission when asked
4. Click **■ Stop** when done — exports as WebM

**Note for system audio on Mac:** Chrome only captures tab audio, not system-wide audio. For recording your DAW or mixer, use **Microfoon** and route your audio interface into your computer.

**Note for Android:** Use **Microfoon** with a USB-C audio interface connected to your mixer's booth output for best quality.

---

## Create your GitHub Pages app

### Step 1 — Create a GitHub account
Go to [github.com](https://github.com) and sign up if you don't have an account.

### Step 2 — Create a new repository
1. Go to [github.com/new](https://github.com/new)
2. Repository name: `multiwave-analyzer` (or any name you like)
3. Set to **Public**
4. Leave everything else as default
5. Click **Create repository**

### Step 3 — Upload the files
1. In your new repository, click **Add file → Upload files**
2. Upload these files maintaining the folder structure:

```
multiwave-analyzer/
├── index.html
├── manifest.json
├── sw.js
└── icons/
    ├── icon-192.png
    ├── icon-512.png
    └── icon-apple.png
```

**To upload the icons folder:**
- Drag the entire `icons` folder into the upload area
- GitHub will automatically create the folder

3. At the bottom, click **Commit changes**

### Step 4 — Enable GitHub Pages
1. Go to your repository **Settings** (top menu)
2. In the left sidebar, click **Pages**
3. Under **Source**, select **Deploy from a branch**
4. Under **Branch**, select `main` and `/ (root)`
5. Click **Save**

### Step 5 — Wait ~1 minute
GitHub builds the site. You'll see a green checkmark and your URL:

```
https://your-username.github.io/multiwave-analyzer
```

This is the URL you share or install as an app.

### Step 6 — Install as PWA (optional)
Open the URL from Step 5 in Chrome (Mac) or Safari (iPhone) and follow the install instructions above.

---

## Updating the app

When you make changes to `index.html`:
1. Go to your repository on GitHub
2. Click on `index.html`
3. Click the **pencil icon** (Edit)
4. Make changes or click **...** → **Upload file** to replace it
5. Click **Commit changes**

The live app updates within ~1 minute.

---

## Browser requirements

| Feature | Browser |
|---------|---------|
| Full app | Chrome 94+ |
| MP4 export | Chrome 94+ (WebCodecs) |
| Live recording | Chrome, Firefox, Safari |
| PWA install | Chrome (Mac/Android), Safari (iOS) |

---

## Technical notes

- **No server required** — pure client-side HTML/CSS/JS
- **AIFF support** — custom parser, no native browser decoding needed
- **Offline capable** — service worker caches all assets after first load
- **MP4 export** uses WebCodecs API + mp4-muxer for H.264/AAC encoding
- **Live recording** uses MediaRecorder API → WebM output

---

## License

MIT — use freely, modify freely.
