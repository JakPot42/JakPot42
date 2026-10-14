# Jak Potvin

I build checks that sit between an automated system and a consequential action. One rule runs through all of it:

> Nothing automated should file, deny or pay unless the facts are in the source and the rule is the one in force.

If either part fails, the action stops, and the stop says what is missing or what is present but out of date. I'm starting with US public benefits, where the rules are written down and a maintained rules engine already exists.

Everything below runs on public or synthetic data. None of it is in production use, and none of it is peer-reviewed.

I design these projects and direct their build. The code is written with Claude Code; I review the specifications, the results and the READMEs.

## Projects

| Project | What it is | Status |
|---|---|---|
| [asof-gate](https://github.com/JakPot42/asof-gate) | A check that runs after an AI intake step proposes the facts of a SNAP case and before the benefit is computed. It stops the case when a fact does not trace to the household's own documents, or a legal figure is not the one in force on the decision date. A second example applies the same check to a tax return. | **Demonstration.** Six SNAP cases on four synthetic households. The intake step is a fixture written by hand, not a model. A second implementation recomputes every verdict. |
| [redtape](https://github.com/JakPot42/redtape) | Evaluation environments for US public-benefits work, published on the [Prime Intellect Environments Hub](https://app.primeintellect.ai/dashboard/environments/jakpotvin/redtape). They score whether a model knows which facts a question needs and when it cannot answer from the facts it was given. | **Published, with its headline result retracted.** The retraction is the first thing in the README. Three models have been run on the corrected tasks. |
| [snap-qc-analysis](https://github.com/JakPot42/snap-qc-analysis) | An analysis of USDA's public SNAP quality-control data. What share of payment error dollars could a deterministic check catch? In the FY 2024 file, 15 to 36 percent, almost all of it from checking facts and very little from checking rules. | **Finished analysis.** The plan carries an independent timestamp. The README separates what that timestamp proves from what rests on my word. |
| [logchain](https://github.com/JakPot42/logchain) | A log journal in Rust in which a later edit to any entry is detectable. A second verifier, written in Python from the format specification, shares no code with it. | **Working command-line tool, format version 2.** Version 1 had a root collision, found while writing the format specification. Its roots are void. |
| [sentinel-ledger](https://github.com/JakPot42/sentinel-ledger) | A recorder for a machine's command path. It signs a record of each command, and a gate on the actuator's side passes a command only if it arrives inside a signed record. Includes a witness and an independent verifier. | **First build, on a simulated machine.** Not certified and not a safety system. The README lists its limits before any result. |
| [filing-check](https://github.com/JakPot42/filing-check) | Compares NHTSA vehicle-incident filings with independent public records and reports where two documents about the same event differ. It never states or implies a verdict about a company. | **Working tool, run on public data.** Every link it makes between two records is low confidence, and the README says why. |

Each repository states its licence.

## Reports to other projects

Places where I found a correct answer graded as wrong, or a rule encoded differently from the law, and one place where I was the one who was wrong.

- [prime-envs #825](https://github.com/PrimeIntellect-ai/prime-envs/issues/825) and [#826](https://github.com/PrimeIntellect-ai/prime-envs/issues/826). In the livecodebench environment, a correct solution is recorded as failing when a test input is larger than the command-line limit, and verdicts change with the number of cores on the grading machine. Both are open.
- [human-eval PR #23, comment](https://github.com/openai/human-eval/pull/23#issuecomment-5781755077). The tests for HumanEval problem 116 pass in negative numbers, which its own specification excludes.
- [PolicyEngine #9374](https://github.com/PolicyEngine/policyengine-us/issues/9374). I reported two places where the rules engine differed from the law. Half of that report was my mistake: my probe had hardcoded one state. I retracted that half on the issue. The other half stands, and a fix is open as a draft pull request, [#9610](https://github.com/PolicyEngine/policyengine-us/pull/9610).

## Earlier work

Between June and August 2026 I built more than eighty smaller tools, mostly defense and national-security demonstrations. The rule above came out of them. [Glassbox](https://github.com/JakPot42/glassbox) is the library and specification I distilled from that work. Most of those repositories have no licence. The index is in [EARLIER_WORK.md](EARLIER_WORK.md).
