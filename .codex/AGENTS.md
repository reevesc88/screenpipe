# ECC for Codex CLI

Repo-local notes for Codex in this checkout. There is no root `AGENTS.md`.

## Repo Skill

- Repo skill: `.agents/skills/screenpipe/SKILL.md`
- Claude-facing companion skill: `.claude/skills/screenpipe/SKILL.md`
- Implicit invocation for that skill stays off (`allow_implicit_invocation: false`).
- Keep credentials and MCP servers in `~/.codex/config.toml`, not in this repo.
- Pin any opt-in MCP package to an exact version in user config. Do not enable Playwright `--extension` or a third-party MCP URL from this repo.

## Multi-Agent Support

- Explorer: read-only evidence gathering
- Reviewer: correctness, security, and regression review
- Docs researcher: API and release-note verification

## Workflow Files

No dedicated workflow command files were generated for this repo.
