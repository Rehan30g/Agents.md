# Agents.md

A drop-in `AGENTS.md` that gives AI coding agents (Claude Code, Codex, Cursor, Antigravity, etc.) a working style, not just project facts.

## The problem

Most agents write code that compiles and stops there. They mark tasks "done" the moment there are no errors, never revise their own mediocre output, and either do too little (never touching anything unrequested) or too much (silently restructuring things nobody asked them to touch). `AGENTS.md` fixes this by defining *behavior*, not documentation.

## What's in here

- **[`AGENTS.md`](./AGENTS.md)** — the actual manual. Copy this one file into the root of any repo.

That's it. This isn't a library or a tool — it's a text file you hand to an agent.

## How to use it

1. Copy `AGENTS.md` into the root of your project.
2. Point your agent at it (most tools — Claude Code, Cursor, Codex — read a root-level `AGENTS.md` automatically; check your tool's docs if it doesn't).
3. Leave the **Project configuration** section at the bottom empty on first use — the agent is instructed to detect your stack, commands, and conventions itself and fill it in. After that, it's a fast lookup for every future session.
4. Optionally, let the agent create `DESIGN.md` (frontend style decisions) and `NOTES.md` (a running log of mistakes and useful references) as it works — both are referenced in the manual and grow on their own.

No install, no config, no dependencies.

## What it actually changes

Three behaviors, enforced with a concrete example each inside `AGENTS.md`:

1. **Verifies before claiming "done"** — runs the real tests, and actually exercises the feature (clicks the button, hits the endpoint) instead of trusting a clean compile.
2. **Holds its own quality bar** — revises half-baked work before reporting, without waiting to be told.
3. **Takes initiative, with a handbrake** — freely does small reversible improvements (a missing error message, a filled-in description); asks first before anything structural or hard to undo (renames, new dependencies, schema changes, pushing to main).

It also sets a tone (direct, restrained, no filler), a design floor (flat UI, responsive, no gradient/neon slop), and a memory habit (write down what you learn so the next session doesn't relearn it).

## Why

Different agent tools don't share instincts by default — the same request can get you a careful partner or a box-checker depending which tool you're running. This file is an attempt to transfer the former, in a form small enough to actually get read.

## License

MIT — see [`LICENSE`](./LICENSE).
