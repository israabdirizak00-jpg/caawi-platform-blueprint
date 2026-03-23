# caawi-platform-blueprint

**For Somalis, by Somalis.**

Caawi is a bilingual Somali-English civic tech platform that helps non-English-speaking Somali immigrants in Minnesota navigate employment, housing, healthcare, legal aid, and community services. It is built on the CCLI (Civic Communication and Language Infrastructure) framework, which treats language access as an infrastructure problem rather than a service delivery problem.

---

## Repository Contents

| File | Description |
|------|-------------|
| `caawi-platform-blueprint.html` | **Platform blueprint** — interactive document covering research synthesis, intake form decision logic, user path flowchart, UX/UI design brief, and landing page preview. Open in any browser. |
| `Caawi_Partner_Outreach_Tracker.xlsx` | Partner outreach tracker — 18 organizations across 3 tiers with status tracking, templates, and CIT framework reference |
| `caawi_org_researcher.py` | Auto-research script — fetches org contact info from the web and writes it into the tracker |
| `requirements.txt` | Python dependencies for the research script |

## Platform Blueprint

The blueprint (`caawi-platform-blueprint.html`) is a single-file, GitHub-Pages-compatible document with five sections:

1. **Research Synthesis** — extrapolation of three foundational research areas (low-literacy onboarding patterns, refugee/immigrant technology adoption, Somali-specific language and literacy landscape) mapped to Caawi design decisions
2. **Intake Logic (Step 1)** — 6-question intake form with answer options, decision logic, and four routing variables (language, experience lane, service priority, context layer)
3. **User Paths (Step 2)** — SVG flowchart showing three experience lanes (Audio, Text, Helper) from intake through first success to account creation
4. **UX Brief (Step 3)** — design specifications for icon standards, audio/visual requirements, plain language rules, error recovery, navigation, and trust/cultural considerations, with Bubble.io implementation notes
5. **Landing Page (Step 4)** — fully styled bilingual landing page preview with deferred account creation and privacy-first messaging

## Partner Outreach

```bash
pip install -r requirements.txt

# Research all 18 organizations
python caawi_org_researcher.py --all

# Research a single org
python caawi_org_researcher.py --org "Brian Coyle"

# Preview results without writing to Excel
python caawi_org_researcher.py --all --dry-run
```

The script searches for each org's contact page, extracts emails, phone numbers, and staff titles, and writes results into the tracker (only fills empty cells, never overwrites manual entries). Activity is logged to `caawi_research_log.txt` with a JSON summary in `caawi_research_results.json`.

### Tracker Sheets

- **Outreach Tracker** — main log with status, contacts, partnership type, and alignment notes
- **Dashboard** — live summary of outreach status and domain coverage
- **Outreach Templates** — 5 ready-to-use message templates
- **CIT Framework** — reference linking Civic Information Theory to Caawi's structural argument

## Design Principles

- **Audio-first, not text-first** — spoken Somali is a primary processing mode, not a fallback
- **Three-lane user model** — written-Somali capable / spoken-Somali preferred / assisted-bilingual
- **Try first, configure later** — value before account creation
- **Helper-compatible** — every screen works for assisted use (caseworker, family member)
- **One action per screen** — no dense multi-field forms
- **Composability over competition** — Caawi connects to existing service providers, not replaces them

## Tech Stack

- **Platform:** Bubble.io (no-code)
- **Research:** Python (openpyxl, requests, beautifulsoup4)
- **Design documentation:** HTML/CSS/SVG (this repo)

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

*Built by Isra Ali — Minneapolis, MN*
