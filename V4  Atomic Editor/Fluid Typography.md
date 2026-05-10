# Fluid Typography in Elementor V4

## Why Use Fluid Typography?

Fluid typography automatically scales text smoothly between mobile and desktop using `clamp()`.

Benefits:

* Better responsiveness
* Consistent design system
* Fewer breakpoint adjustments
* Cleaner Elementor workflow

---

# Recommended Typography Scale

```css
text-sm
clamp(0.8rem, 0.75rem + 0.2vw, 0.9rem)

text-md
clamp(1rem, 0.95rem + 0.3vw, 1.1rem)

text-lg
clamp(1.25rem, 1.1rem + 0.6vw, 1.5rem)

heading-sm
clamp(1.45rem, 1.2rem + 1vw, 2rem)

heading-md
clamp(1.75rem, 1.4rem + 1.5vw, 2.5rem)

heading-lg
clamp(2.2rem, 1.6rem + 2.5vw, 3.5rem)

heading-xl
clamp(2.8rem, 2rem + 3.5vw, 4.5rem)
```

---

# Typography Reference Table

| Variable   | Mobile Approx | Desktop Approx | Usage                        |
| ---------- | ------------- | -------------- | ---------------------------- |
| text-sm    | 13px          | 14px           | Small text, labels           |
| text-md    | 16px          | 18px           | Paragraph text               |
| text-lg    | 20px          | 24px           | Large paragraph / intro text |
| heading-sm | 23px          | 32px           | Card titles, small headings  |
| heading-md | 28px          | 40px           | Section headings             |
| heading-lg | 35px          | 56px           | Hero headings                |
| heading-xl | 45px          | 72px           | Main landing page heading    |

---

# Best Practices

* Use REM units instead of PX
* Reuse the same typography tokens everywhere
* Avoid creating too many font sizes
* Combine with consistent line-height and spacing
* Let `clamp()` handle responsiveness instead of adding many breakpoints

---

# Elementor V4 Tip

Create typography variables once in:
Global Variables → Typography

Then reuse them across:

* Atomic Elements
* Components
* Templates
* Containers

This creates a scalable design system for all client projects.
