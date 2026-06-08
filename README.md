1|# SF Impact Brief
2|
3|Generate personalised SAP SuccessFactors release impact briefs in seconds. Select your client's modules, pick a version, and get a tiered action plan - what you must act on, what to test, and what's nice to know.
4|
5|**Live at: https://sahirvhora.github.io/sf-impact-brief**
6|
7|## What it does
8|
9|- **Module-based filtering** - select any of 40 SF modules across 8 areas (Employee Central, Compensation, Talent, Recruiting, Platform, Learning, AI, Payroll)
10|- **Three-tier prioritisation** - every update is classified into MUST ACT (critical/deprecated), SHOULD TEST (high impact), or NICE TO KNOW (medium/low)
11|- **Upsell opportunities** - new features you could implement for clients, surfaced automatically
12|- **Version-aware** - toggle between 1H 2026, 2H 2026, or all releases
13|- **Print-friendly** - print or save as PDF with clean formatting
14|- **Export to JSON** - download the filtered data for your own analysis
15|- **Dark/light theme** - navy+gold dark theme, warm parchment light theme
16|- **Zero setup** - single HTML file, no backend, no login, always free
17|
18|## How it works
19|
20|```
21|sf-release-update (weekly cron -> updates.json)
22|       |
23|       v
24|sf-impact-brief (fetches live JSON -> filters by module -> generates tiered brief)
25|```
26|
27|This tool fetches live data from [SF Release Update](https://sahirvhora.github.io/sf-release-update/), so it's always current. No scraping, no maintenance - the data updates automatically every Monday.
28|
29|## Use cases
30|
31|- **Consultants** - generate a personalised release impact brief for each client in 30 seconds
32|- **Implementation partners** - send proactive release readiness reports to all your managed accounts
33|- **Customer COEs** - filter 492 updates down to what actually matters for YOUR modules
34|- **Sales/pre-sales** - use the Upsell Opportunities section to spot implementation prospects
35|
36|## Architecture
37|
38|```
39|sf-impact-brief/
40|├── index.html      # Single-file app (HTML/CSS/JS)
41|├── favicon.svg     # Favicon
42|├── preview.png     # OG image for social sharing
43|├── preview.svg     # Editable source for preview image
44|└── README.md
45|```
46|
47|No build step. No dependencies. Deploy to GitHub Pages directly from the repo root.
48|
49|## Setup
50|
51|```bash
52|# Serve locally
53|python3 -m http.server 8766
54|# Open http://localhost:8766
55|```
56|
57|The page fetches `updates.json` from the live SF Release Update site. No local data needed.
58|
59|## Data source
60|
61|Powered by [SF Release Update](https://github.com/SahirVhora/sf-release-update) - a weekly-scraped tracker of all SAP SuccessFactors What's New updates. The scraper runs every Monday via GitHub Actions and publishes fresh data to GitHub Pages.
62|
63|Cross-links:
64|- **SF Release Update** - browse all 492 updates: [sahirvhora.github.io/sf-release-update](https://sahirvhora.github.io/sf-release-update)
65|- **SF Impact Brief** - generate personalised briefs: [sahirvhora.github.io/sf-impact-brief](https://sahirvhora.github.io/sf-impact-brief)
66|
67|## Related SAP SuccessFactors tools
68|
69|This project is part of a wider SAP SuccessFactors supplementary tools suite.
70|
71|Start with SF Compass for the full hub: https://sahirvhora.github.io/sf-compass/
72|
73|| Tool | Purpose |
74||---|---|
75|| SF Compass | Feasibility answers, implementation guidance, and links to the full tool suite |
76|| SF Release Update | Release impact tracking - browse all 492 updates |
77|| **SF Impact Brief** | **Personalised briefs from release data - this tool** |
78|| SF Pay Transparency | EU Pay Transparency readiness and evidence workflow framing |
79|| SF Value Navigator | Value realisation and sponsor-facing consulting framework |
80|| SF Position Integrity Checker | Position hierarchy, incumbency, and EC data-quality validation |
81|| SAPSF ObjectSync | Controlled foundation-object synchronisation between SF environments |
82|