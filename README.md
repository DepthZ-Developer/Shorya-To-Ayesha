# Aysha Birthday Gift — Chitthi.io

A hardcoded, personal, interactive birthday gift site for **Aysha** from **Shorya (Ganda Baccha)**.  
11-screen journey: invitation → smile check → gift unwrap → scratch card → shayari → polaroid wall → hidden lights → hold-to-hug → typewriter letter → vouchers → certificate.

---

## Live Preview

Deploy on **GitHub Pages** (free, instant):

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Source: `main` branch, `/ (root)` folder
4. Save — your site is live at `https://<your-username>.github.io/<repo-name>/`

Share that link with Aysha on her birthday. Done.

---

## Adding Photos (Polaroid Wall)

When Shorya sends you the photos:

1. Resize each to **600 × 600 px**, save as JPG (quality 80 is fine).
2. Name them **exactly**:
   ```
   photo-1.jpg
   photo-2.jpg
   photo-3.jpg
   photo-4.jpg
   photo-5.jpg
   photo-6.jpg
   ```
3. Drop them into **`assets/images/`**
4. Commit & push — the polaroid wall auto-loads them.

> If any photo is missing, that polaroid shows an emoji placeholder instead. No crash, no code change needed.

You can also update the captions in `index.html` — search for `const FRAMES=` and edit each `cap:` value.

---

## Adding the Song (Banjare Ka Bairan)

1. Get the MP3:
   ```bash
   # Using yt-dlp (install with: pip install yt-dlp)
   yt-dlp -x --audio-format mp3 -o "bairan.%(ext)s" <YouTube-URL>
   ```
   Or use any MP3 converter — just keep it under ~8 MB for fast loading.

2. Rename the file to exactly **`bairan.mp3`**

3. Drop it into **`assets/audio/`**

4. Commit & push.

> Without the file the site still works — it plays melodic Web Audio beeps instead. No error shown to Aysha.

---

## Customising Captions / Text

Open `index.html` and search for these markers:

| What to change | Search for |
|---|---|
| Polaroid captions | `const FRAMES=` |
| Shayaris (3 cards) | `const SHAYARIS=` |
| Hidden lights notes | `const NOTES=` |
| Typewriter letter | `const LETTER=` |
| Birthday vouchers | `const VOUCH=` |
| Aysha's name / Shorya's name | Search `Aysha`, `Shorya`, `Ganda Baccha` |

---

## File Structure

```
aysha-gift-repo/
├── index.html              ← The entire gift (one self-contained file)
├── assets/
│   ├── images/
│   │   ├── .gitkeep        ← placeholder; drop photo-1.jpg … photo-6.jpg here
│   │   └── photo-1.jpg     ← (add when Shorya sends photos)
│   └── audio/
│       ├── .gitkeep        ← placeholder; drop bairan.mp3 here
│       └── bairan.mp3      ← (add when you have the file)
├── screenshots/            ← App Store preview PNGs (for marketing)
│   ├── 01-invitation.png
│   ├── 02-gift-unwrap.png
│   ├── 03-shayari.png
│   └── 04-letter-cert.png
├── .gitignore
└── README.md
```

---

## Tech

- Vanilla HTML/CSS/JS — zero dependencies, zero build step
- Web Audio API for sound effects + beep fallback music
- HTML5 `<audio>` for the real song (bairan.mp3)
- Canvas API for the scratch card
- CSS spring animations (cubic-bezier) throughout
- Works on mobile (iOS Safari, Chrome Android) — tested

---

## Made with Chitthi.io
