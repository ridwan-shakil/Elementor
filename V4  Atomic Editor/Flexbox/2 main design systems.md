# Flexbox Design Types Notes (Elementor V4)

Understanding Flexbox becomes much easier when layouts are divided into 2 main design systems.

---

# 1. Auto-Flow Layouts (Dynamic Card Systems)

## Purpose
Used for layouts where:
- column count changes automatically
- items wrap responsively
- cards flow naturally based on available space

Examples:
- Service cards
- Product grids
- Blog cards
- Team sections
- Feature lists

---

## Recommended Structure

```css
.wrapper{
   display:flex;
   flex-wrap:wrap;
   gap:24px;
}

.card{
   flex:1 1 280px;
   min-width:240px;
}
```

---

## How It Works

```css
flex:1 1 280px;
```

| Value | Meaning |
|---|---|
| 1 | grow equally |
| 1 | shrink if needed |
| 280px | preferred card width |

---

## Important Mentality

Do NOT think:
> “I need 4 columns.”

Think:
> “Cards become ugly below 280px.”

Flexbox automatically creates:
- 4 columns
- 3 columns
- 2 columns
- 1 column

depending on available space.

---

## Why `min-width` Is Used

```css
min-width:240px;
```

Means:
> “Never shrink below 240px.”

Used only as a safety limit.

---

## Best Use Cases

Use auto-flow layouts for:
- repeated content
- scalable layouts
- unknown item count
- responsive card systems

---

# 2. Proportional Layouts (Structured Sections)

## Purpose
Used for layouts where:
- exact composition matters
- sections are intentionally designed
- content relationships matter more than automatic wrapping

Examples:
- Hero sections
- Split layouts
- Image + text sections
- Editorial layouts
- CTA sections

---

# WRONG Approach

Avoid using:

```css
63% / 37%
```

when gaps exist.

Because:

```text
63% + 37% + gap > 100%
```

which may cause:
- overflow
- wrapping
- layout breaking

---

# Recommended Professional Method

Use proportional grow ratios instead.

Example:

```css
.wrapper{
   display:flex;
   gap:40px;
}

.left{
   flex-grow:2;
   flex-basis:0;
}

.right{
   flex-grow:1;
   flex-basis:0;
}
```

Approx result:
- Left ≈ 66%
- Right ≈ 33%

WITHOUT manual calculations.

---

# Why Grow Ratios Work Better

Flexbox:
1. Calculates remaining space AFTER gaps
2. Distributes space proportionally

Benefits:
- no overflow
- cleaner responsiveness
- easier maintenance
- no calc() math

---

# Elementor Important Note

Elementor usually supports only whole-number grow values like:

```text
1, 2, 3, 4, 5...
```

So instead of exact decimal ratios like:

```text
1.7 / 1
```

use approximate whole-number ratios.

---

# Recommended Ratio Equivalents

| Visual Layout | Recommended Grow Ratio |
|---|---|
| 50 / 50 | 1 / 1 |
| 60 / 40 | 3 / 2 |
| 63 / 37 | 2 / 1 |
| 66 / 33 | 2 / 1 |
| 70 / 30 | 7 / 3 |
| 75 / 25 | 3 / 1 |

These are visually very close in real designs.

---

# Recommended Elementor Setup

## Wrapper
- Direction → Row
- Wrap → No
- Gap → 24px–40px

---

## Left Container

```text
Grow: 2
Shrink: 1
Basis: 0
```

---

## Right Container

```text
Grow: 1
Shrink: 1
Basis: 0
```

---

# Why `basis:0` In Proportional Layouts

`flex-basis:0` tells Flexbox:

> “Ignore content width and distribute space purely by ratio.”

This creates cleaner proportional layouts.

---

# 3. Wrap vs No-Wrap

## Use `flex-wrap:wrap`

For:
- card systems
- product grids
- dynamic layouts

Example:

```css
flex-wrap:wrap;
```

---

## Avoid Wrap

For:
- hero sections
- split layouts
- image/content sections

Usually use:

```css
flex-wrap:nowrap;
```

Then switch to:

```css
flex-direction:column;
```

on tablet/mobile.

---

# 4. Important `flex-basis` Behavior

`flex-basis` works on the MAIN AXIS.

---

## Row Direction

```css
flex-direction:row;
```

`flex-basis` behaves like width.

---

## Column Direction

```css
flex-direction:column;
```

`flex-basis` behaves more like height.

This is why layouts may behave differently on mobile when direction changes.

---

# 5. Final Mental Model

## Auto-Flow Layouts
Think:
> “Minimum comfortable card width.”

Use:
```css
flex-basis + wrap
```

---

## Proportional Layouts
Think:
> “Space proportions.”

Use:
```css
grow ratios + nowrap
```

---

# 6. Professional Rule Of Thumb

| Layout Type | Recommended Method |
|---|---|
| Cards / Grids | `flex:1 1 280px` |
| Hero Sections | grow ratios |
| Split Layouts | grow ratios |
| Product Lists | auto-wrap cards |
| Feature Cards | auto-wrap cards |
| Editorial Layouts | proportional grow |
| Dashboard Widgets | auto-wrap cards |
