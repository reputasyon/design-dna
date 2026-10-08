---
id: 2026-10-09-mise-today-dashboard
source: Mise (restaurant prep planner, concept)
platform: web
tags: [light, dashboard, ai-ux, sidebar, onboarding, kpi, table, data-viz]
focus: (tahmin) the full app shell — calm operational "Today" dashboard
added: 2026-10-09
---

## What makes it work
- **KPI cards always carry context.** Big number (~32px, regular weight) + unit in muted
  small text, then a footer row: delta chip (green check-circle "+6%") left, comparison
  baseline right ("vs a typical Monday"). Never a naked number.
- **Each KPI has a tinted icon tile** (blue, neutral, orange) at the top-left — the only
  place category color appears; the rest of the card is neutral.
- **Table rows as soft cards.** Each row is its own rounded tile with a 56px food photo,
  two-line item (title + muted "station · owner"), priority pill with colored dot,
  quantity with a thin progress bar under it ("32 kg done"), due time + relative time.
- **CTA style follows state.** Not started → dark filled "Start"; in progress → outlined
  "Continue"; finished → green tinted "✓ Done" chip. Urgency is red text under the time
  ("Running late"), not a red button.
- **"Needs attention" feed = problem + reason + one action.** Each item: tinted icon,
  bold one-line problem, 1-2 muted lines of why, a text link with chevron ("Add to prep ›").
  The AI suggestion lives here as a normal item with the AI accent icon.
- **Dot-matrix chart.** Covers-by-hour drawn as a grid of tiny dots; served vs forecast
  in two colors, with a big "13 served so far, forecast was 11" headline above.
- **Segmented filter bar** (date chip + All / Hot line / Cold station / Bakery) with
  "Updated 11:40 AM" right-aligned in muted text.

## Measurable values
- palette (approx): #E9E9E9 outer bg, #F5F5F4 shell, #FFFFFF cards, #1A1A1A primary
  button/text, #8A8A8A meta, #2F6FD6 blue, #F0A15A orange, #2E9E5B green, #D9342B red
- radius: ~8px buttons/pills, ~14px row tiles and KPI cards, ~20px shell panels
- type: sans; KPI 32px regular, section titles 17-18px medium, rows 16/13px
- progress bars: ~4px tall, rounded, black in progress, green when complete
- borders: none on rows; 1px hairline only on outlined buttons and pills
- header: one dark primary ("Open prep board") + one white secondary ("Log waste")

## Steal this
- Every metric gets a baseline ("vs …") and a delta; every alert gets a reason and one action link.
- Encode row state in the button (Start / Continue / Done), and keep urgency in text color.
