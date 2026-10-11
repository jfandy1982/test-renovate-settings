# CLAUDE.md

## Repository Purpose

Test Repository for experimenting with Renovate settings

## Known Structure

- `experiments/` — deliberate playground and backup directory, not production code; ignore when reviewing
- `node_modules/` — exists locally but is gitignored; not committed to the repo

## Tooling

- GitHub Actions SHAs are manually verified and pinned — do not flag pinned SHAs as outdated without checking first
- Renovate: `renovate.json` in `.github/` is the repository-specific Renovate entry point
- pre-commit hook runs `lint-staged` (Prettier + cspell) on `*.json`, `*.md`, `*.yml`; additionally runs `js-yaml` syntax validation on `*.yml`, `*.yaml`

### Commands

These NPM scripts can be used beside pre-commit-hooks to enforce proper spelling and formatting.

```bash
npm run format:all          # format all JSON/MD/YML files with Prettier
npm run format:all:check    # verify formatting without writing
npm run spell:all:check     # run cspell on the whole repo
npm run spell:dict:search   # search word in available dictionaries; reveals which dict to enable in .cspell.json
npm run yaml:all:check      # validate YAML syntax in .github/workflows
```
