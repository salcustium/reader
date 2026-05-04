# reader

A single-page markdown reader with four modes. Open `.md` files locally — nothing is uploaded.

Live: **https://salcustium.github.io/reader/**

## Modes

- **word** — classic Rapid Serial Visual Presentation. One word at a time, centered on a red ORP letter.
- **sentence** — flashes one sentence (or table / code block / blockquote / list item) at a time with full markdown rendering. Best for theoretical material where you need grammatical structure.
- **bionic** — renders the whole document with the first ~40% of each word bolded so the eye fixates faster. Self-paced scrolling.
- **page** — Edge-PDF-style paginated view with side-by-side columns, zoomable, horizontal scroll, configurable column count.

## Versions

| Path | For |
|---|---|
| `/` | auto-routes based on device |
| `/read.html` | desktop |
| `/mobile/` | mobile + installable PWA (offline) |

## Features

- **Library** (mobile): every `.md` you open is saved to an in-browser library (IndexedDB). The list shows recency, size, and reading progress. Tap to resume where you left off. Multi-select picker to import several files at once. Auto-resume the most recent file on app launch.
- **Context strip** (mobile, toggle): a faded view of the current paragraph slides up from the bottom while you read in word or sentence mode, with the current word/sentence highlighted in the accent color. Gives you a sense of where you are without losing the focused reading view.
- **Themes**: dark / light / sepia / night / custom (with bg / fg / accent color pickers).
- **Phantom words** (toggle): faded prev/next word above and below the current word in word mode.
- **Hold to read** (toggle): press-and-hold the stage to play, release to pause. Coexists with horizontal scrub.
- **Heading jump**: `[` and `]` (or buttons in mobile settings) skip to prev / next heading in sentence / bionic / page modes.
- **Status cycle**: tap the status text to cycle progress / percent / time-left / words-left.
- **Resume position**: each file remembers your last position, mode, and total length.

## File formats

The reader natively reads **`.md` / `.markdown` / `.txt` / `.pdf`** files. PDFs are parsed with [pdf.js](https://mozilla.github.io/pdf.js/) (loaded on demand from CDN). For everything else, convert first — some free tools that work well:

| Source | Tool |
|---|---|
| `.docx` → md | [Word2MD](https://word2md.com/), [word2md.net](https://www.word2md.net/), [DocToMD](https://doctomd.com/) |
| `.epub` → md / txt | [Calibre](https://calibre-ebook.com/) (desktop), [Word.to EPUB→Markdown](https://word.to/epub-markdown/) |
| `.pdf` → md (richer than built-in) | [PDF2MD](https://pdf2md.morethan.io/), [NoteGPT PDF→MD](https://notegpt.io/pdf-to-markdown-converter) |
| anything → anything | [Pandoc](https://pandoc.org/) (CLI, free, offline), [Microsoft markitdown](https://github.com/microsoft/markitdown) |

## Markdown features

CommonMark + GFM (tables, task lists, strikethrough) plus Obsidian-style highlights (`==text==`), wikilinks (`[[Page]]`), and embeds (`![[file]]`). Rendered via [marked](https://github.com/markedjs/marked).

## Keyboard (desktop / hardware keyboard)

| key | action |
|---|---|
| `space` | play / pause |
| `← / →` | step one unit / scroll one page |
| `shift + ← / →` | jump 20 |
| `↑ / ↓` | wpm ± 25 |
| `[ / ]` | prev / next heading |
| `1 / 2 / 3 / 4` | switch mode |
| `r` | restart |
| `0` | jump to start |
| `− / =` | zoom out / in (page mode) |
| `,` | open settings |

## Mobile gestures

- **tap** the stage — play / pause
- **swipe horizontally** — continuous scrub through words / sentences (fine near zero, accelerated when far)
- **pinch / scroll** — zoom (page mode)
- **tap status text** — cycle status views

## Stack

Pure HTML / CSS / JS, no build. Mobile is a PWA (manifest + service worker, offline after first load). IndexedDB for the library, localStorage for preferences.
