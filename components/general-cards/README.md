# Service card

A grid of cards for listing services or topics. Each card has a title, an optional one-line summary, bullet points and an optional link. It stacks to one column on phones.

## Files

| File | Purpose |
|---|---|
| `css/service-card.css` | Styles for the component |
| `components/service-card/example.html` | Working example with sample content |

## Usage

1. Add the stylesheet:
   ```html
   <link rel="stylesheet" href="css/service-card.css">
   ```
   Or add `@import "service-card.css";` to `css/components.css`.
2. Copy the markup from `example.html` (the block starting at `service-card-section`).
3. To add a card, copy one `<div class="service-card">` block. Delete the parts you do not need.

## Classes

| Class | Use |
|---|---|
| `service-card-section` | Wrapper. Holds the color settings below |
| `service-card-lead` | Optional intro sentence under the heading |
| `service-card-grid` | The grid. 2 columns by default |
| `service-card-grid--3`, `service-card-grid--4` | 3 or 4 columns (2 on tablet, 1 on phone) |
| `service-card` | One card |
| `service-card-tag` | Optional bold one-line summary |
| `service-card-link` | Optional link line at the bottom |

## Settings

Set these on `.service-card-section`:

| Variable | Default | Controls |
|---|---|---|
| `--sc-accent` | `#cc0033` | Top border, title and link color |
| `--sc-bg` | `#f2f2f2` | Card background |
| `--sc-text` | `#222` | Card text |

To use the site's design tokens, point them at the variables in `tokens.css`, for example `--sc-accent: var(--your-token-name);`.

## Notes

- No JavaScript and no custom fonts.
- Drupal: the Full HTML text format may strip a `<style>` block or a `<link>` inside the body. Add `service-card.css` to the theme instead and paste only the markup.
- Card titles use `<h3>`. Use an `<h2>` section heading above the grid, or adjust to the page's heading levels.
