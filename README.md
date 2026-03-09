# 📚 Folio — Personal Epub Manager

A lightweight, browser-based epub library manager. No server required — runs entirely in your browser as a static site on GitHub Pages.

## Features

- **Library** — Upload and manage your epub/mobi/azw3/pdf files with a cover art grid view. Edit titles, authors, tags. Filter and search.
- **Cover Changer** — Replace the cover art on any book in your library.
- **Send to Kindle** — Select books and send them to your Kindle via Amazon's Send-to-Kindle email system.

## Deploy to GitHub Pages

1. Fork or clone this repo
2. Go to your repo → **Settings → Pages**
3. Under *Source*, select `main` branch and `/ (root)` folder
4. Hit **Save** — your site will be live at `https://yourusername.github.io/your-repo-name`

That's it. No build step, no dependencies.

## Send to Kindle Setup

1. Log into Amazon → **Manage Your Content and Devices → Preferences → Personal Document Settings**
2. Note your Kindle's email address (ends in `@kindle.com`)
3. Under **Approved Personal Document E-mail List**, add the email you send from
4. In Folio, click **⚙ Kindle Settings** and enter both addresses
5. Select books → **Send Selected Books** → attach the epub files in the email that opens

## Notes

- **Files are session-only.** Since this is a static site with no backend, uploaded files live in browser memory and need to be re-uploaded each session. Book metadata (title, author, tag, cover art) is saved to `localStorage` and persists between visits.
- **Cover art** is stored as base64 in localStorage and persists.
- For true persistent file storage, a backend (Node/Python + file system) would be needed — but this keeps things simple and private.

## File structure

```
index.html   ← entire app, single file
README.md
```
