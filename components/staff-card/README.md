# Staff card

A profile card with a photo or initials, name, role and optional bio.

### Classes
| Class | Purpose |
| --- | --- |
| `.ui-staff-grid` | Flex wrap container (3 across on wide screens) |
| `.ui-staff-card` | The card |
| `.ui-staff-card--wide` | Modifier: full-width card, good for a long bio |
| `.ui-staff-card__avatar` | Use on a `<div>` for initials or on an `<img>` for a photo |
| `.ui-staff-card__name / __role / __bio` | Text parts |

### Accessibility
- Name is a real heading (`h3`; change the level to fit your page).
- Initials avatars are `aria-hidden` since the name is next to them; photos need meaningful `alt` text.
- Colors meet WCAG AA contrast on the card background.

## Markup

```html
<div class="ui-staff-grid">
  <div class="ui-staff-card ui-staff-card--wide">
    <div class="ui-staff-card__avatar" aria-hidden="true">JD</div>
    <h3 class="ui-staff-card__name">Jane Doe</h3>
    <p class="ui-staff-card__role">Director</p>
    <div class="ui-staff-card__bio">
      <p>Jane leads the team and has spent ten years building community programs.</p>
      <p>Outside of work she volunteers with local arts organizations.</p>
    </div>
  </div>
  <div class="ui-staff-card">
    <img class="ui-staff-card__avatar" src="assets/sample-3.svg" alt="Portrait of Sam Lee" width="64" height="64">
    <h3 class="ui-staff-card__name">Sam Lee</h3>
    <p class="ui-staff-card__role">Treasurer</p>
  </div>
  <div class="ui-staff-card">
    <div class="ui-staff-card__avatar" aria-hidden="true">AR</div>
    <h3 class="ui-staff-card__name">Alex Rivera</h3>
    <p class="ui-staff-card__role">Events Coordinator</p>
  </div>
</div>
```

## Usage

```html
<link rel="stylesheet" href="css/components.css">
```

Or include only `css/tokens.css` and `css/staff-card.css`. Open `example.html` in a browser to see it on its own.
