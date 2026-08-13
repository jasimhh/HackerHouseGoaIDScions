# Builder Pass — Hacker House Goa 2026

A fast web tool: upload a photo, add your details → instantly mint your **Hacker House Goa 2026
Boarding Pass** → download it and share to X with **#FrameInGoa**.

Built as a single self-contained `index.html` (no build step, no backend).

## The Boarding Pass
A landscape, ID-card-proportioned (1500×946) airline-style boarding pass:
- Left‑aligned **HACKERHOUSE गोवा AIR** wordmark, big **PUN → GOA** route with city names.
- **PASSENGER** name, plus **FLIGHT · SEAT · BOARDING · CLASS** and **DATE · TEAM** fields.
- An authentic rotated **“NOW BOARDING”** ink stamp (gate · seq · zone).
- Tear‑off **stub** with the passenger photo, a scannable **QR → the builder’s X**, a barcode and wallet id.
- Subtle Goa art (sun · palms) and the real HH Goa floral borders.

## Passport‑photo background removal
Tick **“Passport photo”** on upload and the tool removes the (plain/light) background in‑browser
— edge flood‑fill chroma key + auto‑crop — and fits the subject cleanly into the photo frames.
Works fully client‑side; no upload to any server.

## Features
- **Speed** — everything renders client‑side on `<canvas>`; result is near‑instant.
- **Real photos** — any aspect ratio / off‑center crop; JPG · PNG · WEBP · **HEIC** (iPhone). Drag to reposition, slider to zoom.
- **Editable fields** — name, role (type or pick), team, from‑city, X handle.
- **Downloadable** — exports a real high‑res PNG.
- **Share to X** — `navigator.share()` attaches the image directly on mobile; desktop falls back
  to downloading the PNG + opening the X composer with a pre‑filled caption and `#FrameInGoa`.
- **Link preview** — `og.png` is set as the Open Graph / Twitter card image.
- **Mobile‑friendly** — responsive, camera capture on phones.

Typography: **Bodoni Moda** (Didone display, with the logo’s drop‑shadow) + **Space Mono**, plus
**Baloo 2** for the outlined गोवा (yellow letters with a magenta letter‑shaped outline).

## Files (all needed for deploy)
- `index.html` — the whole app (fonts load from Google Fonts CDN).
- `og.png` — social / link‑preview image referenced by the meta tags.
- `border-fancy.png`, `border-simple.png` — the HH Goa border art used on the page strips and the pass.

## Deploy (get your live link)
Any static host works.

**Netlify Drop**
1. Go to https://app.netlify.com/drop
2. Drag this whole `ID GOA` folder onto the page.
3. You get a live `https://…netlify.app` link — that’s your submission link.

**Vercel**
```bash
npm i -g vercel
vercel --prod
```

**GitHub Pages** — push the files to a repo, then Settings → Pages → deploy from `main` (root).

> After deploying, update the `og:image` / `twitter:image` meta tags to the full deployed URL of
> `og.png` (e.g. `https://yoursite.netlify.app/og.png`) so the X link preview resolves.

## Local preview
```bash
python -m http.server 8731
# open http://localhost:8731/index.html
```

---
Team **SCION** · Built by Jasim S · Chandra Sekarayyan · Ajin Joseph
Made for Hacker House Goa 2026 · #FrameInGoa
