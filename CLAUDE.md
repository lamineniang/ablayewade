# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A single-file static HTML tribute page celebrating Abdoulaye Wade (1926–2026), former President of Senegal. No build system, no dependencies, no server required — open `index.html` directly in a browser.

## Running the Project

```
start index.html        # Windows: open in default browser
python -m http.server   # Optional: serve locally on port 8000
```

## Architecture

Everything lives in a single `index.html` file with embedded `<style>` and `<script>` blocks.

**Design system** uses CSS custom properties tied to Senegal's national colors:
- `--vert` (#00853F), `--or` (#FDEF42), `--rouge` (#E31E24), `--noir` (#1A1A1A), `--creme` (#FDF8EE), `--sable` (#F0E9D2)

**Page sections** (by anchor ID):
- `#hero` — Full-screen intro with animated stripe background and key statistics
- `#intro` — Portrait and biographical overview
- `#timeline` — Filterable 100-year chronology (categories: Jeunesse, Opposition, Pouvoir, Réalisations, Chute)
- `#realisations` — Six achievement cards (infrastructure, education, healthcare, law)
- `#citations` — Tabbed quote carousel (Wade, African leaders, philosophers, morals, spirituality)
- `#lecons` — Tabbed life lessons (resilience, ambition, knowledge, leadership, errors)
- `#parcours` — 5-phase life journey stepper
- Fixed nav with scroll-tracking active state

**JavaScript** (inline, four functions + one scroll listener):
- `filterTL(cat, btn)` — Timeline category filter
- `showCit(id, btn)` — Citation carousel tab switcher
- `showLecon(id, btn)` — Life lesson tab switcher
- `showPV(idx, btn)` — Life journey phase stepper

**Responsive** breakpoint at 768px; fluid typography via `clamp()`.

Typography: Playfair Display (headings/quotes) and Source Sans 3 (body) loaded from Google Fonts.
