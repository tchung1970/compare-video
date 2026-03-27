# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A single-file client-side video comparison tool. The entire app lives in `index.html` — HTML, CSS, and JavaScript are all inline. No build step, no dependencies, no framework.

## Development

Open `index.html` directly in a browser. No server required (uses `URL.createObjectURL` for local file handling).

## Architecture

- **Upload screen**: Drag-and-drop or file picker for two videos (A = left, B = right). Drop on a specific box or anywhere on the screen (auto-fills A then B).
- **Split view** (default): Both videos overlaid with a draggable vertical slider controlling a CSS `clip-path` to reveal left/right. Video A is clipped on top of Video B.
- **Side-by-side view**: Two independent panels separated by a divider.
- **Four `<video>` elements**: `vidA`/`vidB` for split mode, `vidA2`/`vidB2` for side-by-side mode. All four share the same object URLs and are kept in sync.
- **Sync mechanism**: `setInterval` (200ms) corrects drift between videos; Video A is the time source.
- **Zoom/Pan**: Scroll wheel for zoom (0.5x–10x), click-drag to pan when zoomed >1x. Transform applied to all four video elements.
- **Playback controls**: Space = play/pause, Left/Right arrows = ±5s seek, timeline click to seek.
