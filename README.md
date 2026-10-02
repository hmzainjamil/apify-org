# Apify SDK and scraper Actor snapshot

This repository contains an `actor-scraper/` project with Apify SDK JavaScript workspace metadata and several scraper Actor packages. The tree also includes Actor READMEs, source, input schemas, Dockerfiles, release workflows, and project contribution/license files.

The repository name and contents alone do not establish that this is a complete or current mirror of Apify's upstream repositories. The nested package metadata identifies Apify's `apify-sdk-js` project, while tracked files and paths differ from the current upstream tree. Treat this checkout as a snapshot until maintainers verify its source commit and synchronization process.

## Contents

| Path | Role |
|---|---|
| `actor-scraper/package.json` | pnpm-managed Apify SDK JavaScript workspace metadata and scripts |
| `actor-scraper/packages/actor-scraper/` | Scraper Actor packages, including Cheerio, JSDOM, Playwright, Puppeteer, Camoufox and sitemap variants |
| `actor-scraper/.github/workflows/` | Pull request, end-to-end, and release automation |
| `actor-scraper/CONTRIBUTING.md` | Contribution guidance |
| `actor-scraper/LICENSE.md` | Apache License 2.0 text in the nested project |

See each Actor's README and input schema for its supported configuration and output behavior.

## Other nested project snapshots

The directories below contain separate project trees with their own README files. This index identifies the README path only; it does not assert that each snapshot is complete, current, maintained by Apify, or synchronized with an upstream repository. Check each project's README, package metadata, and license for provenance and instructions.

| Group | Project README |
|---|---|
| SDKs and development tools | [apify-cli](../apify-cli/README.md) |
| SDKs and development tools | [apify-client-js](../apify-client-js/README.md) |
| SDKs and development tools | [apify-client-python](../apify-client-python/README.md) |
| SDKs and development tools | [apify-sdk-js](../apify-sdk-js/README.md) |
| SDKs and development tools | [apify-sdk-python](../apify-sdk-python/README.md) |
| SDKs and development tools | [crawlee](../crawlee/README.md) |
| SDKs and development tools | [crawlee-python](../crawlee-python/README.md) |
| Actors and templates | [actor-templates](../actor-templates/README.md) |
| Actors and templates | [actor-whitepaper](../actor-whitepaper/README.md) |
| Scraping and browser tooling | [camoufox-js](../camoufox-js/README.md) |
| Scraping and browser tooling | [fingerprint-suite](../fingerprint-suite/README.md) |
| Scraping and browser tooling | [got-scraping](../got-scraping/README.md) |
| Scraping and browser tooling | [impit](../impit/README.md) |
| Scraping and browser tooling | [proxy-chain](../proxy-chain/README.md) |
| Integrations and MCP | [apify-mcp-server](../apify-mcp-server/README.md) |
| Integrations and MCP | [apify-openclaw-plugin](../apify-openclaw-plugin/README.md) |
| Integrations and MCP | [cursor-plugins](../cursor-plugins/README.md) |
| Integrations and MCP | [mcp-client-capabilities](../mcp-client-capabilities/README.md) |
| Integrations and MCP | [n8n-nodes-apify](../n8n-nodes-apify/README.md) |
| Integrations and MCP | [rag-web-browser](../rag-web-browser/README.md) |
| Integrations and MCP | [tester-mcp-client](../tester-mcp-client/README.md) |
| Skills and guides | [agent-skills](../agent-skills/README.md) |
| Skills and guides | [awesome-skills](../awesome-skills/README.md) |


## Requirements

The nested workspace declares pnpm 10.24.0 and includes Apify SDK, Crawlee, TypeScript, Vitest, Turbo, Lerna, and lint/format tools. Individual Actors have their own package dependencies and scripts. Use the nested `actor-scraper/` directory as the project root when following its package instructions.

## Install and develop

Inspect package scripts and contribution guidance before installing dependencies or running commands. The upstream project declares pnpm as its package manager:

```bash
cd actor-scraper
pnpm install
```

The root workspace declares commands including `pnpm test`, `pnpm test:e2e`, `pnpm build`, and `pnpm lint`. End-to-end workflows can contact real websites. Run them only with appropriate authorization and test targets.

## Running an Actor

Each Actor has its own `README.md`, `INPUT_SCHEMA.json`, `.actor/actor.json`, and package configuration. Read those files before running it. Actor execution may send requests to target websites, use Apify platform services, and incur platform or proxy costs. Requirements and available input fields vary by Actor.

## Provenance and synchronization

The nested package metadata points to Apify's `apify-sdk-js` repository. A path comparison against the currently fetched upstream tree found significant differences, so this checkout is not documented here as a complete mirror. Maintainers should record the source commit, import date, sync process, and any intentional local changes before claiming upstream parity.

Do not remove, rewrite, or regenerate upstream-owned files without preserving their licenses, notices, and source provenance.

## Security and data handling

See [SECURITY.md](SECURITY.md). Review target-site permissions, data collection, Actor configuration, and destination storage before running a scraper. Never commit Apify tokens, account data, or private run outputs.

## Contributing

Follow [the nested contribution guide](actor-scraper/CONTRIBUTING.md) and preserve upstream attribution and license notices. Identify whether a proposed change belongs to the nested upstream project or this repository's outer snapshot.

## License

The nested project contains [Apache License 2.0 text](actor-scraper/LICENSE.md). Confirm that it covers the files you intend to use and retain required notices when redistributing. Third-party dependencies and external Actors may have separate terms.
