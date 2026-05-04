# reader

A single-page markdown reader with four modes. Open `.md` files locally — nothing is uploaded.

Live: **https://salcustium.github.io/reader/**

## Modes

- **word** — classic Rapid Serial Visual Presentation. One word at a time, centered on a red ORP letter.
- **sentence** — flashes one sentence (or table / code block / blockquote / list item) at a time with full markdown rendering. Best for theoretical material where you need grammatical structure.
- **bionic** — renders the whole document with the first ~40% of each word bolded so the eye fixates faster. Self-paced scrolling.
- **page** — Edge-PDF-style paginated view with side-by-side columns, zoomable, horizontal scroll.

## Versions

| Path | For |
|---|---|
| `/` | auto-routes based on device |
| `/rsvp.html` | desktop |
| `/mobile/` | mobile + installable PWA (offline) |

## Markdown features

CommonMark + GFM (tables, task lists, strikethrough) plus Obsidian-style highlights (`==text==`), wikilinks (`[[Page]]`), and embeds (`![[file]]`). Rendered via [marked](https://github.com/markedjs/marked).

## Keys (desktop / hardware keyboard)

| key | action |
|---|---|
| `space` | play / pause |
| `← / →` | step one unit / scroll one page |
| `shift + ← / →` | jump 20 |
| `↑ / ↓` | wpm ± 25 |
| `1 / 2 / 3 / 4` | switch mode |
| `r` | restart |
| `0` | jump to start |
| `− / =` | zoom out / in (page mode) |

## Mobile gestures

- **tap** the stage — play / pause
- **swipe ←/→** — back / forward one unit (word / sentence modes)
- **prev / play / next** buttons in the bottom bar
- **pinch / scroll** — zoom (page mode)

## Stack

Pure HTML / CSS / JS. No build. Mobile is a PWA (manifest + service worker, offline after first load).
