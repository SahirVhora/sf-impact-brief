# SF Impact Brief

[![Live Site](https://img.shields.io/badge/Live%20Site-sahirvhora.github.io%2Fsf--impact--brief-gold)](https://sahirvhora.github.io/sf-impact-brief/)
[![Data Source](https://img.shields.io/badge/Data-SF%20Release%20Update-teal)](https://sahirvhora.github.io/sf-release-update/)
[![Updates Tracked](https://img.shields.io/badge/Updates-492-blue)](https://sahirvhora.github.io/sf-impact-brief/)
[![Modules](https://img.shields.io/badge/Modules-40-green)](https://sahirvhora.github.io/sf-impact-brief/)
[![Updated](https://img.shields.io/badge/Updated-Weekly-purple)](https://sahirvhora.github.io/sf-impact-brief/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

**Generate personalised SAP SuccessFactors release impact briefs in seconds. Select your client's modules, pick a version, and get a tiered action plan -- what you must act on, what to test, and what's nice to know.**

**[Open the brief generator -](https://sahirvhora.github.io/sf-impact-brief/)**

---

## What it does

| Feature | What it means |
|---------|---------------|
| Module-based filtering | Select any of 40 SF modules across 8 areas (Employee Central, Compensation, Talent, Recruiting, Platform, Learning, AI, Payroll) |
| Three-tier prioritisation | Every update sorted into MUST ACT (critical/deprecated), SHOULD TEST (high impact), or NICE TO KNOW (medium/low) |
| Upsell opportunities | New features you could implement for clients, surfaced automatically |
| Version-aware | Toggle between 1H 2026, 2H 2026, or all releases |
| Print-friendly | Print or save as PDF with clean formatting |
| Export to JSON | Download the filtered data for your own analysis |
| Dark/light theme | Navy+gold dark theme, warm parchment light theme |
| Zero setup | Single HTML file, no backend, no login, always free |

## How it works

```
sf-release-update (weekly cron -> updates.json)
       |
       v
sf-impact-brief (fetches live JSON -> filters by module -> generates tiered brief)
```

This tool fetches live data from [SF Release Update](https://sahirvhora.github.io/sf-release-update/), so it's always current. No scraping, no maintenance -- the data updates automatically every Monday.

## Use cases

- **Consultants** -- generate a personalised release impact brief for each client in 30 seconds
- **Implementation partners** -- send proactive release readiness reports to all your managed accounts
- **Customer COEs** -- filter 492 updates down to what actually matters for YOUR modules
- **Sales/pre-sales** -- use the Upsell Opportunities section to spot implementation prospects

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

Powered by [SF Release Update](https://github.com/SahirVhora/sf-release-update) -- a weekly-scraped tracker of all SAP SuccessFactors What's New updates. The scraper runs every Monday via GitHub Actions and publishes fresh data to GitHub Pages.

### Cross-links

- **SF Release Update** -- browse all 492 updates: [sahirvhora.github.io/sf-release-update](https://sahirvhora.github.io/sf-release-update)
- **SF Impact Brief** -- generate personalised briefs: [sahirvhora.github.io/sf-impact-brief](https://sahirvhora.github.io/sf-impact-brief)

## Related SAP SuccessFactors tools

This project is part of a wider SAP SuccessFactors supplementary tools suite. Start with [SF Compass](https://sahirvhora.github.io/sf-compass/) for the full hub.

| Tool | Purpose |
|---|---|
| SF Compass | Feasibility answers, implementation guidance, and links to the full tool suite |
| SF Release Update | Release impact tracking -- browse all 492 updates |
| **SF Impact Brief** | **Personalised briefs from release data -- this tool** |
| SF Pay Transparency | EU Pay Transparency readiness and evidence workflow framing |
| SF Value Navigator | Value realisation and sponsor-facing consulting framework |
| SF Position Integrity Checker | Position hierarchy, incumbency, and EC data-quality validation |
| SAPSF ObjectSync | Controlled foundation-object synchronisation between SF environments |

---

## Part of the SF Compass Suite

One of 10 free, open tools for SAP SuccessFactors consultants. Explore the full suite at [SF Compass](https://sahirvhora.github.io/sf-compass/).

Related tools:

- [Release Tracker](https://github.com/SahirVhora/sf-release-update) - Live tracker for 1H/2H release changes
- [Value Navigator](https://github.com/SahirVhora/sf-value-navigator) - Value realisation consulting framework
- [Pay Transparency](https://github.com/SahirVhora/sf-pay-transparency) - EU Pay Transparency Directive readiness
