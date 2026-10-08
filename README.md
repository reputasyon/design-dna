# design-dna

A personal UI design language, distilled from hundreds of screenshots into a single
file an LLM can actually read.

- **[DESIGN.md](DESIGN.md)** — the design language: principles, tokens, patterns, do/don't.
- **[notes/](notes/)** — one note per reference, written to be useful without the image.
- **[INDEX.md](INDEX.md)** — searchable list of every reference.

Screenshots are **not** published (they belong to their creators). Only observations are.

## Use it

Point your AI tool at `DESIGN.md`:

```md
<!-- CLAUDE.md / .cursorrules / AGENTS.md -->
Before writing any UI, follow the design language in
https://raw.githubusercontent.com/reputasyon/design-dna/main/DESIGN.md
```

## Build your own

1. Fork, empty `notes/`, `INDEX.md` and reset `DESIGN.md`.
2. Copy `skill/design-dna/` to `~/.claude/skills/` (Claude Code).
3. Drop screenshots into `private/inbox/` (optionally `same-name.txt` with *why* you liked it).
4. Run `/design-dna`. It archives the images privately, writes notes, and updates `DESIGN.md`.

`private/` is git-ignored and a pre-commit hook blocks images
(`git config core.hooksPath .githooks`).

## License

Text: [CC BY 4.0](LICENSE). Referenced products and their visuals belong to their owners.
