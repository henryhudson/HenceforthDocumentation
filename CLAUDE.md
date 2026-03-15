# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the LaTeX documentation for **Henceforth** — a FORTH programming environment for iOS (companion app source at github.com/henryhudson/FORTHapp). The entire document lives in a single file: `hforth.tex`.

## Build

```bash
pdflatex hforth.tex
```

Run twice if table of contents or cross-references change. Uses TeX Live with pdfLaTeX. Required packages: tcolorbox, listings, tikz, fancyhdr, titlesec, hyperref, geometry, enumitem, amsmath, fancyvrb, booktabs, inconsolata, lmodern.

## Document Structure

`hforth.tex` is a `book`-class document with these chapters:

1. **About** — links, support
2. **Goals** — planned features (BSV integration, file access, maths, settings)
3. **Credits** — influences and references
4. **Documentation** — the bulk of the document; comprehensive reference for all Henceforth built-in words and Bitcoin Script opcodes

## Custom Environments

- `forthbox[title]` — `tcolorbox` listing for FORTH word definitions (blue frame, monospace)
- `notebox` — gold-bordered callout for notes/warnings

## Colour Palette

All colours are prefixed `forth`: `forthDark`, `forthBlue`, `forthCyan`, `forthGold`, `forthOrange`, `forthBg`, `forthGrey`, `forthGreen`. Use these consistently when adding new styled elements.

## Conventions

- FORTH stack effect notation: `( before -- after )` with types like `n` (number), `f` (flag), `addr` (address), `u` (unsigned), `c-addr` (character address), `xt` (execution token)
- Word documentation follows the pattern: word name, stack effect, then multi-line description indented beneath
- Subsections within Documentation group words by category (arithmetic, stack, loops, comparison, etc.)
- Bitcoin Script opcodes are prefixed `op_` and grouped separately (push data, control flow, stack, splice, bitwise, arithmetic, crypto, lock time, reserved)
