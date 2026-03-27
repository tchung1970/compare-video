# Compare Video

A client-side video comparison tool. Drop two videos and compare them frame-by-frame using a split slider or side-by-side view — all in the browser, no uploads, no server.

## Live Demo

https://ai.tchung.org/compare-video/

## Features

- **Split view** — draggable vertical slider reveals left/right video with a CSS clip-path overlay
- **Side-by-side view** — two independent panels for simultaneous playback
- **Synced playback** — videos stay in sync with automatic drift correction (200ms interval)
- **Zoom & pan** — scroll to zoom or click the badge to cycle 100%/200%/300%, click-drag to pan when zoomed in
- **Keyboard shortcuts** — Space (play/pause), Left/Right arrows (±5s seek)
- **Drag and drop** — drop files on specific boxes or anywhere on the upload screen
- **Fully local** — uses `URL.createObjectURL`, nothing leaves your machine

## Usage

Open `index.html` in a browser. No build step, no dependencies, no server required.

1. Drop or select two video files (A = left, B = right)
2. Click **Compare**
3. Use the split slider or switch to side-by-side view
4. Scroll to zoom, drag to pan, use keyboard shortcuts for playback

## Architecture

Single-file app — HTML, CSS, and JavaScript are all inline in `index.html`.

Four `<video>` elements are used: `vidA`/`vidB` for split mode and `vidA2`/`vidB2` for side-by-side mode. All share the same object URLs and are kept in sync with Video A as the time source.

## License

MIT
