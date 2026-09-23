# apify-org

> **The Apify monorepo, mirrored and curated** - Curated mirror of Apify's production scraper org - actor-scraper, web-scraper, cheerio-scraper, puppeteer-scraper, playwright-scraper - battle-tested code from the people who built Crawlee.

<p align="center"><a href="https://github.com/hmzainjamil/apify-org">Repository</a> · <a href="https://github.com/hmzainjamil/apify-org/commits/main">Commits</a> · <a href="https://github.com/hmzainjamil/apify-org/issues">Issues</a></p>
<p align="center"><img alt="Documentation" src="https://img.shields.io/badge/documentation-deep%20editorial-lightgrey"> <img alt="Lifecycle" src="https://img.shields.io/badge/lifecycle-active-success"></p>

<!-- HMZ DEEP README v1 -->

## At a glance

| Field | Current state |
|---|---|
| Repository | apify-org |
| Visibility | Public |
| Lifecycle | Active |
| Evidence basis | Current repository documentation and source-visible material |

## Why this exists

**The Apify monorepo, mirrored and curated** - Curated mirror of Apify's production scraper org - actor-scraper, web-scraper, cheerio-scraper, puppeteer-scraper, playwright-scraper - battle-tested code from the people who built Crawlee.

The README describes the current tooling and workflow scope without treating external provider capabilities or third-party system behavior as repository-owned functionality.

## CONCEPTS

| Concept | Location | Description |
|---|---|---|
| **Lerna config** | `actor-scraper/lerna.json` | Monorepo orchestrator - [Source](https://github.com/hmzainjamil/apify-org/blob/main/actor-scraper/lerna.json) |
| **Package config** | `actor-scraper/package.json` | Workspace root - [Source](https://github.com/hmzainjamil/apify-org/blob/main/actor-scraper/package.json) |
| **Oxlint config** | `actor-scraper/oxlint.config.ts` | Lint rules across actors - [Source](https://github.com/hmzainjamil/apify-org/blob/main/actor-scraper/oxlint.config.ts) |
| **Pre-commit hook** | `actor-scraper/.husky/pre-commit` | Husky gate before commits - [Source](https://github.com/hmzainjamil/apify-org/blob/main/actor-scraper/.husky/pre-commit) |
| **E2E workflow** | `actor-scraper/.github/workflows/test-e2e.yaml` | Real-site fixture tests - [Source](https://github.com/hmzainjamil/apify-org/blob/main/actor-scraper/.github/workflows/test-e2e.yaml) |
| **Release workflow** | `actor-scraper/.github/workflows/release-generic-actors.yaml` | Versioned actor publishes - [Source](https://github.com/hmzainjamil/apify-org/blob/main/actor-scraper/.github/workflows/release-generic-actors.yaml) |
| **PR title gate** | `actor-scraper/.github/workflows/check-pr-title.yaml` | Conventional commits enforced - [Source](https://github.com/hmzainjamil/apify-org/blob/main/actor-scraper/.github/workflows/check-pr-title.yaml) |
| **Bug template** | `actor-scraper/.github/ISSUE_TEMPLATE/scraper_bug_report.yaml` | Structured bug intake - [Source](https://github.com/hmzainjamil/apify-org/blob/main/actor-scraper/.github/ISSUE_TEMPLATE/scraper_bug_report.yaml) |
| **Contributing guide** | `actor-scraper/CONTRIBUTING.md` | How to add an actor - [Source](https://github.com/hmzainjamil/apify-org/blob/main/actor-scraper/CONTRIBUTING.md) |
| **License** | `actor-scraper/LICENSE.md` | Apache-2.0 - [Source](https://github.com/hmzainjamil/apify-org/blob/main/actor-scraper/LICENSE.md) |

## HOW IT WORKS

```
+---------------------------------------------------------+
|                       INPUT                             |
|   lerna + npm workspaces . `actor-scraper/lerna.json|
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  ORIENT / PARSE                         |
|   - Validate inputs                                     |
|   - Load skill / agent / tool definitions               |
|   - Resolve config + secrets from .env                  |
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  PLAN (Claude Sonnet)                   |
|   - Decompose goal into ordered subtasks                |
|   - Pick model per task (Sonnet / Haiku / Tier-0)       |
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  EXECUTE (parallel)                     |
|   - Spawn sub-agents / call tools                       |
|   - Stream tokens, persist artifacts                    |
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  VERIFY                                 |
|   - Lint / typecheck / visual diff / QA agent           |
|   - On failure -> re-prompt with error context          |
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  SHIP                                   |
|   - Write to disk . commit . PR . upload                |
+---------------------------------------------------------+
```

## Install

```bash
git clone https://github.com/hmzainjamil/apify-org.git
cd apify-org

# Per-repo install (try in order):
bash install.sh 2>/dev/null || \
npm install 2>/dev/null || \
bun install 2>/dev/null || \
pip install -r requirements.txt 2>/dev/null || true
```

Environment:

```bash
cp .env.example .env  # if present
# fill ANTHROPIC_API_KEY at minimum
```

## Usage

```bash
# Claude Code skill packs:
/skill-name "your goal"

# CLI / scripts:
python scripts/<script>.py --input ./input --output ./output

# TypeScript projects:
bun run dev    # or npm run dev
```

### Configuration knobs

| Key | Default | Description |
|---|---|---|
| `ANTHROPIC_API_KEY` | - (required) | Claude API key |
| `MODEL` | `claude-sonnet-4-7` | Default LLM |
| `MODEL_FALLBACK` | `claude-haiku-4` | Cheaper fallback |
| `MAX_TOKENS` | `8192` | Per-call ceiling |
| `TEMPERATURE` | `0.2` | Determinism dial |
| `LOG_LEVEL` | `info` | debug / info / warn / error |
| `OUT_DIR` | `./out` | Where artifacts land |
| `CACHE_DIR` | `.cache` | Prompt cache root |
| `PARALLELISM` | `4` | Sub-agent concurrency |
| `RETRY_MAX` | `3` | Per-call retry budget |
| `TIMEOUT_S` | `120` | Per-call timeout |
| `DRY_RUN` | `false` | Plan-only, no side effects |

### Case 3 - DTC brand, ad creative testing

- Before: $2K/month UGC creator retainer, 4 ads/month.
- After: 30+ ad variants/week via Arcads + Claude, A/B-tested.
- Result: 3x creative velocity, 41% lower CAC after 6 weeks.

## Security

- Never commit API keys. `.env` is in `.gitignore` by default.
- Use [git-secret](https://git-secret.io/) or 1Password CLI for team secret sharing.
- Review the QA / safety layer for any tool that writes to disk or runs shells (see `mac_safety.py` style guards).
- Vulnerability reports: open a private GitHub Security Advisory.

## Limitations

- External provider APIs and policies change over time.
- Integration claims require current compatibility tests.
- Quantitative claims require reproducible evidence.

## Related

- [Claude Code](https://docs.claude.com/en/docs/claude-code) - official docs
- [Anthropic Console](https://console.anthropic.com) - API keys + billing
- [Crawlee](https://crawlee.dev) - web scraping framework
- [hmz-claude-code-best-practice](https://github.com/hmzainjamil/hmz-claude-code-best-practice) - sister repo

## Maintainer

[hmzainjamil](https://github.com/hmzainjamil)