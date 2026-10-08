# Design Language

> Distilled from a private archive of UI references. Text-only by design: feed this file
> to any LLM (CLAUDE.md, Cursor rules, system prompt) before it builds UI.
> Each principle cites the reference notes in `notes/` that support it.

_Status: seed — 3 references (2 products). **(provisional)** = single reference, not yet called out by the owner; unmarked = owner explicitly endorsed._

## Principles

### 1. Greyscale UI, color only means something
- Do: build surfaces from stepped warm off-whites; use color only for status (AI/info, urgent, success, edited).
- Do: category color only in small tinted icon tiles; urgency as red text, not red buttons.
- Don't: tint panels or buttons for decoration.
- Refs: 2026-10-08-mise-chef-review, 2026-10-09-mise-today-dashboard

### 2. AI is a visible collaborator
- Do: label AI suggestions with one consistent accent chip; let the agent speak in short first-person sentences; show when the user overrode it and by how much.
- Do: surface AI suggestions inside normal work feeds with a one-click action ("Add to prep ›").
- Don't: hide AI changes or present them as system facts.
- Refs: 2026-10-08-mise-chef-review, 2026-10-09-mise-today-dashboard

### 3. Show the change, not the value
- Do: render edits as `old → new unit`; give every metric a delta and a baseline ("vs a typical Monday").
- Don't: show a naked number.
- Refs: 2026-10-08-mise-chef-review, 2026-10-09-mise-today-dashboard

### 4. End flows with consequences, not confetti
- Do: finish multi-step flows with a summary of what happens next (checklist), one primary + one quiet action; state consequences next to save buttons.
- Do: allow exactly one expressive element at that moment (artwork header, serif headline).
- Do: success modal anatomy — art header (top ~third) with a floating mini-card of the changed object, serif headline, one-line sentence, tinted checklist box, full-width pill buttons: dark primary + outlined secondary.
- Refs: 2026-10-08-mise-chef-review

### 5. Onboarding lives beside the work, not in front of it
- Do: show remaining setup as a small persistent card (sidebar/bottom): soft photo header, one icon chip, title, benefit sentence, progress ring + "n of m", quiet Skip + bordered Next.
- Don't: block the app with a multi-screen wizard for optional steps.
- Refs: 2026-10-08-mise-chef-review

### 6. Persistent sidebar card for "what's next"
- Do: reserve the bottom of the sidebar for one contextual card (unfinished setup, next deadline) with a big key fact, a muted sub-line and one quiet action.
- Refs: 2026-10-08-mise-chef-review, 2026-10-09-mise-today-dashboard, 2026-10-09-quarterly-dark-empty-state

### 7. Dark theme = layered charcoals, not black
- Do: 3-4 close charcoal steps (outer → sidebar → main → card), separated by tone plus a 1px low-contrast hairline; off-white text, grey muted text; one saturated accent and status greens.
- Do: tinted icon tiles (accent ~15% bg + full-color glyph) are the only color blocks.
- Don't: pure #000 cards, glowing borders, gradients, or more than one accent.
- Refs: 2026-10-09-quarterly-dark-empty-state

### 8. Primary button: neutral in light, accent in dark
- Light: near-black filled primary (strongest contrast on off-white); accent stays reserved for meaning (AI, info).
- Dark: the single accent as filled primary (a black button disappears, a white one glares); secondary is outlined with a hairline.
- Either theme: max one filled primary per view.
- Refs: 2026-10-08-mise-chef-review, 2026-10-09-quarterly-dark-empty-state (owner delegated; resolved 2026-10-09)

### 9. Empty states are decisions (provisional)
- Do: centered headline + reassuring line, then 2 choice cards (icon tile, title, one sentence, 3 benefit checks, one button); recommended path filled, alternative outlined.
- Do: answer the user's fear in the copy (permissions, deadlines) — calm, plain tone.
- Refs: 2026-10-09-quarterly-dark-empty-state

## Tokens

| Token | Value | Notes |
|---|---|---|
| Color · background | warm off-white ~#ECEBE8, panels ~#F4F3F1, cards #FFF | |
| Color · text / primary | near-black ~#1C1C1C; secondary ~#6B6B6B | |
| Color · accent | one blue ~#2F6FD6 (AI/info); semantic green, red, orange | |
| Radius | 10 rows/inputs · 16-20 panels · ~24 modals · pill buttons | |
| Spacing scale | generous: ~16-24 inside cards, ~8 between row tiles | |
| Type scale | Inter-like sans 13/15 UI; serif display only for celebratory headings | |
| Dark theme | layered charcoals ~#0E0E10 / #141417 / #1A1A1E, hairline ~#2A2A2F, text #F2F2F2, muted #8E8E93; no pure-black cards |
| Icon tile | ~48px, ~10 radius, accent ~15% bg + full-color glyph |
| Section label | 12px uppercase, +6-8% tracking, muted |
| Shadow / elevation | separate by tone, not shadow; soft shadow + scrim only for modals | |
| Motion | — | |

## Patterns

- **KPI card:** tinted icon tile + label / big regular-weight number + muted unit / footer: delta chip left, baseline right. (2026-10-09-mise-today-dashboard)
- **List row:** rounded tile, 56px thumbnail (~10px radius), title + muted `context · owner`, status pill with colored dot, value with thin progress bar. (both refs)
- **State-driven CTA:** Start = dark filled, Continue = outlined, Done = green tinted chip. (2026-10-09-mise-today-dashboard)
- **Attention feed item:** icon, bold problem, muted reason, one text action with chevron. (2026-10-09-mise-today-dashboard)
- **Header actions:** at most one dark primary + one white secondary + notification bell. (both refs)
- **App shell:** grouped sidebar (Service / Planning / Review), search with `/` shortcut, count badges right-aligned, profile at the bottom. (both refs)

## Do / Don't

## Open tensions

_None._
