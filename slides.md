---
theme: default
background: '#ffffff'
title: You can be productive with Xcode, and you know it
class: text-left
transition: fade
mdc: true
---

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap');

:root {
  /* Typography */
  --font-base: 'Inter', -apple-system, system-ui, sans-serif;
  --size-h1: 2.75rem;
  --size-h2: 1.4rem;
  --size-h3: 1.15rem;
  --size-base: 1.1rem;
  --size-small: 0.95rem;
  --weight-normal: 400;
  --weight-medium: 500;
  --weight-semibold: 600;
  --weight-bold: 700;
  --line-base: 1.6;
  --line-tight: 1.2;

  /* Spacing */
  --space-xs: 0.5rem;
  --space-sm: 0.75rem;
  --space-md: 1rem;
  --space-lg: 1.5rem;
  --space-xl: 2rem;
  --space-2xl: 3rem;
  --gap-cols: 3rem;

  /* Layout */
  --radius: 4px;
  --border-width: 3px;
}

* {
  font-family: var(--font-base) !important;
}

/* Base slide styling */
.slidev-layout {
  background: var(--color-bg);
  color: var(--color-text);
  padding: var(--space-2xl) 3.5rem !important;
  font-size: var(--size-base);
  line-height: var(--line-base);
  position: relative;
  z-index: 1;
}

/* Ensure nav controls don't bleed through */
.slidev-layout::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: var(--color-bg);
  z-index: -1;
}

/* Typography system */
h1 {
  font-size: var(--size-h1) !important;
  font-weight: var(--weight-bold) !important;
  color: var(--color-text) !important;
  margin-bottom: 0 !important;
  line-height: var(--line-tight) !important;
}

/* H2 as subtitle when following H1 */
h1 + h2 {
  font-size: 2rem !important;
  font-weight: var(--weight-semibold) !important;
  color: var(--color-text) !important;
  margin-top: 0.25rem !important;
  margin-bottom: var(--space-sm) !important;
}

h2 {
  font-size: var(--size-h2) !important;
  font-weight: var(--weight-semibold) !important;
  color: var(--color-text) !important;
  margin-top: var(--space-lg) !important;
  margin-bottom: var(--space-sm) !important;
}

h3 {
  font-size: var(--size-h3) !important;
  font-weight: var(--weight-semibold) !important;
  color: var(--color-text) !important;
  margin-bottom: var(--space-xs) !important;
}

strong {
  font-weight: var(--weight-semibold);
  color: var(--color-text);
}

code {
  background: var(--color-bg-muted) !important;
  color: #d14 !important;
  padding: 0.15em 0.4em !important;
  border-radius: var(--radius) !important;
  font-size: 0.9em !important;
  font-weight: var(--weight-medium) !important;
}

/* Code blocks with syntax highlighting */
.slidev-layout pre {
  background: #282a36 !important;
  padding: var(--space-md) !important;
  border-radius: var(--radius) !important;
  overflow-x: auto !important;
}

.slidev-layout pre code {
  background: transparent !important;
  color: inherit !important;
  padding: 0 !important;
}

/* Utility classes */
.quiet {
  color: var(--color-text-muted);
  font-size: var(--size-base);
  font-weight: var(--weight-normal);
  margin-top: calc(var(--space-xs) / 2);
}

.cols {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--gap-cols);
  margin-top: var(--space-md);
}

.grid-3 {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--space-xl);
  margin-top: var(--space-md);
}

.box {
  background: var(--color-bg-muted);
  padding: 1.25rem;
  border-radius: var(--radius);
}

.box h3 {
  margin-top: 0;
  padding-bottom: var(--space-xs);
  border-bottom: 1px solid var(--color-border);
}

/* Tip admonition */
.tip {
  background: var(--color-bg-muted);
  border-left: 4px solid var(--color-accent);
  padding: var(--space-md);
  border-radius: var(--radius);
  margin: var(--space-md) 0;
}

.tip h3 {
  margin-top: 0;
  color: var(--color-accent);
  font-size: var(--size-h3);
  margin-bottom: var(--space-xs);
}

.tip h3::before {
  content: "💡 ";
  margin-right: 0.5rem;
}

/* Phase intro styling */
.phase-intro h1::before {
  content: '';
  display: block;
  width: 4rem;
  height: 0.25rem;
  background: var(--color-accent);
  margin-bottom: var(--space-lg);
}

/* List system */
.slidev-layout ul {
  list-style: none;
  padding: 0;
  margin: var(--space-sm) 0;
}

.slidev-layout li {
  margin: var(--space-xs) 0;
  padding-left: var(--space-lg);
  position: relative;
  line-height: 1.5;
}

.slidev-layout li::before {
  content: '→';
  position: absolute;
  left: 0;
  color: var(--color-text-muted);
  font-weight: var(--weight-normal);
}

.slidev-layout li li {
  font-size: var(--size-small);
  color: var(--color-text-muted);
  margin: calc(var(--space-xs) / 2) 0;
  padding-left: 1.25rem;
}

.slidev-layout li li::before {
  content: '·';
  color: var(--color-text-subtle);
}

/* Hide/layer navigation properly */
.slidev-page,
#slide-content {
  position: relative;
  z-index: 10;
}

.slidev-layout > * {
  position: relative;
  z-index: 2;
}

/* Header with X handle and email */
.slidev-layout::after {
  content: 'x.com/pepicrft · pedro@tuist.dev';
  position: fixed;
  top: 1.5rem;
  right: 3.5rem;
  font-size: 0.85rem;
  color: var(--color-text-muted);
  z-index: 1000;
  opacity: 0.6;
}

/* Repository link in top left */
#slideshow::before {
  content: '📄 github.com/tuist/talk-productive-with-xcode';
  position: fixed;
  top: 1.5rem;
  left: 3.5rem;
  font-size: 0.85rem;
  color: var(--color-text-muted);
  z-index: 1001;
  opacity: 0.6;
  pointer-events: none;
}

/* Per-slide OKLCH colors with varying hue and lightness */
.slidev-page-1 { --color-text: oklch(0.20 0.08 230); --color-text-muted: oklch(0.45 0.06 230); --color-text-subtle: oklch(0.60 0.05 230); --color-bg: oklch(0.97 0.02 230); --color-bg-muted: oklch(0.94 0.02 230); --color-accent: oklch(0.20 0.08 230); --color-border: oklch(0.85 0.03 230); }
.slidev-page-2 { --color-text: oklch(0.21 0.08 235); --color-text-muted: oklch(0.46 0.06 235); --color-text-subtle: oklch(0.61 0.05 235); --color-bg: oklch(0.96 0.02 235); --color-bg-muted: oklch(0.93 0.02 235); --color-accent: oklch(0.21 0.08 235); --color-border: oklch(0.84 0.03 235); }
.slidev-page-3 { --color-text: oklch(0.22 0.09 240); --color-text-muted: oklch(0.47 0.07 240); --color-text-subtle: oklch(0.62 0.06 240); --color-bg: oklch(0.95 0.03 240); --color-bg-muted: oklch(0.92 0.03 240); --color-accent: oklch(0.22 0.09 240); --color-border: oklch(0.83 0.04 240); }
.slidev-page-4 { --color-text: oklch(0.23 0.09 245); --color-text-muted: oklch(0.48 0.07 245); --color-text-subtle: oklch(0.63 0.06 245); --color-bg: oklch(0.94 0.03 245); --color-bg-muted: oklch(0.91 0.03 245); --color-accent: oklch(0.23 0.09 245); --color-border: oklch(0.82 0.04 245); }
.slidev-page-5 { --color-text: oklch(0.24 0.10 250); --color-text-muted: oklch(0.49 0.08 250); --color-text-subtle: oklch(0.64 0.07 250); --color-bg: oklch(0.93 0.04 250); --color-bg-muted: oklch(0.90 0.04 250); --color-accent: oklch(0.24 0.10 250); --color-border: oklch(0.81 0.05 250); }
.slidev-page-6 { --color-text: oklch(0.25 0.10 255); --color-text-muted: oklch(0.50 0.08 255); --color-text-subtle: oklch(0.65 0.07 255); --color-bg: oklch(0.92 0.04 255); --color-bg-muted: oklch(0.89 0.04 255); --color-accent: oklch(0.25 0.10 255); --color-border: oklch(0.80 0.05 255); }
.slidev-page-7 { --color-text: oklch(0.24 0.11 260); --color-text-muted: oklch(0.49 0.09 260); --color-text-subtle: oklch(0.64 0.08 260); --color-bg: oklch(0.93 0.05 260); --color-bg-muted: oklch(0.90 0.05 260); --color-accent: oklch(0.24 0.11 260); --color-border: oklch(0.81 0.06 260); }
.slidev-page-8 { --color-text: oklch(0.23 0.11 265); --color-text-muted: oklch(0.48 0.09 265); --color-text-subtle: oklch(0.63 0.08 265); --color-bg: oklch(0.94 0.05 265); --color-bg-muted: oklch(0.91 0.05 265); --color-accent: oklch(0.23 0.11 265); --color-border: oklch(0.82 0.06 265); }
.slidev-page-9 { --color-text: oklch(0.22 0.12 270); --color-text-muted: oklch(0.47 0.10 270); --color-text-subtle: oklch(0.62 0.09 270); --color-bg: oklch(0.95 0.06 270); --color-bg-muted: oklch(0.92 0.06 270); --color-accent: oklch(0.22 0.12 270); --color-border: oklch(0.83 0.07 270); }
.slidev-page-10 { --color-text: oklch(0.21 0.12 275); --color-text-muted: oklch(0.46 0.10 275); --color-text-subtle: oklch(0.61 0.09 275); --color-bg: oklch(0.96 0.06 275); --color-bg-muted: oklch(0.93 0.06 275); --color-accent: oklch(0.21 0.12 275); --color-border: oklch(0.84 0.07 275); }
.slidev-page-11 { --color-text: oklch(0.20 0.13 280); --color-text-muted: oklch(0.45 0.11 280); --color-text-subtle: oklch(0.60 0.10 280); --color-bg: oklch(0.97 0.07 280); --color-bg-muted: oklch(0.94 0.07 280); --color-accent: oklch(0.20 0.13 280); --color-border: oklch(0.85 0.08 280); }
.slidev-page-12 { --color-text: oklch(0.21 0.13 285); --color-text-muted: oklch(0.46 0.11 285); --color-text-subtle: oklch(0.61 0.10 285); --color-bg: oklch(0.96 0.07 285); --color-bg-muted: oklch(0.93 0.07 285); --color-accent: oklch(0.21 0.13 285); --color-border: oklch(0.84 0.08 285); }
.slidev-page-13 { --color-text: oklch(0.22 0.11 290); --color-text-muted: oklch(0.47 0.09 290); --color-text-subtle: oklch(0.62 0.08 290); --color-bg: oklch(0.95 0.05 290); --color-bg-muted: oklch(0.92 0.05 290); --color-accent: oklch(0.22 0.11 290); --color-border: oklch(0.83 0.06 290); }
.slidev-page-14 { --color-text: oklch(0.23 0.10 295); --color-text-muted: oklch(0.48 0.08 295); --color-text-subtle: oklch(0.63 0.07 295); --color-bg: oklch(0.94 0.04 295); --color-bg-muted: oklch(0.91 0.04 295); --color-accent: oklch(0.23 0.10 295); --color-border: oklch(0.82 0.05 295); }
.slidev-page-15 { --color-text: oklch(0.24 0.09 300); --color-text-muted: oklch(0.49 0.07 300); --color-text-subtle: oklch(0.64 0.06 300); --color-bg: oklch(0.93 0.03 300); --color-bg-muted: oklch(0.90 0.03 300); --color-accent: oklch(0.24 0.09 300); --color-border: oklch(0.81 0.04 300); }
.slidev-page-16 { --color-text: oklch(0.25 0.08 305); --color-text-muted: oklch(0.50 0.06 305); --color-text-subtle: oklch(0.65 0.05 305); --color-bg: oklch(0.92 0.02 305); --color-bg-muted: oklch(0.89 0.02 305); --color-accent: oklch(0.25 0.08 305); --color-border: oklch(0.80 0.03 305); }
.slidev-page-17 { --color-text: oklch(0.24 0.09 310); --color-text-muted: oklch(0.49 0.07 310); --color-text-subtle: oklch(0.64 0.06 310); --color-bg: oklch(0.93 0.03 310); --color-bg-muted: oklch(0.90 0.03 310); --color-accent: oklch(0.24 0.09 310); --color-border: oklch(0.81 0.04 310); }
.slidev-page-18 { --color-text: oklch(0.23 0.10 315); --color-text-muted: oklch(0.48 0.08 315); --color-text-subtle: oklch(0.63 0.07 315); --color-bg: oklch(0.94 0.04 315); --color-bg-muted: oklch(0.91 0.04 315); --color-accent: oklch(0.23 0.10 315); --color-border: oklch(0.82 0.05 315); }
.slidev-page-19 { --color-text: oklch(0.22 0.11 320); --color-text-muted: oklch(0.47 0.09 320); --color-text-subtle: oklch(0.62 0.08 320); --color-bg: oklch(0.95 0.05 320); --color-bg-muted: oklch(0.92 0.05 320); --color-accent: oklch(0.22 0.11 320); --color-border: oklch(0.83 0.06 320); }
.slidev-page-20 { --color-text: oklch(0.21 0.12 325); --color-text-muted: oklch(0.46 0.10 325); --color-text-subtle: oklch(0.61 0.09 325); --color-bg: oklch(0.96 0.06 325); --color-bg-muted: oklch(0.93 0.06 325); --color-accent: oklch(0.21 0.12 325); --color-border: oklch(0.84 0.07 325); }
.slidev-page-21 { --color-text: oklch(0.20 0.13 330); --color-text-muted: oklch(0.45 0.11 330); --color-text-subtle: oklch(0.60 0.10 330); --color-bg: oklch(0.97 0.07 330); --color-bg-muted: oklch(0.94 0.07 330); --color-accent: oklch(0.20 0.13 330); --color-border: oklch(0.85 0.08 330); }
.slidev-page-22 { --color-text: oklch(0.21 0.12 335); --color-text-muted: oklch(0.46 0.10 335); --color-text-subtle: oklch(0.61 0.09 335); --color-bg: oklch(0.96 0.06 335); --color-bg-muted: oklch(0.93 0.06 335); --color-accent: oklch(0.21 0.12 335); --color-border: oklch(0.84 0.07 335); }
.slidev-page-23 { --color-text: oklch(0.22 0.11 340); --color-text-muted: oklch(0.47 0.09 340); --color-text-subtle: oklch(0.62 0.08 340); --color-bg: oklch(0.95 0.05 340); --color-bg-muted: oklch(0.92 0.05 340); --color-accent: oklch(0.22 0.11 340); --color-border: oklch(0.83 0.06 340); }
.slidev-page-24 { --color-text: oklch(0.23 0.10 345); --color-text-muted: oklch(0.48 0.08 345); --color-text-subtle: oklch(0.63 0.07 345); --color-bg: oklch(0.94 0.04 345); --color-bg-muted: oklch(0.91 0.04 345); --color-accent: oklch(0.23 0.10 345); --color-border: oklch(0.82 0.05 345); }
.slidev-page-25 { --color-text: oklch(0.24 0.09 350); --color-text-muted: oklch(0.49 0.07 350); --color-text-subtle: oklch(0.64 0.06 350); --color-bg: oklch(0.93 0.03 350); --color-bg-muted: oklch(0.90 0.03 350); --color-accent: oklch(0.24 0.09 350); --color-border: oklch(0.81 0.04 350); }
.slidev-page-26 { --color-text: oklch(0.25 0.08 355); --color-text-muted: oklch(0.50 0.06 355); --color-text-subtle: oklch(0.65 0.05 355); --color-bg: oklch(0.92 0.02 355); --color-bg-muted: oklch(0.89 0.02 355); --color-accent: oklch(0.25 0.08 355); --color-border: oklch(0.80 0.03 355); }
.slidev-page-27 { --color-text: oklch(0.24 0.09 0); --color-text-muted: oklch(0.49 0.07 0); --color-text-subtle: oklch(0.64 0.06 0); --color-bg: oklch(0.93 0.03 0); --color-bg-muted: oklch(0.90 0.03 0); --color-accent: oklch(0.24 0.09 0); --color-border: oklch(0.81 0.04 0); }
.slidev-page-28 { --color-text: oklch(0.23 0.10 5); --color-text-muted: oklch(0.48 0.08 5); --color-text-subtle: oklch(0.63 0.07 5); --color-bg: oklch(0.94 0.04 5); --color-bg-muted: oklch(0.91 0.04 5); --color-accent: oklch(0.23 0.10 5); --color-border: oklch(0.82 0.05 5); }
.slidev-page-29 { --color-text: oklch(0.22 0.11 10); --color-text-muted: oklch(0.47 0.09 10); --color-text-subtle: oklch(0.62 0.08 10); --color-bg: oklch(0.95 0.05 10); --color-bg-muted: oklch(0.92 0.05 10); --color-accent: oklch(0.22 0.11 10); --color-border: oklch(0.83 0.06 10); }
.slidev-page-30 { --color-text: oklch(0.21 0.12 15); --color-text-muted: oklch(0.46 0.10 15); --color-text-subtle: oklch(0.61 0.09 15); --color-bg: oklch(0.96 0.06 15); --color-bg-muted: oklch(0.93 0.06 15); --color-accent: oklch(0.21 0.12 15); --color-border: oklch(0.84 0.07 15); }
.slidev-page-31 { --color-text: oklch(0.20 0.13 20); --color-text-muted: oklch(0.45 0.11 20); --color-text-subtle: oklch(0.60 0.10 20); --color-bg: oklch(0.97 0.07 20); --color-bg-muted: oklch(0.94 0.07 20); --color-accent: oklch(0.20 0.13 20); --color-border: oklch(0.85 0.08 20); }
.slidev-page-32 { --color-text: oklch(0.21 0.12 25); --color-text-muted: oklch(0.46 0.10 25); --color-text-subtle: oklch(0.61 0.09 25); --color-bg: oklch(0.96 0.06 25); --color-bg-muted: oklch(0.93 0.06 25); --color-accent: oklch(0.21 0.12 25); --color-border: oklch(0.84 0.07 25); }
.slidev-page-33 { --color-text: oklch(0.22 0.11 30); --color-text-muted: oklch(0.47 0.09 30); --color-text-subtle: oklch(0.62 0.08 30); --color-bg: oklch(0.95 0.05 30); --color-bg-muted: oklch(0.92 0.05 30); --color-accent: oklch(0.22 0.11 30); --color-border: oklch(0.83 0.06 30); }
.slidev-page-34 { --color-text: oklch(0.23 0.10 35); --color-text-muted: oklch(0.48 0.08 35); --color-text-subtle: oklch(0.63 0.07 35); --color-bg: oklch(0.94 0.04 35); --color-bg-muted: oklch(0.91 0.04 35); --color-accent: oklch(0.23 0.10 35); --color-border: oklch(0.82 0.05 35); }
</style>

---

# You can be productive with Xcode

<div class="quiet">and you know it</div>

<div style="margin-top: var(--space-2xl); color: var(--color-text-muted);">
A practical guide to fixing the stuff that actually slows you down
</div>

---

# Hi, I'm Pedro 👋

<div style="margin-top: var(--space-2xl); font-size: 1.15rem; line-height: 1.8;">

**Pedro Piñera Buendía**

Based in Berlin (originally from Murcia)

Builder turned founder with Tuist

Enjoy building dev tools

</div>

---

# What we'll cover

<div style="margin-top: var(--space-2xl);">

**💻 Development** — the stuff that happens on your machine

- Frequent merge conflicts
- Clean builds & derived data
- Architecture & build performance
- Non-determinism across environments

<div style="margin-top: var(--space-xl);"></div>

**🔄 Integration** — the stuff that happens on CI

- CI infrastructure constraints
- Caching strategies (dependencies, builds, registry)
- Remote caching solutions (Bazel, Tuist, Xcode)
- Test optimization (selective testing, parallelization, flakiness)

</div>

---
class: phase-intro
---

# 💻 Development

---

# Frequent Merge Conflicts ⚔️
## Xcode Projects

<div class="quiet">The `project.pbxproj` problem</div>

<div class="cols">

<div>

### The problem

Someone adds a file, someone else adds a file. `project.pbxproj` explodes.

Now you're doing archaeology in a 10,000 line XML-ish file instead of writing code.

Every team member has hit this. Multiple times a week.

</div>

<div>

### Stop editing it directly

**Use project generators/managers**
- Tuist, XcodeGen, or SwiftPM
- Generate from something humans can read
- Commit the definitions, not the generated project

**If you can't do that**
- Smaller, focused PRs
- Feature modules as separate projects

</div>

</div>

---

# Frequent Merge Conflicts ⚔️
## Buildable Folders

<div class="quiet">From N-to-N to 1-to-1</div>

<div class="cols">

<div>

### The idea

Reference entire folders instead of individual files.

**Traditional:**
- N files = N potential conflicts

**Buildable folders:**
- 1 folder = 1 potential conflict

Add or remove files without touching `project.pbxproj`.

</div>

<div>

### How to use

- Right-click folder → "Convert to folders"
- Files are automatically discovered
- No project changes for file additions/removals

**Note:** Conflicts don't disappear completely. You'll still get them for build settings, targets, or schemes.

</div>

</div>

<div style="position: fixed; bottom: 2rem; right: 3.5rem; width: 16px; height: 16px; background: var(--color-accent); border-radius: 50%; z-index: 1000; opacity: 0.8;"></div>

---

# Frequent Merge Conflicts ⚔️
## Monolith Files

<div class="quiet">The files everyone touches</div>

<div class="cols">

<div>

### Find your hotspots

AppDelegate. Router. Constants. Config files. Everyone touches them.

**Run this in your repo:**

```bash
git log --pretty=format: --name-only \
  | sort | uniq -c | sort -rn \
  | head -20
```

Shows your top 20 most-modified files.

</div>

<div>

### Split them up

**Break apart the monolith**
- Feature-based organization
- Dependency injection over singletons
- Configuration as separate modules

**For constants/config**
- Generate from build scripts
- Separate file per feature

</div>

</div>

---

# Clean Builds 🧹
## & Derived Data

<div class="quiet">Why it keeps breaking</div>

<div class="cols">

<div>

### What is derived data?

Xcode's cache. References files by absolute path.

Move project? Switch branches? Previews stop working.

### The consequence

"Have you tried cleaning derived data?"

This shouldn't be our "have you tried restarting it?"

</div>

<div>

### The real problem

Build graph links undeclared dependencies.

**Actual vs declared:**
- Actual: What code uses
- Declared: What project says

Mismatch → build system skips compiling dependencies it thinks aren't needed.

[bazel.build/concepts/dependencies](https://bazel.build/concepts/dependencies)

</div>

</div>

---

# Clean Builds 🧹
## How to fix it

<div class="quiet">Make incremental builds reliable</div>

<div class="cols">

<div>

### Build graph hygiene

**Clear module boundaries**
- Explicit dependencies only
- No circular dependencies

**What you import = what you depend on**

If you import something, declare it. If you don't import it, don't depend on it.

</div>

<div>

<div class="tip">

### Tip for Tuist users

You can detect undeclared dependencies:

```bash
tuist inspect implicit-imports
```

This shows where your code imports something that isn't declared as a dependency.

</div>

</div>

</div>

---

# Clean Builds 🧹
## A path away from derived data

<div class="quiet">Xcode 26's compilation cache</div>

<div class="cols">

<div>

### The evolution

Xcode 26 introduces **compilation cache** — moving from file-based (derived data) to hash-based storage.

Computes hermetic fingerprints instead of path-based references.

**Enable it:**
```
COMPILATION_CACHE_ENABLE_CACHING = YES
```

</div>

<div>

### Benefits

**More deterministic and reliable:**
- Explicit dependency graph
- Better task scheduling
- Works when switching branches
- Multiple repo copies share cache directory

Early feature, not all tasks cacheable yet.

</div>

</div>

<div style="position: fixed; bottom: 2rem; right: 3.5rem; width: 16px; height: 16px; background: var(--color-accent); border-radius: 50%; z-index: 1000; opacity: 0.8;"></div>

---

# Clean Builds 🧹
## Related build settings

<div class="quiet">Enabling compilation cache components</div>

<div class="cols">

<div>

### SWIFT_ENABLE_COMPILE_CACHE

Enables compilation caching for Swift compiler.

Works with `COMPILATION_CACHE_ENABLE_CACHING`.

### CLANG_ENABLE_COMPILE_CACHE

Enables compilation caching for Clang (C/Objective-C).

Works with `COMPILATION_CACHE_ENABLE_CACHING`.

</div>

<div>

### SWIFT_ENABLE_EXPLICIT_MODULES

Explicitly built modules (enabled by default in Xcode 26).

Required for compilation cache to work with Swift.

### SWIFT_USE_INTEGRATED_DRIVER

Modern Swift compiler driver.

Coordinates compilation tasks efficiently.

</div>

</div>

---

# Architecture & Build Performance 🏗️

<div class="quiet">Why your architecture choices matter</div>

<div class="cols">

<div>

### Three layers

**App** — Links everything together

**Features** — Independent modules with interface dependencies

**Core** — Shared utilities

</div>

<div>

### Depend on interfaces

Features depend on protocols, implementations injected at app level.

**Tradeoff:**
- Runtime DI overhead
- Worth it for build performance

**Why:**
- Changes don't cascade
- Features build in parallel

</div>

</div>

---

# Non-determinism 🎲
## Across Environments

<div class="quiet">The "works on my machine" special</div>

<div class="cols">

<div>

### What causes this

- Different Xcode versions
- Different Swift toolchain versions
- Different macOS versions
- Floating dependency versions

</div>

<div>

### Lock it down

**Version everything**
- `Package.resolved` for SPM
- Commit lockfiles

**Tooling**
- Use `mise` for version management
- `xcode-select -p` in scripts
- Verify environment in CI
- Fail fast if wrong version

</div>

</div>

<div style="position: fixed; bottom: 2rem; right: 3.5rem; width: 16px; height: 16px; background: var(--color-accent); border-radius: 50%; z-index: 1000; opacity: 0.8;"></div>

---
class: phase-intro
---

# 🔄 Integration

---

# Capped Parallelism ⚡
## CI Concurrency

<div class="quiet">Apple's licensing limits scale</div>

<div class="cols">

<div>

### The constraint

Apple's licensing: 24h min retention, 2 VMs max per host.

You can't elastically scale macOS runners like you can with Linux.

Your PR waits behind 12 others. Nobody's getting coffee today.

</div>

<div>

### Use runner providers

Companies that provide elastic capacity:

- Namespace.so (Buildkite)
- GitHub Actions
- MacStadium
- AWS EC2 Mac

They manage the licensing constraints and hardware pool.

</div>

</div>

<div style="position: fixed; bottom: 2rem; right: 3.5rem; width: 16px; height: 16px; background: var(--color-accent); border-radius: 50%; z-index: 1000; opacity: 0.8;"></div>

---

# Resource Contention 🏃‍♂️
## CI Performance

<div class="quiet">You can't isolate resources physically</div>

<div class="cols">

<div>

### The problem

Multiple builds share the same machine.

CPU, memory, disk I/O all compete.

Build times become unpredictable. Your 10-minute build takes 25 minutes.

</div>

<div>

### Dedicated instances

Providers with dedicated resources:

- Namespace.so (Buildkite)
- MacStadium (Orka)
- AWS EC2 Mac (Dedicated Hosts)

Eliminate resource contention for predictable build times.

</div>

</div>

---

# Not Fast Enough Hardware 🐌
## CI Speed

<div class="quiet">Limited to available Mac configurations</div>

<div class="cols">

<div>

### The limitation

You're constrained by:
- What machines you can buy
- What you can afford to keep running
- Depreciation and replacement cycles

Older hardware means slower builds.

Slower builds mean longer feedback loops.

</div>

<div>

### Latest hardware

Not all providers are fast to upgrade (e.g., Xcode Cloud).

Choose providers that maintain current hardware (M3, M4).

**Self-hosted:** You manage depreciation and replacement cycles. Few companies account for the true cost.

</div>

</div>

---

# Dependency & Tool Caching 📦
## Pipeline Optimization

<div class="quiet">Don't reinstall what hasn't changed</div>

<div class="cols">

<div>

### The waste

Typical pipeline steps:

1. Install toolchain (Homebrew, mise)
2. Install dependencies (SPM)
3. Run action (build, test)

Without caching, steps 1 and 2 run every time, adding minutes even when nothing changed.

</div>

<div>

### Cache everything

**Toolchain:**
- Homebrew packages
- mise installations

**Dependencies:**
- SPM: Cache `.build` and DerivedData

**Cache keys:** Lock files, tool versions, OS version.

</div>

</div>

---

# Cache Performance 💾
## Storage Matters

<div class="quiet">Remote vs local storage</div>

<div class="cols">

<div>

### Two approaches

**Remote cache (S3):** API calls, network overhead.

**Mounted volumes:** Filesystem access, faster.

Both shareable across runners.

</div>

<div>

### Prefer mounted volumes

Faster with direct filesystem I/O.

Not all runner services provide them.

Fall back to remote cache when unavailable.

</div>

</div>

---

# SwiftPM Cache Optimization 📦
## Reduce cache size

<div class="quiet">This approach doesn't work reliably</div>

SwiftPM downloads include .git directories.

These add significant size to your cache.

Remote cache becomes slower to upload/download.

**Removing .git doesn't work reliably** — SwiftPM may re-download packages.

---

# Tuist Registry 🚀
## Faster dependency resolution

<div class="quiet">Package registry for SwiftPM</div>

<div class="cols">

<div>

### What it provides

- Only download commits you need
- No full git history
- Global edge storage (low latency)
- Access to Swift Package Index
- Faster dependency resolution

</div>

<div>

### Setup

```bash
tuist registry setup
tuist registry login
```

<div class="tip">

### A gift for the community

Becoming available without account in the following weeks.

</div>

[docs.tuist.dev/guides/features/registry](https://docs.tuist.dev/en/guides/features/registry)

</div>

</div>

<div style="position: fixed; bottom: 2rem; right: 3.5rem; width: 16px; height: 16px; background: var(--color-accent); border-radius: 50%; z-index: 1000; opacity: 0.8;"></div>

---

# Build Process Caching 💾
## Remote Cache

<div class="quiet">Skip build steps by fetching outputs from network</div>

<div class="cols">

<div>

### How it works

Instead of rebuilding, fetch cached outputs from network.

**Requires hermetism:**
- No side effects
- Same inputs = same outputs
- Deterministic builds
- Inputs can be hashed

Without hermetism, cache is unreliable.

</div>

<div>

### Implementation

**Process:**
- Hash all inputs (source + dependencies)
- Check remote cache for match
- Download artifacts or build + upload

**Solutions:**
- Bazel
- Module cache (Tuist)
- Xcode cache

**Prerequisite:** Clean dependency graph.

</div>

</div>

---

# Bazel ⚙️
## Action-based caching

<div class="quiet">Replaces Xcode build system</div>

<div class="cols">

<div>

### How it works

Breaks build into discrete actions (inputs, outputs, command).

**Cache:**
- Action cache (AC): hash → result
- Content storage (CAS): output files

Checks AC, downloads from CAS if available.

</div>

<div>

### Tradeoffs

**Pros:**
- Very granular (action-level)
- Fast (up to 3x)
- Mature tooling

**Cons:**
- Steep learning curve
- Replaces Xcode build system
- Migration effort required

**Best for:** Large teams with infrastructure investment.

</div>

</div>

---

# Module Cache (Tuist) 📦
## Target-level caching

<div class="quiet">Works with Xcode build system</div>

<div class="cols">

<div>

### How it works

Caches entire frameworks/libraries at module-level.

Pre-fetches binaries, replaces unchanged targets with pre-compiled versions.

Developers use Xcode normally.

</div>

<div>

### Tradeoffs

**Pros:**
- Keep using Xcode
- Faster than Xcode 26 cache
- Easier adoption than Bazel

**Cons:**
- Coarse-grained (module-level)
- Requires modular architecture
- Needs Tuist project generation

**Best for:** Teams using or open to Tuist.

</div>

</div>

<div style="position: fixed; bottom: 2rem; right: 3.5rem; width: 16px; height: 16px; background: var(--color-accent); border-radius: 50%; z-index: 1000; opacity: 0.8;"></div>

---

# Xcode Cache 💾
## Native compilation cache

<div class="quiet">Xcode 26 built-in feature</div>

<div class="cols">

<div>

### How it works

Caches compilation outputs (object files, modules).

Detects same inputs + settings, retrieves from cache.

**Enable:**
```
COMPILATION_CACHE_ENABLE_CACHING = YES
```

Hash-based, not path-based.

</div>

<div>

### Tradeoffs

**Pros:**
- Native, easy to enable

**Cons:**
- ~30% improvement (limited)
- Limited task support
- No SPM dependencies yet
- Still early

**Best for:** Minimal setup with native tooling.

</div>

</div>

<div style="position: fixed; bottom: 2rem; right: 3.5rem; width: 16px; height: 16px; background: var(--color-accent); border-radius: 50%; z-index: 1000; opacity: 0.8;"></div>

---

# The Future of Caching 🔮
## Our vision

<div class="quiet">Bringing cache closer to you</div>

<div class="cols">

<div>

**Latency & bandwidth matter:**
- Latency: Checking if there's a cached result
- Bandwidth: Downloading the output

**Beyond CI:**

CI providers solve this for CI environments.

We want to solve it for **all environments**: local, CI, and agentic.

</div>

<div>

**Our approach:**
- Cache servers in your offices & regions
- Exploring P2P cache
- Slicing technology & service ([Fabrik](https://github.com/tuist/fabrik))
- Works with any build system

Bringing the cache as close to you as possible.

</div>

</div>

---

# Selective Test Execution 🎯
## Smart Testing

<div class="quiet">Run only what's affected</div>

<div class="cols">

<div>

### The problem

Changed one file? Running 2,000 tests anyway.

Most tests are unrelated to your changes.

Wastes time and money.

</div>

<div>

### Solutions

**Graph-based selection:**
- Analyze dependency graph
- Find affected modules
- Run only impacted tests

**Tools:**
- [Tuist Selective Testing](https://docs.tuist.dev/en/guides/develop/test/run#selective-testing)
- [mikeger/XcodeSelectiveTesting](https://github.com/mikeger/XcodeSelectiveTesting)
- Custom git diff scripts

**Strategy:** Selective on PRs, full suite on main.

</div>

</div>

---

# Test Parallelization ⚡
## Running tests faster

<div class="quiet">Maximize concurrency</div>

<div class="cols">

<div>

### Parallelization strategies

**Within environment:**
- Use scheme/test plan parallelization
- Multiple tests run on same machine

**Across environments:**
- Build without testing
- Distribute and test without building
- Split tests across multiple runners

</div>

<div>

### Trade-offs & future

**Warning:**

Parallelization can expose flakiness (e.g., mutating global state, shared resources).

**Coming soon:**

Tuist is bringing dynamic sharding for smarter test distribution.

</div>

</div>

---

# Test Flakiness 🎲

<div class="quiet">The build was red, now it's green, nobody changed anything</div>

<div class="cols">

<div>

### Common causes

Timing issues, race conditions, shared state, network calls, animations.

The test suite is lying to you.

</div>

<div>

### Solutions

**Isolation:**
- No shared state
- Scoped state (use task locals)

**Determinism:**
- Mock network
- Stub external services
- Control time/dates

**UI tests:** Wait for conditions, not time.

</div>

</div>

---

# What matters 🎯

<div class="cols">

<div>

**💻 Development phase**
- Project generators eliminate Xcode project conflicts
- Split monolith files to reduce merge conflicts
- Clean module boundaries enable incremental builds
- Compilation cache (Xcode 26) moves away from DerivedData
- Version locking ensures consistency

</div>

<div>

**🔄 Integration phase**
- Use runner providers to manage CI constraints
- Cache smartly: dependencies, builds (choose: Bazel/Tuist/Xcode)
- Optimize SwiftPM: remove .git, use Tuist Registry
- Selective testing + parallelization maximize efficiency
- Isolated tests prevent flakiness

</div>

</div>

<div style="margin-top: var(--space-xl);">

The common thread? **Architecture**. Good project structure makes everything else easier.

</div>

---

# One more thing 🤖

<div class="quiet">Agentic coding tools</div>

<div class="cols">

<div>

### The opportunity

Agentic coding tools can produce code faster than ever.

**The challenges:**
- Multiple project copies
- Context window limits
- Xcode project modifications
- File additions/removals

</div>

<div>

### Set yourself up

**Compile cache** for multiple copies:
- Use `COMPILATION_CACHE_ENABLE_CACHING`
- Share cache directory across copies

**Filter build noise:**
- [xcsift](https://github.com/ldomaradzki/xcsift) filters xcodebuild output

**Help agents CRUD projects:**
- Buildable folders for file changes
- [xcodeproj-mcp-server](https://github.com/giginet/xcodeproj-mcp-server) for project edits

</div>

</div>

---

# Thank you 🙏

<div style="margin-top: var(--space-2xl); font-size: 1.25rem; line-height: 1.8;">

**Questions? 💬**

<div style="margin-top: var(--space-xl); color: var(--color-text-muted);">

Pedro Piñera Buendía

[@pepicrft](https://x.com/pepicrft) · [tuist.dev](https://tuist.dev) · pedro@tuist.dev

</div>

</div>

---

# You can be productive with Xcode

<div style="margin-top: var(--space-2xl); color: var(--color-text-muted); font-size: 1.25rem;">
You just have to set it up right
</div>
