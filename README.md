# Smart URL Notepad

A lightweight single-page notepad that stores your note in the URL hash.

## Features

- Instant typing in a full-page editor
- URL-based state sharing (no backend required)
- Automatic compression for short notes
- Automatic AES-GCM encryption for longer notes
- Auto-save every 500ms when content changes

## How It Works

- The app reads note data from `location.hash` on load.
- If the hash starts with `e`, it is treated as encrypted data and decrypted.
- Otherwise, it is treated as LZ-String compressed text.
- On changes, text is compressed first. If compressed data is long, encrypted mode is used.

## Run Locally

1. Open `index.html` in your browser.
2. Start typing in the editor.
3. Your note is automatically saved in the URL hash.

## Deploy on GitHub Pages

This repository includes a GitHub Actions workflow at `.github/workflows/deploy-pages.yml`.

1. Push this project to GitHub.
2. Open repository `Settings` > `Pages`.
3. In `Build and deployment`, set `Source` to `GitHub Actions`.
4. Push to the `master` branch (or run the workflow manually from `Actions`).
5. Your site will be published at:
	`https://priyans16PG.github.io/notepad/`

After each push to `master`, GitHub Pages redeploys automatically.

## Project Files

- `index.html` - Main application file (HTML, CSS, JS)

## Notes

- This is a static client-side project.
- Encryption key is currently hard-coded in the source.
