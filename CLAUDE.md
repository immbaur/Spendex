# CLAUDE.md

## Project Overview
Spendex is a self-hosted, single-user personal finance dashboard that runs locally on macOS. It connects to bank accounts, categorizes transactions, visualizes spending, generates reports, and includes an AI-powered chat interface for custom queries and visualizations. It is accessible via HTTPS from any device.

## Source of Truth

- **Requirements**: `docs/requirements.md` — all implementation must be based on and stay in sync with this document
- **Software Design**: `docs/software-design.md` — architecture, components, interfaces, tech stack, and design decisions. All implementation must stay in sync with this document

All code must align with both documents. If either is outdated or conflicts with the implementation, update the document first.

### Design-First Workflow

Before implementing any feature or significant change:
1. Propose updates to `docs/software-design.md` covering the relevant architecture, components, and interfaces
2. Wait for approval
3. Only then proceed with implementation

## Key Commands

```bash
# TODO: Fill in as project develops
```

## Coding Conventions

- Keep code clean and readable, but don't over-engineer
- Prefer simple, direct solutions over abstractions
- No unnecessary comments or docstrings — code should be self-explanatory

## Testing

- Tests encouraged for critical paths, not mandatory for every function
- Use judgment on what needs coverage

## Architecture Guidelines

- **Single-user assumption**: No multi-tenancy, no user auth beyond basic access control
- **Local-first**: Database lives on the host machine; no cloud database
- **Security**: Sensitive data (API keys, tokens) stored in environment variables, never committed

## Git & PRs

- Claude Code can commit, push, and create PRs autonomously
- Keep PRs focused on a single concern

### Development Workflow

- Every feature or bug fix starts with a GitHub issue
- Create a feature branch from `develop` (see naming below)
- PRs are merged into `develop`
- `main` is the release branch — only merge `develop` into `main` for releases

### Branch Naming

- Use `feat/123-description` for features and `fix/123-description` for bug fixes, where `123` is the GitHub issue ID
- Always branch off `develop`

### Commit Messages

- Subject line describes *what* changed — do not put issue references (`#123`) in the subject
- Reference issues in the commit body or footer: `Refs #123`
- Keep subjects concise and imperative (e.g., "Add transaction categorization endpoint")

### Squashing

- Squash all commits into one before creating a PR — each PR should be a single commit

### PR Descriptions

- Use closing keywords to auto-close issues on merge: `Closes #123`, `Fixes #123`, or `Resolves #123`

## Communication

- Communicate in English
- Be concise and direct