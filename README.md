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

Use direct branch deployment (no GitHub Actions needed).

### First-time setup

1. Push the project to GitHub.
2. Open `Settings` > `Pages` in your repository.
3. Under `Build and deployment`:
	`Source` -> `Deploy from a branch`
4. Select branch `master` and folder `/(root)`.
5. Click `Save`.

### Live URL

- `https://priyans16PG.github.io/notepad/`

### Redeploy behavior

- Every push to `master` updates the site automatically.

### If you see a 404

- Confirm Pages source is `Deploy from a branch`.
- Confirm branch is `master` and folder is `/(root)`.
- Wait 1-2 minutes, then refresh.

## Project Files

- `index.html`: Main app (HTML, CSS, JS)
- `.nojekyll`: Prevents Jekyll processing on GitHub Pages

## Notes

- This is a static client-side project.
- The encryption key is currently hard-coded in the source.
