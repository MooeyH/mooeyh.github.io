## Design System & Portfolio Starter Guide

**Author:** Mike Holman

A lightweight starter kit and working method for creating personal websites, portfolios and interactive prototypes using HTML, CSS, JavaScript and AI-assisted development.

The kit uses a reusable design system as the source of truth for colours, typography, spacing, radius, shadows, responsive layout and motion.

The aim is to create realistic, testable experiences without needing to recreate everything in design software or introduce unnecessary development frameworks.

### 1. Starter project structure

Start each project from this structure:

```text
portfolio/

├── assets/
│   ├── images/
│   └── icons/
│
├── css/
│   ├── components/
│   ├── tokens.css
│   ├── typography.css
│   └── layout.css
│
├── js/
│   └── app.js
│
├── index.html
├── about.html
├── projects.html
├── contact.html
│
└── README.md
```

#### Shared foundation files

These should normally be reused across projects:

- css/tokens.css
- css/typography.css
- css/layout.css
- README.md

Avoid changing documented design token values for an individual project unless there is a clear reason.

Project-specific styling should normally live in:

```text
css/components/
```

Reusable or project-specific JavaScript should normally live in:

```text
js/
```

Images and visual assets should live in:

```text
assets/
```

### 2. Starting a new project

Create a copy of the starter project folder and rename it for the new project.

The starter already contains design tokens, basic structure and documentation.

#### Creating index.html

The starter kit includes a ready-to-use index.html.

Normally there is no need to create one from scratch.

Simply copy the starter project and edit the supplied file.

### 3. Typography

Typography should be defined in:

```text
css/typography.css
```

Typography should include:

- font families
- font weights
- font sizes
- line heights
- display styles
- utility classes

Typography decisions should remain separate from layout and component styling.

Changing typefaces should not require component rewrites.

### 4. Design tokens

The reusable token file provides the project with shared values for:

- colours
- typography scales
- spacing
- radius
- shadows
- breakpoints
- containers
- responsive grids
- motion durations
- easing
- focus states

Use these tokens when building components rather than repeatedly introducing raw CSS values.

For example:

```css
.card {
  padding: var(--space-4);
  background: var(--colour-surface);
  border-radius: var(--radius-md);
  box-shadow: var(--shadow-1);
}
```

Prefer this over:

```css
.card {
  padding: 16px;
  background: #ffffff;
  border-radius: 12px;
}
```

If a value does not exist in the token system and is needed for an experimental design, make it clear that it is a project-specific value rather than a documented design token.

### 5. Standard CSS order

Load stylesheets in this order:

```html
<link rel="stylesheet" href="css/tokens.css">
<link rel="stylesheet" href="css/typography.css">
<link rel="stylesheet" href="css/layout.css">

<!-- Component styles -->

<link rel="stylesheet" href="css/components/example-component.css">
```

Think of the hierarchy as:

```text
Tokens
    ↓
Typography
    ↓
Layout
    ↓
Components
```

### 6. Standard JavaScript order

Load reusable JavaScript before app.js when required:

```html
<script src="js/example-component.js"></script>
<script src="js/app.js"></script>
```

This allows app.js to use functions that have already been defined.

An empty app.js is completely fine.

Add behaviour only when the project genuinely needs it.

## Starting a New Project with AI

This is the practical bit.

Attach:

- design tokens
- this README
- any design references
- any existing HTML, CSS or JavaScript files
- any imagery or assets

For an existing project, also attach the relevant code that is being modified.

Then copy and paste the prompt below.

### Copy This Prompt

I'm creating a coded website, portfolio or prototype using the attached Design System Starter Kit.

Use the supplied design tokens as the source of truth for colours, typography, spacing, radius, shadows, responsiveness and motion.

Keep the project lightweight using HTML, CSS and vanilla JavaScript.

Work section by section rather than attempting to build the entire experience at once.

Reuse existing components where possible.

Put reusable JavaScript in /js and component CSS in /css/components.

Use semantic HTML and include appropriate responsive, keyboard, focus and accessibility behaviour.

Explain important implementation decisions in plain English because I'm a Product Designer rather than a frontend developer.

What I'm building:
[describe the experience]

First section:
[describe the first section]

Reference viewport:
[for example: 390px mobile]

Expected behaviour:
[describe what should happen]

I've attached the relevant design references and assets.

Let's build this section.

### Working Principle

Understand the design
        ↓
Break it into sections
        ↓
Reuse design tokens
        ↓
Build one section
        ↓
Run it in the browser
        ↓
Inspect and critique it
        ↓
Refine behaviour
        ↓
Extract useful reusable components
        ↓
Move to the next section

