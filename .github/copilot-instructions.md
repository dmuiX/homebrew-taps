# GitHub Copilot Instructions

Repository guidance for GitHub Copilot.

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
- Keep cask/formula definitions explicit and minimal.
- Keep dependencies and conflicts explicit (`depends_on`, `conflicts_with`).
- Keep sources trusted and metadata complete.
- Avoid introducing unrelated tooling or config churn.

## Cask/Formula Rules

- Keep stable paths and names under `Casks/` and `Formula/` unless a migration is included.
- Preserve existing package tokens unless a change is explicitly requested.
- Keep installs reproducible: pinned `version` and correct `sha256`.
- Verify that `url`, artifact blocks, and checksums are aligned.
- Review `zap`/`uninstall` blocks for correctness when package behavior changes.

## Validation Before Finishing

For Homebrew changes, run when possible:

```bash
brew style --fix Casks/*.rb
brew audit --strict --online Casks/*.rb
brew install --cask tuxguitar
```

If validation cannot be run, explicitly state that in the summary.

## Pull Request Quality Bar

- State what changed and why.
- Mention how it was validated.
- Mention any remaining risks (if any).

## What Not To Do

- No hidden magic.
- No broad refactors without clear need.
- No secret leakage in logs/docs.
- No destructive package changes without explicit warning.
- Adding names into READMEs or anywhere else: always anonymize.
