---
name: design-dna
description: Ingest UI screenshots from the design-dna inbox into a distilled, LLM-readable design language (DESIGN.md). Use when the user says "/design-dna", "inbox'u işle", "yeni ss attım", "tasarım arşivini güncelle", or asks to add a UI reference to their design language. Also use to answer "benim tasarım dilim ne" or to apply the design language to a UI task.
---

# design-dna

Turns a private pile of UI screenshots into a public, text-only design language.

Repo root: `~/Developer/design-dna` (resolve `$DNA` to this; if missing, ask the user).

```
$DNA/
  DESIGN.md        public  - the distilled design language (main output)
  INDEX.md         public  - one line per reference
  notes/<id>.md    public  - per-reference notes, readable WITHOUT the image
  private/inbox/   private - new screenshots dropped by the user (+ optional .txt notes)
  private/refs/<id>.<ext>  private - archived screenshots
```

## Hard rules

1. **Never copy, move or reference images into public paths.** Images only live under `private/`. Public notes may mention `private/refs/<id>.png` as a path but must make sense without it.
2. **No personal data in public files.** If a screenshot shows names, handles, DMs, emails, customer data, amounts tied to a person — do not transcribe them. Describe the layout, not the content.
3. **No logos, brand illustrations or copied copywriting.** Observations only: colors (hex), sizes, spacing, radii, type, hierarchy, motion, patterns.
4. **The user's "why I liked it" beats your guess.** If an inbox image has a sibling `.txt` (same basename) or the user said it in chat, that is the primary focus of the note. If there is none, write your best guess and mark it `focus: (tahmin)`.
5. Write notes and DESIGN.md in **English** (public audience). Talk to the user in Turkish.

## Ingest flow (`/design-dna` with no args)

1. List `private/inbox/` (images + `.txt`). Empty → say so and stop.
2. For each image, Read it (vision) and pick an id: `YYYY-MM-DD-<source>-<subject>` in kebab-case, e.g. `2026-10-08-linear-sidebar`. Source = app/product name if recognizable, else `unknown`.
3. Move the image to `private/refs/<id>.<ext>` (use `mv`, never delete). Delete the consumed `.txt` only after its content is in the note.
4. Write `notes/<id>.md`:

```markdown
---
id: <id>
source: <app or unknown>
platform: ios | android | web | macos | other
tags: [dark, dashboard, typography, ...]
focus: <what the user liked, one line>
added: YYYY-MM-DD
---

## What makes it work
- 3-6 bullets, concrete and visual. "Section labels 11px uppercase, +6% tracking, 45% opacity" not "nice typography".

## Measurable values
- palette: #0B0B0C bg, #1A1A1D surface, #5E6AD2 accent (approximate)
- radius / spacing rhythm / type scale / shadows / borders / blur — only what is visible

## Steal this
- One or two rules worth adopting, phrased as instructions.
```

Prefer tags from the existing vocabulary in INDEX.md before inventing new ones.

5. Append to `INDEX.md` under the table: `| <id> | <platform> | <tags> | <focus> |`
6. **Distill into DESIGN.md** — this is the important part:
   - A new pattern seen in ≥2 references, or explicitly called out by the user → add/strengthen a principle, cite the note ids.
   - Contradicts an existing principle → do NOT silently overwrite; list it under "Open tensions" and ask the user.
   - Update tokens only when references agree; keep ranges ("radius 10-14") rather than false precision.
   - Keep DESIGN.md tight (target < 300 lines). Merge, don't append forever.
7. Report in Turkish: what was ingested, which principles changed (diff-style, short), open questions.
8. Do NOT commit or push unless asked. If asked: commit public repo and `private/` repo separately (`private/` is its own git repo). Commit message: `docs: <tr açıklama> (<en>)`.

## Apply flow (UI task in any project)

When building or reviewing UI: read `$DNA/DESIGN.md` first. Only open specific `notes/` (and their private images) when a principle needs a concrete example. Map tokens to the project's stack (SwiftUI, Tailwind, CSS vars) instead of hardcoding.

## Ask flow ("tasarım dilim ne?")

Summarize DESIGN.md in Turkish, 5-8 bullets, plus the open tensions.
