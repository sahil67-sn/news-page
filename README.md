# Newspaper Page Layout

A single-page HTML/CSS project that mimics a newspaper front page. It uses **CSS multi-column layout** to flow text into three columns separated by vertical rules, with a masthead, a scrolling ticker, and a divider headline between two sections.

## Files

| File | Description |
|------|-------------|
| `index.html` | The complete page (HTML and CSS in one file) |

## Page Structure

| Part | Element / class | Description |
|------|-----------------|-------------|
| Masthead | `<h1>` | Centered title "Times Of India" |
| Ticker | `<marquee>` | Scrolling welcome message with a top and bottom border |
| Section 1 | `.three` | Three-column block with sub-headings, a bold lead line and two paragraphs |
| Divider | `<h4>` | Centered, large headline with a border above and below |
| Section 2 | `.box` | Three-column block with four "HELLO" headings, each followed by a paragraph |

All body text is placeholder (Lorem Ipsum) text.

## Key CSS Features

| Feature | Where | Purpose |
|---------|-------|---------|
| `column-count: 3` | `.three`, `.box` | Splits the text into three newspaper-style columns |
| `column-gap: 90px` | `.three`, `.box` | Space between columns |
| `column-rule: 3px solid black` | `.three`, `.box` | Vertical line between columns |
| `text-align: justify` | `*` | Justified text, like a printed newspaper |
| `background-color: beige` | `*` | Newsprint-style background on every element |
| Borders on `h4` and `marquee` | `h4`, `marquee` | Horizontal rules above and below the divider and ticker |
| `h1, h3 { text-align: center }` | `h1`, `h3` | Keeps the main title and sub-headings centered |

## Getting Started

No installation or build step is needed.

1. Save `index.html` to a folder.
2. Open it in any modern web browser.

## Tech Stack

- HTML5
- CSS3 (multi-column layout, borders, universal selector)

## Known Issues

- **Deprecated tag:** `<marquee>` is obsolete. It still works in most browsers, but it is not part of the HTML standard, and the empty `behavior=""` and `direction=""` attributes do nothing.
- **Typo:** the ticker text says "Persented" instead of "Presented".
- **Placeholder content:** the headings and paragraphs use Lorem Ipsum, and the four "HELLO" headings repeat the same text.
- **Fixed columns:** `column-count: 3` always uses three columns, even on narrow screens, where the text becomes cramped. `column-width` would adapt better.
- **Headings can split:** a heading may land at the bottom of one column while its paragraph starts in the next, because there is no `break-inside` or `break-after` rule.
- **Heavy global rule:** `*` sets the background to beige and the text to justified for every element, including the `<marquee>`.
- **Duplicate rules:** there are two separate `*` rules that could be merged.
- The page title is the default "Document".

## Possible Improvements

- Replace `<marquee>` with a CSS animation (`@keyframes` with `transform: translateX`)
- Use `column-width` instead of `column-count` for responsive columns
- Add `break-inside: avoid` to headings and `break-after: avoid` so they stay with their text
- Set the beige background on `body` instead of `*`
- Add a serif font (such as Georgia or Times New Roman) and a date line to look more like a newspaper
- Add images with captions inside the columns
- Replace the placeholder text with real articles and set a descriptive `<title>`
