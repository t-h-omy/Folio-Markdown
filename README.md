# Folio — Markdown Editor

A distraction-free PWA markdown editor with split-pane live preview and easy chapter copying from contents mode.

## Files
- `index.html` — Main app (self-contained)
- `manifest.json` — PWA manifest
- `sw.js` — Service worker (offline support)

## Setup

### Local use (simplest)
Just open `index.html` in any modern browser. All features work except PWA install and service worker (requires HTTPS or localhost).

### Full PWA (installable + offline)
Serve the folder over HTTPS or localhost:

```bash
# Python
python3 -m http.server 8080

# Node.js
npx serve .

# VS Code
Use the "Live Server" extension
```

Then visit `http://localhost:8080` — you'll see an install prompt in the browser's address bar.

## Features
- **Open** `.md`, `.markdown`, `.txt` files via File System Access API (or classic `<input>`)
- **Save** back to the original file in-place (where supported) or download
- **Split / Edit / Preview** view modes with draggable divider
- **Contents mode chapter copy**: copy full chapters without selecting individual lines
- **Drag & drop** `.md` files onto the window
- **Keyboard shortcuts**: `Ctrl+S` save, `Ctrl+O` open, `Ctrl+N` new
- **Live stats**: word count, character count, line count, cursor position
- **Offline capable** via service worker
- **Installable** as a desktop/mobile app

## Browser compatibility
- Chrome / Edge 86+ — full File System Access API (save in place)
- Firefox / Safari — fallback download for save, everything else works
