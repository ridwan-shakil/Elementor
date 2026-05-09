# Modern Card Layout System

## Parent Wrapper
- Direction: `row`
- Wrap: `yes`
- Gap: `24px`

## Card
```css
flex-grow: 1;
flex-basis: 300px;
```

Meaning:

Card tries to stay minimum 300px
Automatically wraps when needed
Grows evenly in available space
Responsive Thinking

### DON'T think:

  3 columns desktop
  2 columns tablet
  1 column mobile

### THINK:

"What is the minimum safe width for this card?"
Let Flexbox handle the layout automatically.

Fast Building Workflow

### Step 1

  Build structure only:
  
    containers
    direction
    wrap
    gap
    alignment
  
  NO styling yet.

### Step 2

Check responsiveness early.

### Step 3

Apply utility classes/components.

### Step 4

Add styling and polish.

#### Golden Rules:
    Use gap instead of margins
    Avoid unnecessary nesting
    Use nested containers logically
    Let flexbox solve layouts naturally
    If layout feels difficult, structure is probably wrong
    Atomic Editor Best Practices

Use:

Variables → design system
Classes → reusable styling
Components → reusable UI
Containers → layout structure

Goal:
Build systems, not individual pages.
