# 🚀 Elementor V4 Atomic Workflow Guide

A minimal, scalable approach to building complex layouts in Elementor V4 using classes, variables, and reusable patterns.

---

## 🔷 Core Philosophy

* Build **systems, not pages**
* Use **classes over local styling**
* Keep everything **reusable and predictable**
* Prefer **fluid design** over fixed breakpoints
* Avoid repetition → **reuse everything**

---

## 🔷 1. Design Tokens (Start Here)

Define global variables:

* Colors → `--color-primary`, `--color-text`
* Typography → fluid (`clamp()`)
* Spacing → consistent scale (`--space-1 → --space-5`)

👉 Never use raw values (px, hex) in design.

---

## 🔷 2. Layout Structure

Use a simple, consistent structure:

```
Section (.section)
  → Wrapper (.wrap)
    → Layout (.flex / .grid)
      → Content (widgets)
```

### Responsibilities:

* `.section` → vertical spacing
* `.wrap` → width control
* `.flex / .grid` → layout
* `.gap-*` → spacing

---

## 🔷 3. Spacing System

Use **gap instead of margin/padding for layout spacing**:

```
gap-1
gap-2
gap-3
gap-4
```

👉 Controls spacing between elements globally
👉 Avoids inconsistent padding usage

---

## 🔷 4. Responsive Strategy (Minimal)

Default behavior:

* `.flex-row` → row (desktop)
* → column (mobile)

Override only when needed:

```
.flex-row-mobile → keeps row on mobile
```

👉 No need for heavy breakpoint management
👉 Works across all layouts

---

## 🔷 5. Typography System

Use predefined classes:

```
.heading-xl
.heading-lg
.text-md
.text-sm
.text-muted
```

👉 Fully controlled via variables
👉 Scales automatically (fluid)

---

## 🔷 6. Components

Create reusable UI:

* `.btn`, `.btn-primary`
* `.card`
* `.grid`

👉 Never redesign components per page

---

## 🔷 7. Workflow

1. Add section → apply `.section`
2. Add inner container → `.wrap`
3. Choose layout → `.flex` / `.grid`
4. Apply spacing → `.gap-*`
5. Apply typography classes
6. Reuse components

👉 Avoid styling from Elementor panel unless necessary

---

## 🔷 8. Rules

✅ Use classes for repeated patterns
✅ Use variables everywhere
✅ Keep class list small
✅ Reuse blocks/components

❌ Don’t use random padding/margin
❌ Don’t mix inconsistent values
❌ Don’t style each widget individually

---

## 🔷 9. Goal

* Faster builds (2–4x)
* Consistent UI
* Minimal responsive work
* Scalable system for all projects

---

## 🔥 Final Insight

> Elementor V4 is not about dragging widgets
> It’s about building a **design system inside a builder**
