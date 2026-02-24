# AGENTS.md

Repository guidance for AI/code assistants.

## Scope

This repo is a Homebrew tap for custom macOS packages.
Main technologies:
- Ruby (Homebrew DSL)
- Homebrew casks/formulas
- macOS packaging/install workflow

Do not apply frontend-only conventions unless a task explicitly adds frontend code.

## Priorities

1. Keep install flow simple and predictable.
2. Keep package metadata accurate and deterministic.
3. Preserve local-first behavior (no hidden network calls beyond package source URLs).
4. Prefer small, focused edits over broad rewrites.

## General Principles

- Clarity over cleverness.
- Deterministic behavior over implicit automation.
- Preserve backward compatibility of tap usage where possible.
- Do not rename package paths or tap naming conventions unless callers are updated.

## Ruby/Homebrew Rules

- Use Homebrew-compatible Ruby syntax and conventions.
- Keep side effects explicit and minimal in cask/formula definitions.
- Prefer small helper blocks only where they improve readability.
- Keep dependencies and conflicts explicit (`depends_on`, `conflicts_with`).
- Keep imports/download sources minimal and trusted.
- Fail fast with actionable errors when package behavior is invalid.

## Cask/Formula Rules

- Keep stable paths and names under `Casks/` and `Formula/` unless a migration is included.
- Preserve existing package tokens unless change is explicitly requested.
- Avoid destructive uninstall/zap changes without explicit warning.
- Keep installs reproducible: pinned `version` and correct `sha256`.
- Keep URLs, checksums, and app artifacts aligned.

## Prompts and UX

- Keep user-facing caveats explicit and short.
- Validate required package metadata.
- Provide safe defaults where useful.
- Do not echo secrets or sensitive data in logs/docs.

## README and Docs Style

- Prefer visually scannable READMEs, not long text blocks.
- Use badges where useful (platform/type/status).
- Include a clear `Quick Start` section with copy/paste commands.
- Prefer tables for package overviews when multiple items are listed.
- Add a short troubleshooting section for common failure paths (for taps: Gatekeeper/quarantine).
- These readability conventions are generally good for most GitHub repos, then adapt details to repo type.

## Security and Secrets

Never commit:
- real credentials/tokens
- private keys
- personal secrets in docs/examples

When editing docs/examples, use placeholders only.

## Validation Before Finishing

For Homebrew changes, run when possible:
- `brew style --fix Casks/*.rb`
- `brew audit --strict --online Casks/*.rb`
- `brew install --cask tuxguitar`

If you cannot run checks, state that explicitly in your summary.

## Commit Style

Use Conventional Commits:
- `feat:`
- `fix:`
- `docs:`
- `chore:`
- `refactor:`
- `test:`
- `ci:`
- `build:`

If the user says "commit", always create separate, detailed, meaningful, and logically scoped commits (not one combined commit).

### Commit Body

- Include a short body when behavior changes.
- Explain what changed and why in 1-3 lines.
- Keep it factual and specific to this repo.

## What Not To Do

- No hidden magic.
- No broad refactors without clear need.
- No secret leakage in logs/docs.
- No destructive package changes without explicit warning.
- Adding names into READMEs or anywhere else: always anonymize.
