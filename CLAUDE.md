# Engaging Starters

A static, teacher-facing site of five-minute classroom starter games, grouped
by subject (Maths, Science, English, Humanities). No build step, no backend.
Every game is a single self-contained HTML file: inline `<style>`, vanilla JS
in an IIFE, diagrams/charts drawn as inline SVG generated on demand (see
`subjects/maths/games/angle-estimator.html` or `misleading-graphs.html` for
the pattern) rather than pulled from a library or preloaded assets. Shared
look and feel — fonts, colours, `.board`/`.panel`/`.game-row` layout — lives
in the root `style.css`; page-specific styles stay in that page's own
`<style>` block.

## How to build a new game

**Design it with the user before writing code.** Don't go off and build a
full first version solo and treat their reaction as a change-request queue —
talk through the shape of the game first, the way you'd scope any feature,
and only start implementing once you've got a shared, agreed design.

That conversation should settle things like:
- Scope — how many rounds/items, how content is generated (procedural/on
  demand, like every game so far) vs. any preloaded data it needs
- The interaction model — what the player actually does each round, and how
  right/wrong is judged
- Where it lives — which subject, and how it's framed on that subject's
  index page
- Scoring/feedback shape — pass/fail, points, tiers, etc.

Use judgement about how much back-and-forth a given request needs — a small,
well-specified tweak to an existing game doesn't need this treatment — but
for a new game, default to a short design discussion (a few targeted
questions, not an exhaustive spec) before the first line of code, the way
"Spot the Misleading Graph" was scoped.

## Conventions worth matching

- Register every new game on its subject's `index.html` (`game-row` entry,
  numbered, plus updating the activity count in the header) and, if it
  changes the count, nowhere else needs touching.
- Reuse the shared CSS variables (`--maths`, `--science`, etc.) rather than
  introducing new colours.
- No external chart/diagram libraries — inline SVG built from template
  strings, matching the rest of the codebase.
