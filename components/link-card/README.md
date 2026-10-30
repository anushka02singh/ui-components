# Link card

A card for an index of things (galleries, articles, programs) where the whole card is one click target.

### How it works
The title is the only real link. Its `::after` is stretched over the card (`position: absolute; inset: 0`), so a click anywhere opens the page, but assistive technology still sees one clearly named link.

### Classes
| Class | Purpose |
| --- | --- |
| `.ui-card-grid` | Responsive grid (`auto-fit`, no media queries needed) |
| `.ui-link-card` | The card |
| `.ui-link-card__media` | Cover image, cropped to 4:3 |
| `.ui-link-card--no-media` | Modifier: gray placeholder when there is no image yet |
| `.ui-link-card__body / __title / __meta / __cta` | Text areas |

### Accessibility
- One link per card; link text is the title.
- Cover image uses `alt=""` because the title already describes the link.
- The decorative "View gallery →" text is `aria-hidden`.
- Visible 3px focus ring around the whole card; 44px+ target; respects `prefers-reduced-motion`.

### Why nothing is nested in the link
Wrapping an image plus several blocks in one `<a>` is valid HTML5, but many WYSIWYG editors (including CKEditor in Drupal) rewrite it. The stretched-link pattern avoids the problem.

## Markup

```html
<div class="ui-card-grid" role="list" aria-label="Photo galleries">
  <div class="ui-link-card" role="listitem">
    <img class="ui-link-card__media" src="assets/sample-1.svg" alt="" width="768" height="576">
    <div class="ui-link-card__body">
      <div>
        <p class="ui-link-card__title"><a href="#celtic">Celtic Pub Night</a></p>
        <p class="ui-link-card__meta">21 photos</p>
      </div>
      <p class="ui-link-card__cta" aria-hidden="true">View gallery</p>
    </div>
  </div>
  <div class="ui-link-card" role="listitem">
    <img class="ui-link-card__media" src="assets/sample-2.svg" alt="" width="768" height="576">
    <div class="ui-link-card__body">
      <div>
        <p class="ui-link-card__title"><a href="#fall">Fall Events</a></p>
        <p class="ui-link-card__meta">12 photos</p>
      </div>
      <p class="ui-link-card__cta" aria-hidden="true">View gallery</p>
    </div>
  </div>
  <div class="ui-link-card ui-link-card--no-media" role="listitem">
    <div class="ui-link-card__body">
      <div>
        <p class="ui-link-card__title"><a href="#brunch">Spring Brunch</a></p>
      </div>
      <p class="ui-link-card__cta" aria-hidden="true">View gallery</p>
    </div>
  </div>
</div>
```

## Usage

```html
<link rel="stylesheet" href="css/components.css">
```

Or include only `css/tokens.css` and `css/link-card.css`. Open `example.html` in a browser to see it on its own.
