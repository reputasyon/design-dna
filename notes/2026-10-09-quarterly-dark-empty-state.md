---
id: 2026-10-09-quarterly-dark-empty-state
source: Quarterly (UK sole-trader tax app, concept)
platform: web
tags: [dark, dashboard, empty-state, onboarding, sidebar, choice-cards, microcopy]
focus: the dark palette — layered charcoals, hairlines, muted text, single accent
added: 2026-10-09
---

## What makes it work
- **Layered near-blacks, no pure black panels.** Outer bg, sidebar, main panel and cards
  are 3-4 close charcoal steps; separation by tone + 1px low-contrast hairline.
- **Empty state as a decision, not a void.** Centered headline + one reassuring line
  ("you can add the other later"), then two equal choice cards: tinted icon tile,
  title, one-sentence explanation, 3-item check list of benefits, one button each.
  Recommended path = filled accent; alternative = outlined neutral.
- **Trust-building microcopy.** Explains the scary part up front ("read-only… never
  move money"), and a calm footer line: deadline + "There is plenty of time."
- **Subtle dotted-grid canvas** behind the empty state gives texture without noise.
- **Sidebar bottom card for the next deadline** (date big, "31 days left · 2 updates to
  send", ghost "Preview update" button) — same persistent-card idea as Mise onboarding.
- **Status at a glance:** green "connected" pill in the welcome header, green dot next
  to a live connection, last-sync time right-aligned on the other.
- Uppercase small section labels in the sidebar (INCOME SOURCES, CONNECTIONS) with
  collapse chevrons; `⌘K` search pill in the top bar; one accent "Capture" CTA.

## Measurable values
- palette (approx): #2B2B2B outer, #0E0E10 sidebar, #141417 main, #1A1A1E cards,
  #2A2A2F hairline, #F2F2F2 text, #8E8E93 muted, #6E56F5 accent violet,
  #3DD68C success green, #F0A15A orange (icon tile)
- icon tiles: ~48px, ~10px radius, accent at ~15% opacity bg + full-color glyph
- radius: ~8px buttons/inputs, ~14px cards, ~16-20px panels
- type: sans; welcome 28px regular, empty-state headline ~28px, card title 18px medium,
  body 14px muted; section labels 12px uppercase, +8% tracking
- buttons: filled accent primary, outlined (1px hairline) secondary, ghost in sidebar card

## Steal this
- Turn empty states into 2 clearly-explained choices with benefits, one recommended.
- Answer the user's fear in the copy before they ask (permissions, deadlines, undo).
