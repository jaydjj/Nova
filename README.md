# Nova

A recreation of the **Nova Robin** birth announcement — a single, self-contained
static web page that reproduces all six screens of the original
[Figma site](https://rail-swear-20024398.figma.site).

The six screens are **3 languages × 2 dates**:

| | June 27 | June 28 |
|------|---------|---------|
| English | ✅ | ✅ |
| Dutch (Nederlands) | ✅ | ✅ |
| German (Deutsch) | ✅ | ✅ |

The three language cards are stacked on one page (US-Letter proportioned,
`8.5in × 11in`). The **Date** toggle (bottom-left) switches every card between
June 27 and June 28, giving all six states.

## Run

No build step. Just open the file in a browser:

```sh
open index.html
```

Fonts (Great Vibes for the name, Cormorant Garamond for the body) load from
Google Fonts, so an internet connection gives the intended look.

## Download / print

The **Download 3 Images** button (bottom-right) opens the print dialog. Each
card is laid out as its own Letter-sized page (`break-after: page`) and the
on-screen controls are hidden in print, so "Save as PDF" produces a clean
3-page document of the currently selected date.

## Structure

```
Nova/
├─ index.html        # everything: markup, CSS, the announcement text, render logic
├─ assets/           # botanical_1.jpg … botanical_10.jpg (watercolor wildflowers)
└─ README.md
```

The announcement text for all three languages lives in the `DATA` array near
the bottom of `index.html`. The first paragraph of each language contains a
`{d}` placeholder that the date toggle fills in.

## Design notes

- **Type:** `Great Vibes` (script, 100px) for the name; `Cormorant Garamond`
  (serif, 13.5px, justified) for the body.
- **Palette:** warm stone greys — `#1c1917` / `#292524` / `#57534e` on a
  `#f4f2ef` page.
- **Florals:** ten 4096px watercolor illustrations (downscaled for the web),
  placed at the card corners with `mix-blend-multiply` and a radial mask so they
  dissolve into the page. A radial white glow at the top keeps the name legible.
