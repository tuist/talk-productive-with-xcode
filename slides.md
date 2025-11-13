---
theme: default
background: '#f5f5f7'
title: You can be productive with Xcode, and you know it
class: text-center
drawings:
  persist: false
transition: slide-left
mdc: true
duration: 35min
fonts:
  sans: 'SF Pro Display, system-ui, -apple-system, sans-serif'
  mono: 'SF Mono, Menlo, Monaco, monospace'
---

<style>
/* Global Apple-inspired styles */
:root {
  --apple-blue: #007AFF;
  --apple-purple: #AF52DE;
  --apple-pink: #FF2D55;
  --apple-orange: #FF9500;
  --apple-gray: #1d1d1f;
  --apple-light-gray: #f5f5f7;
}

.slidev-layout {
  padding: 3rem 4rem 2rem 4rem !important;
  background: var(--apple-light-gray);
}

/* Typography */
h1 {
  font-size: 2.5rem !important;
  font-weight: 700 !important;
  letter-spacing: -0.03em !important;
  line-height: 1.1 !important;
  margin-bottom: 0.75rem !important;
  color: var(--apple-gray) !important;
}

h2 {
  font-size: 1.25rem !important;
  font-weight: 600 !important;
  letter-spacing: -0.02em !important;
  margin-bottom: 0.5rem !important;
  color: var(--apple-gray) !important;
}

h3 {
  font-size: 1.1rem !important;
  font-weight: 600 !important;
  letter-spacing: -0.01em !important;
  margin-bottom: 0.4rem !important;
}

/* Apple glass card effect */
.apple-card {
  background: rgba(255, 255, 255, 0.8);
  backdrop-filter: saturate(180%) blur(20px);
  border-radius: 16px;
  border: 1px solid rgba(0, 0, 0, 0.06);
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
  padding: 1.25rem;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.apple-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 15px 50px rgba(0, 0, 0, 0.12);
}

/* Gradient text */
.gradient-text {
  background: linear-gradient(135deg, var(--apple-blue), var(--apple-purple));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

/* Badge */
.apple-badge {
  display: inline-block;
  padding: 0.35rem 1rem;
  background: var(--apple-blue);
  color: white;
  border-radius: 100px;
  font-size: 0.9rem;
  font-weight: 500;
  letter-spacing: 0.01em;
}

/* Subtitle */
.subtitle {
  font-size: 0.9rem;
  color: #86868b;
  font-weight: 400;
  letter-spacing: -0.01em;
  margin-top: 0.4rem;
}

/* List styling */
.slidev-layout li {
  margin: 0.4rem 0;
  line-height: 1.5;
  color: var(--apple-gray);
  font-size: 0.95rem;
}

.slidev-layout ul {
  list-style: none;
  padding-left: 0;
}

.slidev-layout li::before {
  content: "•";
  color: var(--apple-blue);
  font-weight: bold;
  display: inline-block;
  width: 1.3em;
  font-size: 1em;
}

/* Code styling */
code {
  background: rgba(0, 122, 255, 0.1) !important;
  color: var(--apple-blue) !important;
  padding: 0.2em 0.5em !important;
  border-radius: 6px !important;
  font-family: 'SF Mono', monospace !important;
  font-size: 0.9em !important;
}

/* Phase divider */
.phase-divider {
  width: 60px;
  height: 5px;
  background: linear-gradient(90deg, var(--apple-blue), var(--apple-purple));
  border-radius: 100px;
  margin: 2rem auto;
}

/* Column layouts */
.two-column {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
  margin-top: 1rem;
}

.three-column {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 1.5rem;
  margin-top: 1rem;
}

/* Hero section */
.hero-section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
  text-align: center;
}

/* Feature icon */
.feature-icon {
  font-size: 2.5rem;
  margin-bottom: 0.75rem;
  display: block;
}

/* Problem-solution layout */
.problem-box {
  background: linear-gradient(135deg, rgba(255, 45, 85, 0.1), rgba(255, 149, 0, 0.1));
  border-left: 4px solid var(--apple-pink);
  padding: 1rem;
  border-radius: 12px;
  margin: 1rem 0;
}

.solution-box {
  background: linear-gradient(135deg, rgba(0, 122, 255, 0.1), rgba(175, 82, 222, 0.1));
  border-left: 4px solid var(--apple-blue);
  padding: 1rem;
  border-radius: 12px;
  margin: 1rem 0;
}

/* Section header */
.section-header {
  text-align: center;
  margin-bottom: 1.5rem;
}

.section-header h1 {
  margin-bottom: 0.5rem;
}

/* Content spacing */
.content-wrapper {
  margin-top: 2rem;
}

/* Make sure content doesn't overlap with controls */
.slidev-layout {
  overflow-y: auto;
}
</style>

<div class="hero-section">

# You can be productive<br>with Xcode

<div class="subtitle" style="font-size: 1.5rem; margin-top: 1.5rem; margin-bottom: 2rem;">
and you know it
</div>

<div class="apple-badge">A practical guide to avoiding common pitfalls</div>

</div>

---

<div class="hero-section">

<div class="section-header">

# The Journey

<div class="phase-divider"></div>

</div>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; max-width: 900px; width: 100%;">

<div class="apple-card" style="text-align: center;">
  <div class="feature-icon">🔨</div>
  <h3 style="color: var(--apple-blue);">Development</h3>
  <p class="subtitle">Local workflow optimization</p>
</div>

<div class="apple-card" style="text-align: center;">
  <div class="feature-icon">🔄</div>
  <h3 style="color: var(--apple-purple);">Integration</h3>
  <p class="subtitle">CI/CD efficiency</p>
</div>

</div>

</div>

---
layout: center
---

<div style="text-align: center;">

<div class="feature-icon">🔨</div>

# <span class="gradient-text">Phase 1: Development</span>

<p class="subtitle" style="font-size: 1.25rem; margin-top: 1rem;">Mastering your local workflow</p>

</div>

---

<div class="section-header">

# Frequent Git Conflicts

<div class="subtitle">The Xcode project file curse</div>

</div>

<div class="two-column">

<div class="problem-box">

## The Problem

- `project.pbxproj` is a merge nightmare
- Adding files causes conflicts
- Build settings changes collide
- Team velocity suffers

</div>

<div class="solution-box">

## Solutions

<v-clicks>

- **Use project generators**
  - Tuist, XcodeGen, or SwiftPM
  - Generate from declarative configs
  - No more manual project edits

- **Adopt modular architecture**
  - Multiple smaller projects
  - Reduced conflict surface

</v-clicks>

</div>

</div>

---

<div class="section-header">

# Clean Builds & Derived Data

<div class="subtitle">Breaking the CMD+SHIFT+K habit</div>

</div>

<div class="two-column">

<div>

<h3 style="color: var(--apple-pink);">Why it happens</h3>

<v-clicks>

- Incremental build cache corruption
- Xcode indexing issues
- Build system inconsistencies
- "It works after clean build"

</v-clicks>

</div>

<div>

<h3 style="color: var(--apple-blue);">Better approaches</h3>

<v-clicks>

- **Stable build graphs**
  - Well-defined dependencies
  - Avoid circular deps
  - Explicit imports

- **Build system optimization**
  - New build system
  - Proper declarations

- **Automation**
  - CI validates clean builds
  - Local incremental builds

</v-clicks>

</div>

</div>

---

<div class="section-header">

# Non-determinism Across Environments

<div class="subtitle">Works on my machine syndrome</div>

</div>

<div class="two-column">

<div>

<h3 style="color: var(--apple-pink);">Root causes</h3>

<v-clicks>

- Xcode version mismatches
- Different simulator runtimes
- macOS version differences
- Environment-specific configs
- Floating dependency versions

</v-clicks>

</div>

<div>

<h3 style="color: var(--apple-blue);">Solutions</h3>

<v-clicks>

- **Version locking**
  - `.xcode-version` file
  - SPM Package.resolved
  - CocoaPods Podfile.lock

- **Environment management**
  - mise/asdf for tool versions
  - Consistent Xcode selection

- **Validation**
  - Setup verification scripts
  - Environment checks in CI

</v-clicks>

</div>

</div>

---
layout: center
---

<div style="text-align: center;">

<div class="feature-icon">🔄</div>

# <span class="gradient-text">Phase 2: Integration</span>

<p class="subtitle" style="font-size: 1.25rem; margin-top: 1rem;">Optimizing your CI/CD pipeline</p>

</div>

---

<div class="section-header">

# Limited CI Concurrency

<div class="subtitle">Making the most of your runners</div>

</div>

<div class="two-column">

<div>

<h3 style="color: var(--apple-pink);">The challenge</h3>

<v-clicks>

- Expensive macOS runners
- Long queue times
- Sequential test execution
- Bottlenecked deployments

</v-clicks>

</div>

<div>

<h3 style="color: var(--apple-purple);">Optimization strategies</h3>

<v-clicks>

- **Smart parallelization**
  - Split tests across runners
  - Matrix strategies

- **Selective execution**
  - Run only affected tests
  - Skip unchanged modules

- **Resource efficiency**
  - Cache aggressively
  - Reuse build artifacts

</v-clicks>

</div>

</div>

---

<div class="section-header">

# Test Flakiness

<div class="subtitle">The red build that turns green on retry</div>

</div>

<div class="two-column">

<div>

<h3 style="color: var(--apple-pink);">Common culprits</h3>

<v-clicks>

- Timing-dependent tests
- Shared state between tests
- Network/external dependencies
- UI test instability
- Race conditions

</v-clicks>

</div>

<div>

<h3 style="color: var(--apple-purple);">Remedies</h3>

<v-clicks>

- **Test isolation**
  - Independent test cases
  - Proper setup/teardown
  - No shared mutable state

- **Deterministic testing**
  - Mock network calls
  - Stub external services

- **UI test stability**
  - Proper wait conditions
  - Accessibility identifiers

</v-clicks>

</div>

</div>

---

<div class="section-header">

# Slow CI

<div class="subtitle">Every second counts</div>

</div>

<div class="three-column" style="margin-top: 1.5rem;">

<div class="apple-card">

<h3 style="color: var(--apple-blue); font-size: 1.25rem;">Build speed</h3>

<v-clicks>

- **Incremental builds**
  - Modular architecture
  - Explicit dependencies

- **Compilation**
  - Parallel build jobs
  - Whole module opt.

</v-clicks>

</div>

<div class="apple-card">

<h3 style="color: var(--apple-purple); font-size: 1.25rem;">Caching</h3>

<v-clicks>

- **Dependencies**
  - SPM/CocoaPods cache
  - Homebrew packages

- **Build artifacts**
  - Derived data
  - Binary frameworks

</v-clicks>

</div>

<div class="apple-card">

<h3 style="color: var(--apple-pink); font-size: 1.25rem;">Infrastructure</h3>

<v-clicks>

- **Runner optimization**
  - Larger machines
  - Pre-warmed images

- **Pipeline design**
  - Fail fast
  - Parallel jobs

</v-clicks>

</div>

</div>

---

<div class="hero-section">

<div class="section-header">

# Key Takeaways

<div class="phase-divider"></div>

</div>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; max-width: 1000px; text-align: left; margin-top: 2rem;">

<div class="apple-card">

<h3 style="color: var(--apple-blue);">Development</h3>

<v-clicks>

- Use project generators
- Build modular architectures
- Lock your dependencies
- Automate environment setup

</v-clicks>

</div>

<div class="apple-card">

<h3 style="color: var(--apple-purple);">Integration</h3>

<v-clicks>

- Parallelize everything possible
- Cache aggressively
- Isolate and stabilize tests
- Monitor and iterate

</v-clicks>

</div>

</div>

<v-click>

<div style="margin-top: 3rem; text-align: center;">
<div class="apple-badge" style="background: linear-gradient(135deg, var(--apple-blue), var(--apple-purple)); font-size: 1.1rem; padding: 0.5rem 1.5rem;">
Invest in architecture
</div>
<p class="subtitle" style="margin-top: 1rem;">Good project structure pays dividends everywhere</p>
</div>

</v-click>

</div>

---
layout: center
---

<div class="hero-section">

# <span class="gradient-text">You can be productive<br>with Xcode</span>

<p class="subtitle" style="font-size: 1.5rem; margin-top: 2rem; margin-bottom: 3rem;">
And now you have the tools to prove it
</p>

<div class="phase-divider"></div>

<p class="subtitle" style="margin-top: 3rem;">Thank you</p>

</div>
