# SF Impact Brief

Generate personalised SAP SuccessFactors release impact briefs in seconds. Select your client's modules, pick a version, and get a tiered action plan — what you must act on, what to test, and what's nice to know.

**Live at: https://sahirvhora.github.io/sf-impact-brief**

## What it does

- **Module-based filtering** — select any of 40 SF modules across 8 areas (Employee Central, Compensation, Talent, Recruiting, Platform, Learning, AI, Payroll)
- **Three-tier prioritisation** — every update is classified into MUST ACT (critical/deprecated), SHOULD TEST (high impact), or NICE TO KNOW (medium/low)
- **Upsell opportunities** — new features you could implement for clients, surfaced automatically
- **Version-aware** — toggle between 1H 2026, 2H 2026, or all releases
- **Print-friendly** — print or save as PDF with clean formatting
- **Export to JSON** — download the filtered data for your own analysis
- **Dark/light theme** — navy+gold dark theme, warm parchment light theme
- **Zero setup** — single HTML file, no backend, no login, always free

## How it works

```
sf-release-update (weekly cron -> updates.json)
       |
       v
sf-impact-brief (fetches live JSON -> filters by module -> generates tiered brief)
```

This tool fetches live data from [SF Release Update](https://sahirvhora.github.io/sf-release-update/), so it's always current. No scraping, no maintenance — the data updates automatically every Monday.

## Use cases

- **Consultants** — generate a personalised release impact brief for each client in 30 seconds
- **Implementation partners** — send proactive release readiness reports to all your managed accounts
- **Customer COEs** — filter 492 updates down to what actually matters for YOUR modules
- **Sales/pre-sales** — use the Upsell Opportunities section to spot implementation prospects

## Architecture

```
sf-impact-brief/
├── index.html      # Single-file app (HTML/CSS/JS)
├── favicon.svg     # Favicon
├── preview.png     # OG image for social sharing
├── preview.svg     # Editable source for preview image
└── README.md
```

No build step. No dependencies. Deploy to GitHub Pages directly from the repo root.

## Setup

```bash
# Serve locally
python3 -m http.server 8766
# Open http://localhost:8766
```

The page fetches `updates.json` from the live SF Release Update site. No local data needed.

## Data source

Powered by [SF Release Update](https://github.com/SahirVhora/sf-release-update) — a weekly-scraped tracker of all SAP SuccessFactors What's New updates. The scraper runs every Monday via GitHub Actions and publishes fresh data to GitHub Pages.

Cross-links:
- **SF Release Update** — browse all 492 updates: [sahirvhora.github.io/sf-release-update](https://sahirvhora.github.io/sf-release-update)
- **SF Impact Brief** — generate personalised briefs: [sahirvhora.github.io/sf-impact-brief](https://sahirvhora.github.io/sf-impact-brief)

## Related SAP SuccessFactors tools

This project is part of a wider SAP SuccessFactors supplementary tools suite.

Start with SF Compass for the full hub: https://sahirvhora.github.io/sf-compass/

| Tool | Purpose |
|---|---|
| SF Compass | Feasibility answers, implementation guidance, and links to the full tool suite |
| SF Release Update | Release impact tracking — browse all 492 updates |
| **SF Impact Brief** | **Personalised briefs from release data — this tool** |
| SF Pay Transparency | EU Pay Transparency readiness and evidence workflow framing |
| SF Value Navigator | Value realisation and sponsor-facing consulting framework |
| SF Position Integrity Checker | Position hierarchy, incumbency, and EC data-quality validation |
| SAPSF ObjectSync | Controlled foundation-object synchronisation between SF environments |
