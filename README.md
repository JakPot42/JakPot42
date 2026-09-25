# JakPot42

## What I'm building now

An independent check that has to pass before an automated system files, denies, or pays.

Two rules. Every material fact the decision relies on has to trace to a source that actually contains it. Every legal number it uses has to be the one in force on the date the decision covers. If either fails, the action stops, and the stop says what is missing or what is present but out of date. The check follows the published rule, so anyone can recompute a stop without trusting me. The law stays the authority, not the checker.

I'm starting with public benefits, where the rules are written down and a maintained rules engine already exists.

## The evidence so far

**[Redtape](https://github.com/JakPot42/redtape)** is a published benchmark, on the [Prime Intellect Environments Hub](https://app.primeintellect.ai/dashboard/environments/jakpotvin/redtape), that scores whether a model knows when a benefits question cannot be answered from the facts it was given. Answer keys come from PolicyEngine and are fixed when the tasks are generated, so no language model grades anything and every score can be reproduced from a cache. Its original headline result is retracted. Before re-running, I committed both possible corrections and the rule for choosing between them. The re-run, plus a disclosed follow-up analysis, showed the design could not test its own central claim, and the retraction sits at the top of the repository and the Hub listing. The newest model I tested applied next year's benefit amounts to this year's cases, which is the failure the check above is built to stop.

**Three bug reports filed against benchmarks I did not build**, each one a case where a correct answer was graded as wrong:

- [prime-envs #825](https://github.com/PrimeIntellect-ai/prime-envs/issues/825): the verifier passes test input through a single command-line argument, so on Linux any input over about 128 KB fails to start and a correct solution is recorded as failing.
- [prime-envs #826](https://github.com/PrimeIntellect-ai/prime-envs/issues/826): the verdict depends on how many cores the grading machine has and how busy it is, so the same solution can pass or fail from run to run.
- [human-eval PR #23, comment](https://github.com/openai/human-eval/pull/23#issuecomment-5781755077): HumanEval problem 116's tests pass in negative numbers that its own specification excludes.

**[PolicyEngine #9374](https://github.com/PolicyEngine/policyengine-us/issues/9374).** I reported two places where the rules engine my benchmark depends on diverged from the law. Half of that report was my mistake: my probe had hardcoded one state. I retracted that half publicly on the issue. The other half stands, and the maintainers invited a fix, which I'm preparing.

## Where the idea came from

[![Glassbox](https://img.shields.io/badge/glassbox-auditable%20human--in--the--loop%20AI-2563EB?style=for-the-badge)](https://github.com/JakPot42/glassbox)

**[Glassbox](https://github.com/JakPot42/glassbox)**: Every project below independently reinvented the same four disciplines: an LLM proposes, deterministic code decides, a human confirms before anything consequential happens, and the system's own limitations get disclosed, not hidden. Glassbox is what's left after distilling that pattern out of 70+ separate builds: an importable Python library for all four pieces, a machine-checkable specification (`glassbox-spec.json`) defining exactly what "glassbox" means, and a conformance checker that statically analyzes a real codebase against that spec. It never imports or executes the code, it just proves the guarantees hold.

It's tested against itself honestly, not just demoed. Run for real against four unmodified sibling projects in this portfolio, it scores each 56 to 68 out of 100, never a rigged 100, because none of them were built against this spec. And one piece of the library (bounded repair/retry on failed structured extraction) is disclosed as genuinely new: a portfolio-wide search found no project that re-prompts Claude on a bad response. Every one just fails loud. That gap, and the real file/line citations for everything else, are documented in [`docs/REFERENCE_IMPLEMENTATIONS.md`](https://github.com/JakPot42/glassbox/blob/master/docs/REFERENCE_IMPLEMENTATIONS.md).

## The receipt

**[LogChain](https://github.com/JakPot42/logchain)** keeps the record of each check: what was decided, from which facts, under which version of the rules, in an append-only log where any later edit is detectable. It is a Rust tool with a second, independent verifier in Python, and the two are checked against each other on every test run. Writing its format specification exposed a root collision in my own Merkle tree (the same class as CVE-2012-2459) that both implementations had agreed on. I shipped the fix as format version 2, built on RFC 6962, as a clean break that voids every version 1 root.

---

## Earlier work: the defense and national-security portfolio

The pattern above was distilled from these. More than eighty builds, mostly defense and national-security tools, built between June and August 2026. Several of the standalone web demos were later merged into [Arbor](https://arbor-vpa1.onrender.com), [Analyst's Desk](https://analysts-desk.onrender.com), and [Cleared Facility Suite](https://cleared-facility-suite.onrender.com). Live demos run on a free tier and can take about a minute to wake up.

---

## Start Here

[![Awesome Defense Tech](https://img.shields.io/badge/awesome--defense--tech-curated%20resource%20list-blue?style=for-the-badge)](https://github.com/JakPot42/awesome-defense-tech)

**[awesome-defense-tech](https://github.com/JakPot42/awesome-defense-tech)**: a curated list of every public API, open standard, and policy document used across this portfolio. 35+ free APIs (CISA KEV, USASpending.gov, Space-Track, USGS, EIA, WHO DON, congress.gov, CourtListener, SEC EDGAR, and more), 30+ frameworks (MITRE ATT&CK, DISARM, NIST AI RMF, DoD AI Ethical Principles, CNSA 2.0, NIST PQC, CMMC, Purdue Model, ICD 203), and 49 worked examples. If you're building in this space, start here.

---

## Defense Acquisition & Contracting

| Project | What it does | Demo |
|---|---|---|
| [SEAD 3 Auditor](https://github.com/JakPot42/sead3-auditor) | Parses cleared-employee disclosures, computes SEAD 3 reporting deadlines, generates FSO compliance briefs and DISS export files | [sead3-auditor.onrender.com](https://sead3-auditor.onrender.com) |
| [SAM Acquisition Agent](https://github.com/JakPot42/sam-acquisition-agent) | Monitors SAM.gov for relevant solicitations, reads RFPs, and drafts compliance matrices and capability statements | Merged into [Analyst's Desk](https://analysts-desk.onrender.com/sam/) |
| [ATO Accelerator](https://github.com/JakPot42/ato-accelerator) | Categorizes systems under FIPS 199, maps them to NIST 800-53 baselines, and drafts System Security Plan narratives control by control | Merged into [Cleared Facility Suite](https://cleared-facility-suite.onrender.com/ato/) |
| [CFIUS Screener](https://github.com/JakPot42/cfius-screener) | Screens foreign-investment transactions for CFIUS jurisdiction and mandatory-declaration triggers under 31 CFR Part 800; every determination cites the specific regulation | Merged into [Arbor](https://arbor-vpa1.onrender.com) |
| [Security Clearance Advisor](https://github.com/JakPot42/clearance-advisor) | Evaluates clearance eligibility against all 13 SEAD 4 adjudicative criteria with whole-person analysis and mitigating/aggravating factors from the Adjudicative Desk Reference | Merged into [Cleared Facility Suite](https://cleared-facility-suite.onrender.com/clearance/) |
| [Defense Budget Tracker](https://github.com/JakPot42/defense-budget-tracker) | Tracks DoD RDT&E / Procurement / O&M funding for AI/ML, Hypersonics, Space, and Cyber across FY2022 to 2026; CAGR trend analysis; NDAA provisions; USASpending.gov + congress.gov APIs | CLI, 204 tests |
| [Pre-Acquisition Intelligence Brief](https://github.com/JakPot42/acquisition-brief) | Generates a pre-deal intelligence brief from USPTO, CourtListener, SEC EDGAR, and SAM.gov: IP strength, litigation risk, regulatory exposure, contract dependency | Live in [Arbor](https://arbor-vpa1.onrender.com) |

---

## Threat Intelligence & Influence Operations

| Project | What it does |
|---|---|
| [SENTINEL](https://github.com/JakPot42/sentinel-io-engine) | Detects coordinated influence operations by clustering adversary narratives and classifying TTPs against the DISARM framework. Merged into [Analyst's Desk](https://analysts-desk.onrender.com/sentinel/) |
| [Dragonbridge Analyzer](https://github.com/JakPot42/dragonbridge-analyzer) | Scores content samples against 12 behavioral fingerprints from public Meta ATR, Google/Mandiant, and Stanford SIO Dragonbridge/Spamouflage takedown reports. Deterministic. Non-attribution framing enforced throughout. 230 tests. |
| [IP Theft Pattern Database](https://github.com/JakPot42/ip-theft-db) | Pattern database of documented intellectual property theft operations; scores a scenario against methods from public DoJ indictments and NCSC/FBI advisories. 443 tests. |
| [Infrastructure Exposure Assessor](https://github.com/JakPot42/infra-exposure-assessor) | Scores an OT/IT environment against documented Volt Typhoon TTPs (living-off-the-land binaries, SOHO router pivoting) from the CISA/NSA/FBI February 2024 joint advisory. 129 tests. |
| [OSINT Brief Generator](https://github.com/JakPot42/osint-brief) | Compiles an ICD 203-formatted intelligence brief for any named entity from open sources, with confidence levels and source citations |

---

## Critical Infrastructure

| Project | What it does |
|---|---|
| [GridPulse](https://github.com/JakPot42/gridpulse) | Regional electricity grid stress index. Fuses EIA API demand/generation data with NOAA weather forecasts. Six US regions. Four named scenarios (polar vortex, wind drop, solar drop, demand surge). CISA NCF framing. 221 tests. |
| [Water Security Stress Monitor](https://github.com/JakPot42/water-monitor) | USGS streamflow percentile + USDM drought severity → regional water stress score. Eight US watersheds. Colorado River Basin at CRITICAL (82.8/100) in demo. 391 tests. |
| [ICS/SCADA Vulnerability Assessor](https://github.com/JakPot42/ics-assessor) | Maps CISA ICS-CERT advisories to Purdue Model layers; scores OT exposure; flags Volt Typhoon attack vectors for internet-exposed assets. Three demo environments: water treatment, oil refinery, auto assembly. 225 tests. |
| [Cable Resilience Analyzer](https://github.com/JakPot42/cable-resilience) | NetworkX graph of global submarine cable infrastructure: N-1/N-2 failure simulation, betweenness centrality, chokepoint identification. [Live demo](https://cable-resilience-analyzer.onrender.com) |

---

## Space & Advanced Propulsion

| Project | What it does | Demo |
|---|---|---|
| [Orbital Sentinel](https://github.com/JakPot42/orbital-sentinel) | Space domain awareness: sgp4 propagation + Space-Track CDM ingestion + 3D Plotly orbital visualization. Flags satellite conjunction risk (Pc thresholds) and generates 5-section SDA intelligence briefs. | [orbital-sentinel-65cj.onrender.com](https://orbital-sentinel-65cj.onrender.com) |
| [TLE Propagator](https://github.com/JakPot42/tle-propagator) | From-scratch Rust SGP4 secular propagator: J2 nodal regression, B* drag, Newton-Raphson Kepler solver, TEME→ECEF coordinate chain. Library + CLI. 30 tests. | CLI, Rust |
| [LumenGrid Mission Calculator](https://github.com/JakPot42/lumengrid) | Live physics calculator comparing beamed-thermal vs chemical propulsion across four missions (LEO→GEO, Moon, Mars, Europa). Tsiolkovsky rocket equation, Rayleigh beam divergence, light-sail thrust (F = 2P/c), Hohmann transit times. Isp mass curve chart. | [jakpot42.github.io/lumengrid](https://jakpot42.github.io/lumengrid) *(GitHub Pages)* |

---

## Supply Chain & Foreign Investment Risk

| Project | What it does | Demo |
|---|---|---|
| [FriendShore](https://github.com/JakPot42/friendshore-supply-chain) | BOM → Tier 1-3 supply chain graph, adversary-nation single points of failure, OFAC SDN screening, allied alternatives | Merged into [Analyst's Desk](https://analysts-desk.onrender.com/friendshore/) |
| [GhostTrace](https://github.com/JakPot42/ghosttrace) | EDGAR beneficial ownership extraction with entity resolution, ChromaDB semantic search, OFAC screening, agentic deep-trace loop (5 tool calls) | Merged into [Arbor](https://arbor-vpa1.onrender.com) |
| [DIB Monitor](https://github.com/JakPot42/dib-monitor) | SEC 10-K Claude extraction + Monte Carlo GBM distress simulation (P(distress) at 1/2/3 years) + 13F foreign ownership screening | Merged into [Arbor](https://arbor-vpa1.onrender.com) |
| [Debt Exposure Monitor](https://github.com/JakPot42/debt-exposure-monitor) | Tracks lender identity behind a defense supplier's credit facilities and bond issuances: OFAC/BIS screening plus a curated foreign state-connected lender list neither equity nor physical supply chain data would surface | Live in [Arbor](https://arbor-vpa1.onrender.com) |
| [Critical Mineral Monitor](https://github.com/JakPot42/critical-mineral) | DoD-critical mineral supply chain exposure: production concentration, US import dependency, strategic reserve analysis | [critical-mineral-monitor.onrender.com](https://critical-mineral-monitor.onrender.com) |

---

## AI Safety, Ethics & Compliance

| Project | What it does | Demo |
|---|---|---|
| [RAI Compliance](https://github.com/JakPot42/rai-compliance) | Scores an AI system against all five DoD AI Ethical Principles across 20 criteria. Claude extracts evidence; deterministic rules produce the score. Claude never makes compliance determinations. | Merged into [Cleared Facility Suite](https://cleared-facility-suite.onrender.com/rai/) |
| [NCF TTX Generator](https://github.com/JakPot42/ncf-ttx-generator) | Generates tabletop exercise scenarios for any of CISA's 55 National Critical Functions using HSEEP exercise structure | [ncf-ttx-generator.onrender.com](https://ncf-ttx-generator.onrender.com) |
| [Guarden-FV](https://github.com/JakPot42/guarden-fv) | Z3 SMT-based formal verification of UAV behavioral rules. Checks logical consistency of autonomous decision policies. Rule-consistency checker, not a flight simulator. |

---

## Policy & Regulatory Analytics

| Project | What it does |
|---|---|
| [Regulatory Velocity Tracker](https://github.com/JakPot42/regulatory-velocity) | Z-score anomaly detection on rulemaking velocity by agency. Flags unusual acceleration or slowdown in DFARS, CMMC, ITAR, BIS, and SEAD rule publication. Federal Register API. 98 tests. |
| [Rulemaking Comment Analyzer](https://github.com/JakPot42/comment-analyzer) | Downloads all public comments from a Regulations.gov docket, classifies by position and stakeholder type with Claude Haiku, and produces a government decision memo. Demo: CMMC 2.0 docket. 131 tests. |
| [Civic RAG](https://github.com/JakPot42/civic-rag) | Retrieval-augmented generation over a town's council, school committee and planning board minutes (Tiverton, RI); every answer cites the meeting it came from | [civic-rag.onrender.com](https://civic-rag.onrender.com) |

---

## Formal Verification & AI Research

| Project | What it does |
|---|---|
| [Z3 Contract Checker](https://github.com/JakPot42/z3-contract) | Encodes contract clause term sheets as Z3 SMT constraints and reports logical contradictions and names the specific conflicting clauses |
| [race-condition](https://github.com/JakPot42/race-condition) | Multi-agent strategic simulator studying how individually rational agents produce collectively bad outcomes under competitive pressure, with Capability Race and Escalation Ladder scenarios |
| [redteam-eval](https://github.com/JakPot42/redteam-eval) | LLM red-teaming and evaluation framework for high-stakes government use cases: adversarial test suites, regression tracking, visual dashboards |

---

**Stack:** Python · FastAPI · Claude (Anthropic) · Click · Rich · SQLAlchemy · pandas · numpy · NetworkX · ChromaDB · Z3 · Jinja2 · Render · TypeScript · React · Next.js · D3.js · Chart.js · Rust

**Approach:** Claude extracts and synthesizes; deterministic Python rules make every decision. No LLM randomness in compliance, scoring, or attribution paths.
