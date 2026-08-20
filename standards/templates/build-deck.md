# Build a deck from Markdown — pattern

The harness stores the Markdown source; the deck is regenerable and stored outside Git (per `FORMATS.md`).

## Input
A Markdown file in `<domain>/outputs/<deck-name>.md` with:
- Top-level `# Title` (slide 1)
- `## Section` for section dividers
- `### Slide title` for individual content slides
- Body content per slide

## Tooling options

### Marp (lightweight)
- Install: `npm i -g @marp-team/marp-cli`
- Build: `marp <input.md> -o <output.pptx>`
- Best for: clean defaults, web preview during drafting.

### python-pptx (full brand control)
- See your domain's build script (e.g. `<domain>/scripts/build-deck.py`) for a Python pipeline with brand constants, content-aware image generation, and layout selection.
- Best for: brand-compliant decks with specific colour, font, and layout requirements.

### Reveal.js / Slidev (HTML output)
- For web-rendered presentations served from GitHub Pages or any static host.
- Best for: presentations consumed via URL rather than a downloaded file.

## Storage rule

The Markdown source is committed in the harness. The built output (PPTX, PDF, HTML) is **not** committed — it is regenerable, and storing it would create a source-of-truth split.

Built outputs live where they are consumed:

- **For external delivery (Pattern A):** the built deck lives in the external-work repo or the client environment. Reference from the relevant domain's `references.md`.
- **For internal use:** the built deck lives in the org's shared drive. Reference from `<domain>/references.md`.

## Smoke test for adopters

When you commit a deck-source Markdown, also commit a one-line `build.sh` in the same folder that documents the build command. This makes the deck reproducible six months later without archaeology.
