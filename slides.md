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
  /* Colors */
  --color-text: #1a1a1a;
  --color-text-muted: #666;
  --color-text-subtle: #999;
  --color-bg: #ffffff;
  --color-bg-muted: #fafafa;
  --color-accent: #1a1a1a;
  --color-border: #eee;

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
  background: #f0f9ff;
  border-left: 4px solid #0284c7;
  padding: var(--space-md);
  border-radius: var(--radius);
  margin: var(--space-md) 0;
}

.tip h3 {
  margin-top: 0;
  color: #0284c7;
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
</style>

---

# You can be productive with Xcode

<div class="quiet">and you know it</div>

<div style="margin-top: var(--space-2xl); color: var(--color-text-muted);">
A practical guide to fixing the stuff that actually slows you down
</div>

---

# Hi, I'm Pedro

<div style="margin-top: var(--space-2xl); font-size: 1.15rem; line-height: 1.8;">

**Pedro Piñera Buendía**

Based in Berlin (originally from Murcia)

Builder turned founder with Tuist

Enjoy building dev tools

</div>

---

# Two phases, seven problems

<div style="margin-top: var(--space-2xl);">

**Development** — the stuff that happens on your machine

- Frequent merge conflicts
- Clean builds you shouldn't need
- Architecture & build performance
- "Works on my machine" moments

<div style="margin-top: var(--space-xl);"></div>

**Integration** — the stuff that happens on CI

- CI queues that waste your time
- Flaky tests that waste everyone's time
- Slow builds that waste company money

</div>

---
class: phase-intro
---

# Development

---

# Frequent Merge Conflicts
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

# Frequent Merge Conflicts
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

---

# Frequent Merge Conflicts
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

# Clean Builds
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

# Clean Builds
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

# Clean Builds
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

---

# Clean Builds
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

# Architecture & Build Performance

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

# Non-determinism
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

---
class: phase-intro
---

# Integration

---

# Limited
## CI Concurrency

<div class="quiet">Or: why our PRs take 2 hours</div>

<div class="cols">

<div>

### The constraints

macOS runners are expensive. There aren't many of them. Everyone wants them.

Your PR is stuck behind 12 other PRs and nobody's getting coffee today.

</div>

<div>

### Make the most of it

**Parallelize intelligently**
- Run tests in parallel (really)
- Split schemes across runners
- Matrix builds for multi-platform

**Don't run what you don't need**
- Affected tests only
- Skip unchanged modules
- Different strategies per branch

**Cache everything**
- SPM dependencies
- CocoaPods
- Homebrew
- Build artifacts if you can

</div>

</div>

---

# Test Flakiness

<div class="quiet">The build was red, now it's green, nobody changed anything</div>

<div class="cols">

<div>

### Usually it's one of these

Timing issues. Race conditions. Tests that touch each other's state. Network calls. Animations you're not waiting for.

The test suite is lying to you and you can't trust it anymore.

</div>

<div>

### Stop the lying

**Isolation**
- Tests should not share state
- Real setup/teardown
- No global mutable state

**Determinism**
- Mock the network
- Stub external services
- Control time and dates

**UI tests**
- Wait for conditions, not for time
- Use accessibility identifiers
- Never use `sleep()`

**Track it**
- Note which tests flake
- Run them multiple times in CI
- Fix or delete them

</div>

</div>

---

# Slow CI

<div class="quiet">Every second costs actual money</div>

<div class="grid-3">

<div class="box">

### Build speed

**Go modular**
- Smaller compilation units
- Explicit dependencies
- Hide implementation details

**Compiler settings**
- Whole module optimization
- Parallelize builds
- Use the build timeline

</div>

<div class="box">

### Caching strategy

**Dependencies**
- Cache SPM packages
- Cache CocoaPods
- Cache system tools

**Artifacts**
- Cache build outputs
- Binary frameworks
- Remote caching (Tuist Cache)

</div>

<div class="box">

### Infrastructure

**Better runners**
- Larger machines
- Pre-warmed images
- Local runner caches

**Smarter pipeline**
- Fail fast on errors
- Run fast tests first
- Parallel job execution

</div>

</div>

---

# What matters

<div style="margin-top: var(--space-xl);">

**Development phase**
- Project generators eliminate Xcode project conflicts
- Split monolith files to reduce merge conflicts
- Clean module boundaries enable incremental builds
- Modular architecture prevents build issues
- Version locking ensures consistency

<div style="margin-top: var(--space-xl);"></div>

**Integration phase**
- Parallelization maximizes limited resources
- Aggressive caching reduces redundant work
- Isolated tests prevent flakiness

<div style="margin-top: var(--space-xl);"></div>

The common thread? **Architecture**. Good project structure makes everything else easier.

</div>

---

# You can be productive with Xcode

<div style="margin-top: var(--space-2xl); color: var(--color-text-muted); font-size: 1.25rem;">
You just have to set it up right
</div>
