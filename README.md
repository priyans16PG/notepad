# Smart URL Notepad

A lightweight single-page notepad that saves your note in the URL hash.

## Features

- Full-page editor with instant typing
- Share notes directly by sharing the URL
- LZ-String compression for small notes
- AES-GCM encryption for longer notes
- Auto-save every 500ms when content changes

## How It Works

- On load, the app reads the note from `location.hash`.
- If the hash starts with `e`, the note is treated as encrypted and decrypted.
- Otherwise, the hash is treated as LZ-String compressed text.
- While typing, text is compressed first; if it gets long, encrypted mode is used.

## Run Locally

1. Open `index.html` in your browser.
2. Start typing in the editor.
3. Your note is auto-saved in the URL hash.

## Deploy to GitHub Pages

This repo already includes a workflow file:

- `.github/workflows/deploy-pages.yml`

### First-time setup

1. Push the project to GitHub.
2. Open `Settings` > `Pages` in your repository.
3. Under `Build and deployment`, set `Source` to `GitHub Actions`.
4. Push any commit to `master` (or run the workflow manually from `Actions`).

### Live URL

- `https://priyans16PG.github.io/notepad/`

### Redeploy behavior

- Every push to `master` triggers a new Pages deployment automatically.

### If you see a 404

- Confirm Pages `Source` is set to `GitHub Actions`.
- Check the `Actions` tab and wait until the deployment workflow is green.
- Refresh after 1-2 minutes (first deploy can take a bit longer).

## Project Files

- `index.html`: Main app (HTML, CSS, JS)
- `.github/workflows/deploy-pages.yml`: GitHub Pages deployment workflow

## Notes

- This is a static client-side project.
- The encryption key is currently hard-coded in the source.
