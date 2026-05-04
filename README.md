# rsvp-reader

A single-file, local-first reading tool for `.md` files. Three modes:

- **word** — classic Rapid Serial Visual Presentation: one word at a time, centered on a red ORP letter.
- **sentence** — flashes one sentence (or table / code block / blockquote) at a time with full markdown rendering. Better for theoretical material where you need grammatical structure.
- **bionic** — renders the whole document with the first ~40% of each word bolded so the eye fixates faster. Self-paced scrolling.

## Use

Open `rsvp.html` in any modern browser. Drag a `.md` file onto the window (or click *open .md*).

## Keys

| key | action |
|---|---|
| `space` | play / pause |
| `← / →` | step one unit back / forward |
| `shift + ← / →` | jump 20 units |
| `↑ / ↓` | wpm ± 25 |
| `1 / 2 / 3` | switch to word / sentence / bionic mode |
| `r` | restart |
| `0` | jump to start |

## Markdown features

Sentence and bionic modes render: headings, lists, ordered lists, tables, code blocks, blockquotes, bold / italic / strikethrough, inline code, links, horizontal rules, plus Obsidian-style highlights (`==text==`), wikilinks (`[[Page]]`), and embeds (`![[file]]`).

## Stack

Pure HTML / CSS / JS in one file. Sentence-mode markdown via [marked](https://github.com/markedjs/marked) loaded from CDN.
