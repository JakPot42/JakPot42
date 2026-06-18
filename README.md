# JakPot42

I'm building AI-powered tools for national security and defense compliance — the kind of work that used to take analysts days and now takes minutes. My focus is on problems that are real, funded, and underserved by existing software: personnel security reporting, acquisition intelligence, supply chain risk, ATO documentation, influence operation detection, beneficial ownership tracing, and foreign investment screening. Every project in this portfolio is deployed, live, and demo-ready.

---

## Defense & National Security Compliance Suite

| Project | What it does | Live demo |
|---|---|---|
| [SEAD 3 Auditor](https://github.com/JakPot42/sead3-auditor) | Parses cleared-employee disclosures, computes SEAD 3 reporting deadlines, and generates FSO compliance briefs and DISS export files | [sead3-auditor.onrender.com](https://sead3-auditor.onrender.com) |
| [SAM Acquisition Agent](https://github.com/JakPot42/sam-acquisition-agent) | Monitors SAM.gov for relevant solicitations, reads RFPs, and drafts compliance matrices and capability statements | [sam-acquisition-agent.onrender.com](https://sam-acquisition-agent.onrender.com) |
| [FriendShore](https://github.com/JakPot42/friendshore-supply-chain) | Maps Tier 1–3 supplier relationships from bills of materials, flags adversary-nation single points of failure, and recommends allied alternatives | [friendshore-supply-chain.onrender.com](https://friendshore-supply-chain.onrender.com) |
| [ATO Accelerator](https://github.com/JakPot42/ato-accelerator) | Categorizes systems under FIPS 199, maps them to NIST 800-53 baselines, and drafts System Security Plan narratives control by control | [ato-accelerator.onrender.com](https://ato-accelerator.onrender.com) |
| [SENTINEL](https://github.com/JakPot42/sentinel-io-engine) | Detects coordinated influence operations by clustering adversary narratives and classifying TTPs against the DISARM framework | [sentinel-io-engine.onrender.com](https://sentinel-io-engine.onrender.com) |
| [GhostTrace](https://github.com/JakPot42/ghosttrace) | Pulls SEC EDGAR beneficial ownership filings, extracts every owner and subsidiary with Claude, and scores the structure for shell-company and sanctions risk | [ghosttrace-aose.onrender.com](https://ghosttrace-aose.onrender.com) |
| [CFIUS Screener](https://github.com/JakPot42/cfius-screener) | Screens foreign-investment transactions for CFIUS jurisdiction and mandatory-declaration triggers under 31 CFR Part 800, with every determination citing the regulation that drives it | [cfius-screener.onrender.com](https://cfius-screener.onrender.com) |
| [DIB Monitor](https://github.com/JakPot42/dib-monitor) | Reads SEC 10-K filings with Claude to extract debt terms and covenant language, runs a Monte Carlo GBM distress simulation (P(distress) at 1/2/3 years), and screens 13F ownership for CFIUS-relevant foreign connections — outputs a Supplier Financial Resilience Report | [dib-monitor.onrender.com](https://dib-monitor.onrender.com) |
| [Cable Resilience Analyzer](https://github.com/JakPot42/cable-resilience) | NetworkX graph of global submarine cable infrastructure — betweenness centrality ranks landing-station chokepoints, N-1/N-2 cable-cut simulation measures connectivity and capacity loss, Folium interactive map with risk heat layer; 3 demo scenarios: Taiwan Strait, Red Sea, Singapore hub | [cable-resilience-analyzer.onrender.com](https://cable-resilience-analyzer.onrender.com) |

---

## AI Systems Research

| Project | What it does |
|---|---|
| [race-condition](https://github.com/JakPot42/race-condition) | Multi-agent strategic simulator studying how individually rational Claude-backed agents produce collectively bad outcomes under competitive pressure — two scenarios: Capability Race and Escalation Ladder |
| [redteam-eval](https://github.com/JakPot42/redteam-eval) | CLI + pip-installable LLM red-teaming and evaluation framework calibrated for high-stakes government and regulatory use cases — adversarial test suites, SQLite regression tracking, and visual dashboards |

---

## Formal Verification

| Project | What it does |
|---|---|
| [z3-contract](https://github.com/JakPot42/z3-contract) | CLI tool that encodes contract term sheets as Z3 SMT constraints and reports logical contradictions — names the specific conflicting clauses if unsatisfiable. Catches both boolean contradictions (automatic vesting acceleration + board veto requiring prior approval) and arithmetic ones (liquidation preference floors that together exceed exit proceeds). |

---

## Platform Accountability & Collective Intelligence

| Project | What it does | Live demo / Registry |
|---|---|---|
| [Carta](https://github.com/JakPot42/carta) | Open standard + CLI for auditing platform power dynamics. 18 criteria across 6 categories (data portability, deletion rights, terms notice, surveillance, exit costs, accountability). `carta watch` diffs a platform's ToS month-over-month and alerts you to changes. | 3 platforms audited: Mastodon (Platinum, 88.3), GitHub (Gold, 76.8), X/Twitter (Silver, 53.8) |
| [Agora](https://github.com/JakPot42/agora) | Collective deliberation platform — people submit beliefs, values, needs, and proposals; three Claude agents (Synthesizer, Devil's Advocate, Bridge Builder) synthesize them into a live D3 force graph of agreements, tensions, and bridges. Click a tension to open the Bridge Builder's analysis of what each side is actually protecting and a concrete move that honors both. | [agora-oaje.onrender.com](https://agora-oaje.onrender.com) |

---

**Stack:** Python · FastAPI · Claude (Anthropic) · SQLAlchemy · NetworkX · PyYAML · Jinja2 · Render · TypeScript · Next.js · Drizzle ORM · D3.js · Z3
