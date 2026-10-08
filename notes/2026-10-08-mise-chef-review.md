---
id: 2026-10-08-mise-chef-review
source: Mise (restaurant prep planner, concept)
platform: web
tags: [light, dashboard, ai-ux, modal, success-state, onboarding, sidebar, review-flow, illustration]
focus: the success pop-up (art header + floating item card + checklist) and the sidebar onboarding card
added: 2026-10-08
---

## What makes it work
- **Warm-neutral greys, almost no color.** Background, sidebar and panels are stepped
  off-white/stone tones; color is reserved for meaning (blue = AI/data, red = urgent,
  green = auto-approved, orange dot = edited).
- **AI as a collaborator, not a feature.** "AI recommended" chip, the agent speaks in
  first person in plain sentences, user overrides are tracked ("set by you", "3 kg above
  my recommendation"), and the success modal shows "You" and the agent as two cursors
  on the same card.
- **Success modal with a fine-art header.** Impressionist painting as the top third,
  a floating mini-card of the changed item on top, then a serif headline + one-line
  sentence + checklist summary of what will happen. Celebrates without confetti.
- **Onboarding as a sidebar card, not a wizard.** Pinned above Settings in the sidebar:
  soft sky/cloud photo header with one centered icon chip + dark tooltip-style label
  ("Pair tablet"), bold title, two-line muted explanation of the *benefit*, footer with a
  circular progress ring + "3 of 4", quiet "Skip" text button and a bordered "Next".
  Setup stays reachable but never blocks the real work.
- **Deltas as the primary data format.** Every list row is `old → new unit`
  (`37 → 40 kg`); the delta is the content, not a column.
- **Review queue ergonomics:** "1 of 5 done" pill, prev/next arrows, "Approve all
  remaining" as secondary, final CTA disabled until done, and a calm green footer
  "N items need no review" that explains why they were skipped.
- **Action bar states consequences:** "Saving sends 40 kg to Tuesday prep" sits next
  to the primary button; destructive/undo is a quiet text button on the left.

## Measurable values
- palette (approx): #ECEBE8 app bg, #F4F3F1 panel, #FFFFFF card/modal,
  #1C1C1C text/primary button, #6B6B6B secondary text, #2F6FD6 AI/accent blue,
  #E3EDF9 AI bubble tint, #D9E8DF + #2E7D4F success, #D9342B badge red
- radius: ~10px inputs/rows, ~16-20px panels, ~24px modal, full pill for primary buttons in modal
- type: neo-grotesk sans (Inter-like) for UI, ~15/13px row title/meta; **serif display
  headline only in the celebratory moment**
- density: 2-line list rows (title + muted delta), 48-56px thumbnails with ~10px radius
- borders: 1px hairline on selected row (dark) instead of fill; panels separated by tone, not borders
- shadow: almost none in-app; modal gets a soft large shadow + dimmed scrim
- icons: thin outline (1.5px), monochrome

## Steal this
- Put remaining onboarding steps in a small persistent card (image header, benefit copy, progress ring, Skip/Next) instead of a blocking wizard.
- Keep the UI greyscale and spend color only on status/meaning; one accent for the AI.
- After a multi-step flow, end with a "here is what happens next" checklist modal, with
  a single expressive element (art/serif headline) instead of generic success icons.
