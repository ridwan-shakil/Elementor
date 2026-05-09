# Elementor V4 Atomic Flexbox Workflow Notes

## Core Mindset
- Think in containers, not visuals
- Every layout = parent-child relationship
- Complex layouts = nested simple layouts

---

# Layout Thinking

## Ask First:
- Is the main layout horizontal? → `row`
- Is the main layout vertical? → `column`

Then group related elements into nested containers.

---

# Flexbox Rules

## Use Flexbox For:
- Hero sections
- Cards
- CTA sections
- Content layouts
- Most website sections

## Use Grid For:
- Strict equal columns
- Galleries
- Complex 2D layouts

---

# Professional Responsive Strategy

Avoid:
- Fixed widths
- Too many media queries
- Margin hacks

Prefer:
- `gap`
- `flex-wrap`
- `flex-grow`
- `flex-basis`
