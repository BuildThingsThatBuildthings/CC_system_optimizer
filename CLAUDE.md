# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A prompt library, not a software project. The entire repository is two Markdown files that users copy-paste into Claude Code to have *another* Claude instance audit and optimize their macOS / Linux / Windows system. There is no build system, no tests, no source code, and no runtime.

- `README.md` — landing page, quick-start prompt, supported platforms, typical results
- `prompt.md` — the canonical prompt catalog: universal prompt, per-OS variants (macOS/Linux/Windows), use-case variants (developer, non-technical, aggressive, disk-only, memory-only), and rollback snippets

The "product" shipped by this repo is the prompt text itself. Edits to those prompts are the primary work.

## Editing guidance

When changing prompts, keep these invariants — they are the repo's safety contract with end users, stated in README.md and prompt.md:

1. **Always ask before destructive actions.** Every prompt instructs the target Claude to confirm with the user before deleting, stopping services, or changing settings.
2. **Always provide rollback commands** for every change made.
3. **Cross-platform parity.** The universal prompt must stay OS-agnostic; OS-specific details belong in the per-platform sections. If you add an optimization category (e.g. a new cache type), update the "What Gets Optimized" table in `prompt.md` so macOS/Linux/Windows columns stay in sync.
4. **Keep README.md and prompt.md consistent.** README.md embeds a condensed version of the Quick Start prompt from prompt.md — if you change one, check the other.

## No tooling

There is nothing to build, lint, test, or run. Don't scaffold package.json, CI, linters, or test harnesses unless the user explicitly asks. Don't add code files — this repo's value is that it's copy-pasteable Markdown.
