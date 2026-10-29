# Earlier work: the defense and national-security portfolio

The pattern on [my profile page](https://github.com/JakPot42) was distilled from these. More than eighty builds, mostly defense and national-security tools, built between June and August 2026. Several of the standalone web demos were later merged into [Arbor](https://arbor-vpa1.onrender.com), [Analyst's Desk](https://analysts-desk.onrender.com), and [Cleared Facility Suite](https://cleared-facility-suite.onrender.com). Live demos run on a free tier and can take about a minute to wake up.

---

## A resource list

[![Awesome Defense Tech](https://img.shields.io/badge/awesome--defense--tech-curated%20resource%20list-blue?style=for-the-badge)](https://github.com/JakPot42/awesome-defense-tech)

**[awesome-defense-tech](https://github.com/JakPot42/awesome-defense-tech)**: a curated list of public APIs, open standards, policy documents and worked examples for building national-security and defense-adjacent software. 35+ free APIs (CISA KEV, USASpending.gov, Space-Track, USGS, EIA, WHO DON, congress.gov, CourtListener, SEC EDGAR, and more), 30+ frameworks (MITRE ATT&CK, DISARM, NIST AI RMF, DoD AI Ethical Principles, CNSA 2.0, NIST PQC, CMMC, Purdue Model, ICD 203), and 46 worked examples. If you're building in this space, it is a place to start.

---

## Defense Acquisition & Contracting

| Project | What it does | Demo |
|---|---|---|
| [SEAD 3 Auditor](https://github.com/JakPot42/sead3-auditor) | Parses cleared-employee disclosures, computes SEAD 3 reporting deadlines, generates FSO compliance briefs and DISS export files | [sead3-auditor.onrender.com](https://sead3-auditor.onrender.com) |
| [SAM Acquisition Agent](https://github.com/JakPot42/sam-acquisition-agent) | Searches SAM.gov for active solicitations and uses Claude to produce a compliance matrix and a capability statement outline | Merged into [Analyst's Desk](https://analysts-desk.onrender.com/sam/) |
| [ATO Accelerator](https://github.com/JakPot42/ato-accelerator) | Categorizes systems under FIPS 199, maps them to NIST 800-53 baselines, and drafts System Security Plan narratives control by control | Merged into [Cleared Facility Suite](https://cleared-facility-suite.onrender.com/ato/) |
| [CFIUS Screener](https://github.com/JakPot42/cfius-screener) | Screens foreign-investment transactions for CFIUS jurisdiction and mandatory-declaration triggers under 31 CFR Part 800; every determination cites the specific regulation | Merged into [Arbor](https://arbor-vpa1.onrender.com) |
| [Security Clearance Advisor](https://github.com/JakPot42/clearance-advisor) | Explains the 13 SEAD 4 adjudicative guidelines and helps a candidate prepare for the clearance interview. It explains the process and never predicts an adjudication outcome | Merged into [Cleared Facility Suite](https://cleared-facility-suite.onrender.com/clearance/) |
| [Defense Budget Tracker](https://github.com/JakPot42/defense-budget-tracker) | Tracks DoD RDT&E / Procurement / O&M funding for AI/ML, Hypersonics, Space, and Cyber across FY2022 to 2026; CAGR trend analysis; NDAA provisions; USASpending.gov + congress.gov APIs | CLI |
| [Pre-Acquisition Intelligence Brief](https://github.com/JakPot42/acquisition-brief) | Compiles a scored due-diligence brief on a target company from USPTO patents, CourtListener litigation, SEC EDGAR filings and USASpending contract history: IP strength, litigation risk, regulatory exposure | Live in [Arbor](https://arbor-vpa1.onrender.com) |

---

## Threat Intelligence & Influence Operations

| Project | What it does |
|---|---|
| [SENTINEL](https://github.com/JakPot42/sentinel-io-engine) | Detects coordinated influence operations by clustering adversary narratives and classifying TTPs against the DISARM framework. Merged into [Analyst's Desk](https://analysts-desk.onrender.com/sentinel/) |
| [Dragonbridge Analyzer](https://github.com/JakPot42/dragonbridge-analyzer) | Scores a set of social-media accounts against 12 behavioral indicators drawn from published takedown reports on the Dragonbridge/Spamouflage network. Deterministic. It makes no attribution claim about any real account or person. |
| [Infrastructure Exposure Assessor](https://github.com/JakPot42/infra-exposure-assessor) | Scores an OT/IT environment against documented Volt Typhoon TTPs (living-off-the-land binaries, SOHO router pivoting) from CISA advisories AA23-144A and AA24-038A. |
| [OSINT Brief Generator](https://github.com/JakPot42/osint-brief) | Runs a bounded search loop across five public sources for a company, technology or topic, then writes a SITREP-style brief with a HIGH, MEDIUM or LOW confidence rating on each finding |

---

## Critical Infrastructure

| Project | What it does |
|---|---|
| [GridPulse](https://github.com/JakPot42/gridpulse) | Regional electricity grid stress index. Fuses EIA API demand/generation data with NOAA weather forecasts. Six US regions. Four named scenarios (polar vortex, wind drop, solar drop, demand surge). |
| [Water Security Stress Monitor](https://github.com/JakPot42/water-monitor) | USGS streamflow percentiles and US Drought Monitor severity combined into a 0 to 100 regional water-stress score. Eight US regions. Four what-if scenarios. |
| [ICS/SCADA Vulnerability Assessor](https://github.com/JakPot42/ics-assessor) | Scores a described OT environment against published CISA ICS advisories and the Purdue Model. Deterministic exposure score, with a report of which advisories apply and why. |
| [Cable Resilience Analyzer](https://github.com/JakPot42/cable-resilience) | NetworkX graph of global submarine cable infrastructure: N-1/N-2 failure simulation, betweenness centrality, chokepoint identification. [Live demo](https://cable-resilience-analyzer.onrender.com) |

---

## Space & Advanced Propulsion

| Project | What it does | Demo |
|---|---|---|
| [Orbital Sentinel](https://github.com/JakPot42/orbital-sentinel) | Space domain awareness: sgp4 propagation + Space-Track CDM ingestion + 3D Plotly orbital visualization. Ranks conjunctions by collision probability (Pc) and writes a plain-language SDA brief. | [orbital-sentinel-65cj.onrender.com](https://orbital-sentinel-65cj.onrender.com) |
| [TLE Propagator](https://github.com/JakPot42/tle-propagator) | From-scratch Rust implementation of a simplified, secular-only SGP4 propagator: J2 nodal regression, B* drag, Newton-Raphson Kepler solver, TEME→ECEF coordinate chain. Library + CLI. Not validated against the full SGP4 standard. | CLI, Rust |
| [LumenGrid Mission Calculator](https://github.com/JakPot42/lumengrid) | Live physics calculator comparing beamed-thermal vs chemical propulsion across four missions (LEO→GEO, Moon, Mars, Europa). Tsiolkovsky rocket equation, Rayleigh beam divergence, light-sail thrust (F = 2P/c), Hohmann transit times. Isp mass curve chart. | [jakpot42.github.io/lumengrid](https://jakpot42.github.io/lumengrid) *(GitHub Pages)* |

---

## Supply Chain & Foreign Investment Risk

| Project | What it does | Demo |
|---|---|---|
| FriendShore | BOM → Tier 1-3 supply chain graph, adversary-nation single points of failure, allied alternatives | Merged into [Analyst's Desk](https://analysts-desk.onrender.com/friendshore/) |
| [GhostTrace](https://github.com/JakPot42/ghosttrace) | EDGAR beneficial ownership extraction with entity resolution, ChromaDB semantic search, OFAC screening, agentic deep-trace loop (5 tool calls) | Merged into [Arbor](https://arbor-vpa1.onrender.com) |
| [DIB Monitor](https://github.com/JakPot42/dib-monitor) | SEC 10-K Claude extraction + Monte Carlo GBM distress simulation (P(distress) at 1/2/3 years) + 13F foreign ownership screening | Merged into [Arbor](https://arbor-vpa1.onrender.com) |
| [Debt Exposure Monitor](https://github.com/JakPot42/debt-exposure-monitor) | Tracks lender identity behind a defense supplier's credit facilities and bond issuances: OFAC/BIS screening plus a curated foreign state-connected lender list neither equity nor physical supply chain data would surface | Live in [Arbor](https://arbor-vpa1.onrender.com) |
| [Critical Mineral Monitor](https://github.com/JakPot42/critical-mineral) | Scores critical minerals by US import dependency, DoD criticality and substitutability, and matches each to near-Earth asteroid candidates from NASA data, with a one-page brief | [critical-mineral-monitor.onrender.com](https://critical-mineral-monitor.onrender.com) |

---

## AI Safety, Ethics & Compliance

| Project | What it does | Demo |
|---|---|---|
| [RAI Compliance](https://github.com/JakPot42/rai-compliance) | A 20-criteria assessment against the five DoD AI Ethical Principles. Claude characterizes the system and drafts a narrative for each criterion. A person sets each status, and the engine computes the score from those. | Merged into [Cleared Facility Suite](https://cleared-facility-suite.onrender.com/rai/) |
| [NCF TTX Generator](https://github.com/JakPot42/ncf-ttx-generator) | Generates a tabletop exercise package for any of 50 CISA National Critical Functions: scenario injects, discussion questions, decision points and facilitator notes | [ncf-ttx-generator.onrender.com](https://ncf-ttx-generator.onrender.com) |
| [Guarden-FV](https://github.com/JakPot42/guarden-fv) | Z3-based check of UAV geofencing rule sets for logical contradictions. Discrete rule logic only. It does not model flight dynamics and gives no safety guarantee about any aircraft. |

---

## Policy & Regulatory Analytics

| Project | What it does |
|---|---|
| [Regulatory Velocity Tracker](https://github.com/JakPot42/regulatory-velocity) | Z-score on monthly Federal Register publication counts for a regulatory domain, such as CMMC, ITAR, DFARS, BIS export controls or SEAD. Flags a domain whose recent activity is unusually high against its own baseline. |
| [Rulemaking Comment Analyzer](https://github.com/JakPot42/comment-analyzer) | Pulls the public comments on a Regulations.gov docket, uses Claude to classify each by theme, stakeholder type and argument, clusters them deterministically, and drafts a structured decision memo. Demo: a real CMMC rulemaking docket. |

---

## Formal Verification & AI Research

| Project | What it does |
|---|---|
| [Z3 Contract Checker](https://github.com/JakPot42/z3-contract) | Encodes contract clause term sheets as Z3 SMT constraints and reports logical contradictions and names the specific conflicting clauses |
| [race-condition](https://github.com/JakPot42/race-condition) | Multi-agent strategic simulator studying how individually rational agents produce collectively bad outcomes under competitive pressure, with Capability Race and Escalation Ladder scenarios |
| [redteam-eval](https://github.com/JakPot42/redteam-eval) | LLM red-teaming and evaluation framework for high-stakes government use cases: adversarial test suites, regression tracking, visual dashboards |

---

**Stack:** Python · FastAPI · Claude (Anthropic) · Click · Rich · SQLAlchemy · pandas · numpy · NetworkX · ChromaDB · Z3 · Jinja2 · Render · TypeScript · React · Next.js · D3.js · Chart.js · Rust
