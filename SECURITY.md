# Security and data handling

## Credentials

Use an Apify token with the minimum permissions needed. Prefer approved interactive authentication or a protected environment variable. Never commit tokens, paste them into prompts, or include them in logs, issue reports, or generated artifacts.

## Scraping and external services

Actors can send network requests to target websites and interact with Apify platform services. Review each Actor's source, input schema, publisher, permissions, proxy settings, cost model, and output destination before running it. Use only sites and data you are authorized to access, and follow applicable terms and privacy requirements.

Use test URLs and synthetic records when possible. Minimize personal data. Check datasets and key-value stores before sharing or retaining run output.

## Upstream provenance

This repository contains a nested upstream project snapshot. Preserve upstream license files, attribution, security fixes, and source history when changing or redistributing its contents.

## Reporting

Report concerns through a private GitHub Security Advisory for this repository. Do not disclose credentials, private customer data, or sensitive target details in public issues.
