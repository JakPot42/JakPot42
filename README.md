# JakPot42

I'm building AI-powered tools for national security and defense — the kind of work that used to take analysts days and now takes minutes. **50 projects in 16 days.** My focus is on problems that are real, funded, and underserved by existing software: program funding analysis, acquisition intelligence, supply chain risk, ATO documentation, influence operation detection, beneficial ownership tracing, foreign investment screening, and critical infrastructure resilience. Every project is deployed, live, and demo-ready.

---

## Start Here

[![Awesome Defense Tech](https://img.shields.io/badge/awesome--defense--tech-curated%20resource%20list-blue?style=for-the-badge)](https://github.com/JakPot42/awesome-defense-tech)

**[awesome-defense-tech](https://github.com/JakPot42/awesome-defense-tech)** — A curated list of every public API, open standard, and policy document used across this portfolio. 35+ free APIs (CISA KEV, USASpending.gov, Space-Track, USGS, EIA, WHO DON, congress.gov, CourtListener, SEC EDGAR, and more), 30+ frameworks (MITRE ATT&CK, DISARM, NIST AI RMF, DoD AI Ethical Principles, CNSA 2.0, NIST PQC, CMMC, Purdue Model, ICD 203), and 49 worked examples. If you're building in this space, start here.

---

## Defense Acquisition & Contracting

| Project | What it does | Demo |
|---|---|---|
| [SEAD 3 Auditor](https://github.com/JakPot42/sead3-auditor) | Parses cleared-employee disclosures, computes SEAD 3 reporting deadlines, generates FSO compliance briefs and DISS export files | [sead3-auditor.onrender.com](https://sead3-auditor.onrender.com) |
| [SAM Acquisition Agent](https://github.com/JakPot42/sam-acquisition-agent) | Monitors SAM.gov for relevant solicitations, reads RFPs, and drafts compliance matrices and capability statements | [sam-acquisition-agent.onrender.com](https://sam-acquisition-agent.onrender.com) |
| [ATO Accelerator](https://github.com/JakPot42/ato-accelerator) | Categorizes systems under FIPS 199, maps them to NIST 800-53 baselines, and drafts System Security Plan narratives control by control | [ato-accelerator.onrender.com](https://ato-accelerator.onrender.com) |
| [CFIUS Screener](https://github.com/JakPot42/cfius-screener) | Screens foreign-investment transactions for CFIUS jurisdiction and mandatory-declaration triggers under 31 CFR Part 800 — every determination cites the specific regulation | [cfius-screener.onrender.com](https://cfius-screener.onrender.com) |
| [Security Clearance Advisor](https://github.com/JakPot42/clearance-advisor) | Evaluates clearance eligibility against all 13 SEAD 4 adjudicative criteria with whole-person analysis and mitigating/aggravating factors from the Adjudicative Desk Reference | [clearance-advisor.onrender.com](https://clearance-advisor.onrender.com) |
| [Defense Budget Tracker](https://github.com/JakPot42/defense-budget-tracker) | Tracks DoD RDT&E / Procurement / O&M funding for AI/ML, Hypersonics, Space, and Cyber across FY2022–2026; CAGR trend analysis; NDAA provisions; USASpending.gov + congress.gov APIs | CLI — 204 tests |
| [Pre-Acquisition Intelligence Brief](https://github.com/JakPot42/acquisition-brief) | Generates a pre-deal intelligence brief from USPTO, CourtListener, SEC EDGAR, and SAM.gov — IP strength, litigation risk, regulatory exposure, contract dependency | CLI — 221 tests |

---

## Threat Intelligence & Influence Operations

| Project | What it does |
|---|---|
| [SENTINEL](https://github.com/JakPot42/sentinel-io-engine) | Detects coordinated influence operations by clustering adversary narratives and classifying TTPs against the DISARM framework — [live demo](https://sentinel-io-engine.onrender.com) |
| [Dragonbridge Analyzer](https://github.com/JakPot42/dragonbridge-analyzer) | Scores content samples against 12 behavioral fingerprints from public Meta ATR, Google/Mandiant, and Stanford SIO Dragonbridge/Spamouflage takedown reports. Deterministic. Non-attribution framing enforced throughout. 230 tests. |
| [IP Theft Pattern Database](https://github.com/JakPot42/ip-theft-db) | Pattern database of documented intellectual property theft operations; scores a scenario against methods from public DoJ indictments and NCSC/FBI advisories. 443 tests. |
| [Volt Typhoon Exposure Assessor](https://github.com/JakPot42/volt-typhoon) | Scores an OT/IT environment against documented Volt Typhoon TTPs — living-off-the-land binaries, SOHO router pivoting — from the CISA/NSA/FBI February 2024 joint advisory. 129 tests. |
| [OSINT Brief Generator](https://github.com/JakPot42/osint-brief) | Compiles an ICD 203-formatted intelligence brief for any named entity from open sources, with confidence levels and source citations |

---

## Critical Infrastructure

| Project | What it does |
|---|---|
| [GridPulse](https://github.com/JakPot42/gridpulse) | Regional electricity grid stress index — fuses EIA API demand/generation data with NOAA weather forecasts. Six US regions. Four named scenarios (polar vortex, wind drop, solar drop, demand surge). CISA NCF framing. 221 tests. |
| [Water Security Stress Monitor](https://github.com/JakPot42/water-monitor) | USGS streamflow percentile + USDM drought severity → regional water stress score. Eight US watersheds. Colorado River Basin at CRITICAL (82.8/100) in demo. 391 tests. |
| [ICS/SCADA Vulnerability Assessor](https://github.com/JakPot42/ics-assessor) | Maps CISA ICS-CERT advisories to Purdue Model layers; scores OT exposure; flags Volt Typhoon attack vectors for internet-exposed assets. Three demo environments: water treatment, oil refinery, auto assembly. 225 tests. |
| [Cable Resilience Analyzer](https://github.com/JakPot42/cable-resilience-analyzer) | NetworkX graph of global submarine cable infrastructure — N-1/N-2 failure simulation, betweenness centrality, chokepoint identification — [live demo](https://cable-resilience-analyzer.onrender.com) |

---

## Space & Advanced Propulsion

| Project | What it does | Demo |
|---|---|---|
| [Orbital Sentinel](https://github.com/JakPot42/orbital-sentinel) | Space domain awareness — sgp4 propagation + Space-Track CDM ingestion + 3D Plotly orbital visualization. Flags satellite conjunction risk (Pc thresholds) and generates 5-section SDA intelligence briefs. | [orbital-sentinel-65cj.onrender.com](https://orbital-sentinel-65cj.onrender.com) |
| [TLE Propagator](https://github.com/JakPot42/tle-propagator) | From-scratch Rust SGP4 secular propagator — J2 nodal regression, B* drag, Newton-Raphson Kepler solver, TEME→ECEF coordinate chain. Library + CLI. 30 tests. | CLI — Rust |
| [LumenGrid Mission Calculator](https://github.com/JakPot42/lumengrid) | Live physics calculator comparing beamed-thermal vs chemical propulsion across four missions (LEO→GEO, Moon, Mars, Europa). Tsiolkovsky rocket equation, Rayleigh beam divergence, light-sail thrust (F = 2P/c), Hohmann transit times. Isp mass curve chart. | [jakpot42.github.io/lumengrid](https://jakpot42.github.io/lumengrid) *(GitHub Pages)* |

---

## Supply Chain & Foreign Investment Risk

| Project | What it does | Demo |
|---|---|---|
| [FriendShore](https://github.com/JakPot42/friendshore-supply-chain) | BOM → Tier 1-3 supply chain graph, adversary-nation single points of failure, OFAC SDN screening, allied alternatives | [friendshore-supply-chain.onrender.com](https://friendshore-supply-chain.onrender.com) |
| [GhostTrace](https://github.com/JakPot42/ghosttrace) | EDGAR beneficial ownership extraction with entity resolution, ChromaDB semantic search, OFAC screening, agentic deep-trace loop (5 tool calls) | [ghosttrace-aose.onrender.com](https://ghosttrace-aose.onrender.com) |
| [DIB Monitor](https://github.com/JakPot42/dib-monitor) | SEC 10-K Claude extraction + Monte Carlo GBM distress simulation (P(distress) at 1/2/3 years) + 13F foreign ownership screening | [dib-monitor.onrender.com](https://dib-monitor.onrender.com) |
| [Critical Mineral Monitor](https://github.com/JakPot42/critical-mineral-monitor) | DoD-critical mineral supply chain exposure — production concentration, US import dependency, strategic reserve analysis | [critical-mineral-monitor.onrender.com](https://critical-mineral-monitor.onrender.com) |

---

## AI Safety, Ethics & Compliance

| Project | What it does | Demo |
|---|---|---|
| [RAI Compliance](https://github.com/JakPot42/rai-compliance) | Scores an AI system against all five DoD AI Ethical Principles across 20 criteria. Claude extracts evidence; deterministic rules produce the score. Claude never makes compliance determinations. | [rai-compliance.onrender.com](https://rai-compliance.onrender.com) |
| [NCF TTX Generator](https://github.com/JakPot42/ncf-ttx-generator) | Generates tabletop exercise scenarios for any of CISA's 55 National Critical Functions using HSEEP exercise structure | [ncf-ttx-generator.onrender.com](https://ncf-ttx-generator.onrender.com) |
| [Guarden-FV](https://github.com/JakPot42/guarden-fv) | Z3 SMT-based formal verification of UAV behavioral rules — checks logical consistency of autonomous decision policies. Rule-consistency checker, not a flight simulator. |

---

## Policy & Regulatory Analytics

| Project | What it does |
|---|---|
| [Regulatory Velocity Tracker](https://github.com/JakPot42/regulatory-velocity) | Z-score anomaly detection on rulemaking velocity by agency. Flags unusual acceleration or slowdown in DFARS, CMMC, ITAR, BIS, and SEAD rule publication. Federal Register API. 98 tests. |
| [Rulemaking Comment Analyzer](https://github.com/JakPot42/comment-analyzer) | Downloads all public comments from a Regulations.gov docket, classifies by position and stakeholder type with Claude Haiku, and produces a government decision memo. Demo: CMMC 2.0 docket. 131 tests. |
| [Civic RAG](https://github.com/JakPot42/civic-rag) | Retrieval-augmented generation over federal regulations and agency guidance — answers policy questions with citations to source documents | [civic-rag.onrender.com](https://civic-rag.onrender.com) |

---

## Formal Verification & AI Research

| Project | What it does |
|---|---|
| [Z3 Contract Checker](https://github.com/JakPot42/z3-contract) | Encodes contract clause term sheets as Z3 SMT constraints and reports logical contradictions — names the specific conflicting clauses |
| [race-condition](https://github.com/JakPot42/race-condition) | Multi-agent strategic simulator studying how individually rational agents produce collectively bad outcomes under competitive pressure — Capability Race and Escalation Ladder scenarios |
| [redteam-eval](https://github.com/JakPot42/redteam-eval) | LLM red-teaming and evaluation framework for high-stakes government use cases — adversarial test suites, regression tracking, visual dashboards |

---

**Stack:** Python · FastAPI · Claude (Anthropic) · Click · Rich · SQLAlchemy · pandas · numpy · NetworkX · ChromaDB · Z3 · Jinja2 · Render · TypeScript · React · Next.js · D3.js · Chart.js · Rust

**Approach:** Claude extracts and synthesizes; deterministic Python rules make every decision. No LLM randomness in compliance, scoring, or attribution paths.
