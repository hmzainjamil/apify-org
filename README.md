# apify-org

> **Apify organization skills for Claude Code — web scraping, data extraction, and actor orchestration**

![Status](https://img.shields.io/badge/status-active-brightgreen?style=flat)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat)
![Claude Code](https://img.shields.io/badge/Claude_Code-Skill-FF6B35?style=flat)
![GitHub Stars](https://img.shields.io/github/stars/hmzainjamil/apify-org?style=flat)
![Last Commit](https://img.shields.io/github/last-commit/hmzainjamil/apify-org?style=flat)

---

## CONCEPTS

| Concept | Description |
|---|---|
| **Actor** | Serverless scraping/automation unit on Apify platform |
| **Dataset** | Structured output storage for scraped data |
| **Key-Value Store** | Unstructured file/blob storage per run |
| **Proxy** | Rotating residential/datacenter proxies |
| **Scheduler** | Cron-based actor execution |
| **Webhook** | Event triggers on actor run completion |
| **Puppeteer** | Headless Chrome automation library |
| **Cheerio** | Fast HTML parsing for static sites |

---

## 🔥 Hot Commands

```bash
# Run an Apify actor
apify call apify/web-scraper --input '{"startUrls":[{"url":"https://example.com"}]}'

# Get actor output
apify datasets get-items DATASET_ID

# List your actors
apify actors ls
```

## ■ tip
> Use Apify's residential proxies for scraping — avoids blocks on 99% of sites.

---

## ☠️ STARTUPS / BUSINESSES

- **Lead gen agencies**: scrape LinkedIn, directories, review sites at scale
- **E-commerce**: monitor competitor pricing automatically
- **Research firms**: bulk data extraction without engineering team

---

## Features

- 1500+ ready-made actors on Apify Store
- Residential proxy network included
- Dataset storage + export (JSON/CSV/Excel)
- Scheduled runs via cron
- Claude Code native integration

---

## Installation

```bash
git clone https://github.com/hmzainjamil/apify-org.git
cd apify-org
```

---

## Usage

```bash
# Install Apify CLI
npm install -g apify-cli

# Authenticate
apify login

# Run web scraper
apify call apify/web-scraper
```

---

## Configuration

| Variable | Description | Default |
|---|---|---|
| `API_KEY` | Primary API key | Required |
| `MODEL` | AI model to use | claude-sonnet |
| `DEBUG` | Enable debug mode | false |
| `MAX_TOKENS` | Max token budget | 8192 |

---

## Architecture

```
apify-org/
├── README.md          # Documentation
├── SKILL.md           # Claude Code skill definition
├── scripts/           # Automation scripts
├── templates/         # Output templates
└── examples/          # Usage examples
```

---

## Troubleshooting

| Issue | Cause | Fix |
|---|---|---|
| Auth fails | Invalid API key | Re-export key |
| Timeout | Network latency | Increase timeout |
| Empty output | Bad prompt | Check template |
| Rate limit | Too many requests | Add delay |

---

## Contributing

PRs welcome. Open an issue first for major changes.

---

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=hmzainjamil/apify-org&type=Date)](https://star-history.com/#hmzainjamil/apify-org&Date)

---

## 📜 License

MIT — free to use, modify, distribute.
