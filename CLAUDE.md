# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static HTML/CSS/JS website with no build system or package manager. Development is done by editing files directly and previewing in a browser.

## Running Locally

Open any HTML file directly in a browser, or serve with a local HTTP server (required for audio to work correctly in some browsers):

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Site Structure

The site has three distinct pages with different purposes:

- **`index.html`** — The main "Bring A Plate" landing page. Since the business site got no traffic, it now hosts a browser-based breakout/pong game (`scripts/game.js`) as a placeholder. The ball uses `images/social_logo.png` as its sprite.

- **`contact_apartment.html`** — A virtual apartment intercom panel for "10 First Ave". Displays a list of apartment buttons (G01–206); clicking a bell-enabled button plays `door_chime.mp3` then redirects to `door_chime.html`. Disabled apartments show a `fa-bell-slash` icon. Uses Bootstrap 4.5 and Font Awesome (kit `e3e5df0a2c`).

- **`door_chime.html`** — The confirmation screen shown after ringing a doorbell. Allows ringing again without redirecting.

## Key Details

- No framework, bundler, or build step — pure HTML/CSS/JS.
- Bootstrap 4.5.2 and Font Awesome are loaded from CDN in `contact_apartment.html` and `door_chime.html`.
- `scripts/game.js` is a canvas-based pong game; ball resets on miss (no game-over/reload).
- `build-req/brands/specs/` directory exists but is currently empty — likely a placeholder for brand assets.
- Inline `<style>` blocks are used for page-specific CSS; there is no shared stylesheet.
