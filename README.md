# PreMock

**Present Figma & AI prototypes beautifully.**

PreMock drops your prototype into a realistic hand‑held phone mockup and turns it into an interactive, live presentation. Paste a Figma link or upload an AI‑generated HTML prototype, pick a backdrop, and present — or record the whole thing as a video.

🔗 **Live:** [premock.co](https://www.premock.co/)

---

## Features

- **Two prototype sources**
  - **Figma** — paste a prototype share link; it's embedded right in the phone.
  - **HTML** — drag & drop a file, click **Upload HTML**, or paste raw markup into the gallery.
- **Realistic device mockup** — a hand holding the phone, with an **iOS / Android** toggle.
- **Custom cursor** — a soft dot replaces the system cursor over the screen for a clean, touch‑like feel.
- **Backdrops** — three built‑in scenes (Soft Gray, Apricot, Sky Blue), a full **color palette** with hex input and a random‑color dice, or your own **background image**.
- **iPhone status bar overlay** — toggle a status bar on top of the screen.
- **Prototype gallery** — save, rename, reorder and remove prototypes; persisted in the browser (`localStorage`). Figma titles are fetched automatically via oEmbed.
- **Presentation mode** — go fullscreen; the UI fades away while you present.
- **Screen recording** — capture the presentation with `MediaRecorder` and download a `.webm`. Optional **microphone audio** via a checkbox in the record tooltip.
- **Shareable links** — for Figma prototypes, copy a link that reproduces the prototype, device, backdrop and status‑bar state on open.
- **Dark‑mode aware favicon.**

## Tech

No build step, no dependencies — just **vanilla HTML, CSS and JavaScript**.

| File | Purpose |
|------|---------|
| [`index.html`](index.html) | Markup + Google Analytics + favicon |
| [`styles.css`](styles.css) | All styling |
| [`app.js`](app.js) | All behavior (device fitting, cursor, gallery, scenes, recording, sharing) |
| `hand-ios.png` / `hand-and.png` | Device mockup images (transparent screen cutout) |
| `Status Bar.png`, `home.png` | Status‑bar overlay and a sample background |
| `CNAME` | GitHub Pages custom domain (`premock.co`) |

Hosted on **GitHub Pages**.

## Run locally

It's a static site, so any static server works:

```bash
# from the project root
python3 -m http.server 8080
# then open http://localhost:8080
```

> Opening `index.html` directly via `file://` mostly works, but a local server avoids browser restrictions around iframes and the clipboard.

## Usage

1. Open the app. The phone slides into view.
2. **Add a prototype:**
   - Click **Upload HTML** (or drag a `.html` file anywhere), **or**
   - Open the **Gallery**, paste a Figma share link or HTML, and press **Add**.
3. Pick a **backdrop** from the bottom‑left dock (scenes, palette or your own image).
4. Switch **iOS / Android** and toggle the **status bar** from the bottom‑right.
5. Press **Full Screen** to present, or **Record** to capture a clip (tick *Record microphone audio* first if you want voice‑over).
6. For Figma prototypes, use the **share** button to copy a link that restores the full setup.

### Figma prototype tips

For a Figma link to display correctly, in Figma:

- Set sharing to **“Anyone with the link → can view.”**
- In prototype settings, set **Device → None** (PreMock adds the frame).
- Set **Scaling → “Scale down to fit width.”**
- Choose the correct **starting frame**.
- In Present mode, enable **“Hide Figma UI”** (the link will include `hide-ui=1`).

The in‑app guide (Gallery → *Follow the guide*) walks through the same steps.

## Browser support

Modern Chromium browsers, Firefox and Safari. Screen recording requires a browser that supports `getDisplayMedia` + `MediaRecorder` (e.g. Chrome).

## Credit

Designed and built by [Arda Arıcan](https://www.thisisarda.com).
