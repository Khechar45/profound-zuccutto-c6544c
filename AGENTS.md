# AGENTS.md

## Architecture

This is a plain static site: a single `index.html` at the repo root with inline `<style>` (no external CSS framework, no JS framework, no build tooling). Netlify serves it directly with no build command.

## Key directories

- `index.html` — the entire page markup and styles.
- `assets/` — resort photos (`photo_01.jpeg` … `photo_18.jpeg`) and a resort walkthrough video (`video_01.mov`).

## Conventions

- Images are referenced sequentially as `assets/photo_NN.jpeg` (zero-padded two digits). When adding/removing photos, keep the numbering contiguous and update the `<img>` list in the gallery section of `index.html` to match.
- The video is an `.mp4`/`.mov` `<source>` inside a single `<video>` element; if more videos are added, add more `<video>` blocks inside `.videos`.
- All styling is inline in the `<style>` tag in `index.html` — there is no separate CSS file to keep in sync.

## Non-obvious decisions

- The source video was uploaded as `.mov`, so its `<source>` uses `type="video/quicktime"` rather than `video/mp4`. If a broader-compatibility format is needed later, transcode to `.mp4` and update the `type` attribute accordingly.
