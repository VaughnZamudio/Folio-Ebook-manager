# 📚 Folio — Personal Ebook Manager

**A free, private ebook library that lives in your browser. No account. No install. No ads.**

## → [Open Folio](https://vaughnzamudio.github.io/Folio-Ebook-manager/)

---

## What is Folio?

Folio is a single webpage that acts as a personal epub library manager. You drag in your ebook files, and it gives you a clean bookshelf with cover art, metadata, search, and tools to send books to your Kindle or repair broken epub files.

Everything runs locally in your browser — nothing is uploaded to any server.

---

## What it can do

### 📚 Library
- Drag and drop epub, mobi, azw3, or pdf files to add them
- Browse your books as a cover art grid
- Search by title or author, filter by tag or series
- Edit a book's title, author, and series/tag
- Download any loaded book back to your computer

### 🖼 Cover Changer
- Replace the cover art on any book in your library
- Upload any JPG, PNG, or WEBP image as the new cover
- Cover art saves permanently and shows up every time you return

### 📨 Send to Kindle
- Select one or more books and send them to your Kindle via Amazon's free email delivery system
- Folio opens a pre-filled email and downloads the files automatically — you just attach and send
- See the [Kindle setup guide](#kindle-setup) below

### 🔧 Repair & Clean
The most powerful feature. Folio reads your epub's internal structure, sends it to AI for analysis, and gives you:

- A **health score** (0–100) for the epub
- A list of **issues** found (missing cover, broken navigation, bad metadata, etc.)
- **One-click auto-fixes** for things it can actually patch:
  - Wrong or missing title in the epub's navigation file
  - Empty description field
  - Missing series/series-index tags (Calibre-compatible)
  - Author name in "Last, First" format → normalized to "First Last"
- An editable **metadata panel** to fix title, author, publisher, series, and more
- A **Fix & Download** button that writes all patches into the epub and downloads a clean `_fixed.epub`

> **One thing it can't auto-fix:** a missing cover image. If the original file never had one, there's nothing to inject. Use the **Cover Changer** tab to add one after downloading.

**Two modes for the AI analysis:**
| Mode | How it works | Cost |
|---|---|---|
| ⚡ API mode | Uses your Anthropic API key for instant in-app analysis | ~$0.01–0.03/book. New accounts get $5 free at [console.anthropic.com](https://console.anthropic.com) |
| ✨ Free mode | Folio builds the prompt, you paste it into [Claude.ai](https://claude.ai), paste the response back | Free |

---

## What persists between visits

| Data | Saved? |
|---|---|
| Book titles, authors, tags | ✅ Always (localStorage) |
| Cover art | ✅ Always (localStorage) |
| Kindle email settings | ✅ Always (localStorage) |
| Anthropic API key | ✅ Always (localStorage) |
| Epub file contents | ⚠️ This session only — re-upload after closing the tab |

Epub files can't be saved permanently without a backend server, so you'll need to re-drag them in each session. Your library info and covers will already be there waiting.

---

## Kindle Setup

1. Go to [Amazon → Manage Your Content and Devices](https://www.amazon.com/mycd) → **Preferences → Personal Document Settings**
2. Find your Kindle's `@kindle.com` email address
3. Under **Approved Personal Document E-mail List**, add the email address you'll send from
4. In Folio, click **⚙ Kindle Settings** on the Send to Kindle tab
5. Enter both addresses and save
6. Select books → **Send Selected** → attach the downloaded files to the email that opens → send

---

## Privacy

- Nothing leaves your device except epub structure metadata sent to the Anthropic API (Repair tab, API mode only)
- No tracking, no analytics, no accounts, no ads
- All data stored in your own browser's localStorage

---

## Self-hosting

Want your own copy on GitHub Pages?

1. Fork this repo
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)` folder
4. Save — live at `https://yourusername.github.io/your-repo-name`

No build step. No dependencies. The entire app is one HTML file.

```
index.html   ← the entire app
README.md    ← this file
```
