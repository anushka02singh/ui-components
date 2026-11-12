# UI components

A small set of reusable, accessible UI components written in plain HTML and CSS: **link card**, **accordion**, **staff profile card** and **general card**. No build step, no framework, no JavaScript.

They were extracted from real pages built for a university department site running on Drupal, where the editing tools only allow basic HTML and CSS. That constraint shaped the design: everything must survive a WYSIWYG editor and work without scripts.

## Preview

Open `index.html` in a browser for a demo of all four components, plus a re-themed version.

## Components

| Component | What it is | Docs |
| --- | --- | --- |
| Link card | Image + title card where the whole card is one link | [components/link-card](components/link-card/README.md) |
| Accordion | Native `<details>` FAQ accordion | [components/accordion](components/accordion/README.md) |
| Staff card | Photo or initials, name, role, bio | [components/staff-card](components/staff-card/README.md) |
| General card | Grid of cards that each list a service or topic: title, short summary, bullets, optional link | [components/general-card](components/general-card/README.md) |

## Use it

```html
<link rel="stylesheet" href="css/components.css">
```

Copy the markup from a component's README. Load a single component by linking `css/tokens.css` plus that component's file.

## Theming

All colors, radius and the focus color are CSS custom properties in `css/tokens.css`. Override them on `:root` or any wrapper:

```css
.theme-blue { --ui-accent: #0b5fa5; --ui-accent-dark: #084677; }
```

## Design decisions

- **Semantic HTML first.** `details/summary` for the accordion, real headings and links everywhere.
- **Accessibility built in (WCAG 2.1 AA).** Visible focus rings, 44px+ touch targets, AA color contrast, reduced-motion support, no information conveyed by color alone.
- **Prefixed, BEM-style classes** (`ui-block__element--modifier`) so they cannot collide with a host theme's styles.
- **Responsive without media-query soup.** CSS grid `auto-fit` and flex wrapping; one small breakpoint where needed.
- **Defensive against theme CSS.** Component rules set their own margins, list styles and sizes so a host theme's defaults do not leak in.

## Structure

```
css/            tokens.css, one file per component, components.css (entry point)
components/     one folder per component with a README and a standalone example.html
assets/         sample images used by the demo
index.html      demo page
```

## Browser support

Current Chrome, Edge, Safari and Firefox. Native `details[name]` (single-open accordion) is an optional enhancement.

## License

MIT, see [LICENSE](LICENSE).
