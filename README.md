# Jak Potvin

I build checks that sit between an automated system and a consequential action. One rule runs through all of it:

> Nothing automated should file, deny or pay unless the facts are in the source and the rule is the one in force.

If either part fails, the action stops, and the stop says what is missing or what is present but out of date. I'm starting with US public benefits, where the rules are written down and a maintained rules engine already exists.

Everything below runs on public or synthetic data. None of it is in production use, and none of it is peer-reviewed.

I design these projects and direct their build. The code is written with Claude Code; I review the specifications, the results and the READMEs.

## Projects

- [asof-gate](https://github.com/JakPot42/asof-gate) (demonstration): stops a SNAP case or a tax return when a fact does not trace to its documents or a legal figure is not in force.
- [redtape](https://github.com/JakPot42/redtape) (published, headline result retracted): evaluation environments that score whether a model knows when it cannot answer a benefits question from the facts it was given.
- [snap-qc-analysis](https://github.com/JakPot42/snap-qc-analysis) (finished analysis): in USDA's FY 2024 SNAP quality-control file, 15 to 36 percent of payment error dollars are errors such a check could catch in principle.
- [logchain](https://github.com/JakPot42/logchain) (working tool): a log journal in Rust in which a later edit to any entry is detectable.
- [sentinel-ledger](https://github.com/JakPot42/sentinel-ledger) (first build on a simulated machine; not a safety system): signs a record of each machine command, and the actuator's gate passes only commands inside a signed record.
- [filing-check](https://github.com/JakPot42/filing-check) (working tool, on public data): reports where NHTSA vehicle-incident filings and independent public records about the same event differ, never a verdict about a company.

Each repository states its licence.

## Reports to other projects

Places where I found a correct answer graded as wrong, or a rule encoded differently from the law, and one place where I was the one who was wrong.

- [prime-envs #825](https://github.com/PrimeIntellect-ai/prime-envs/issues/825) and [#826](https://github.com/PrimeIntellect-ai/prime-envs/issues/826). In the livecodebench environment, a correct solution is recorded as failing when a test input is larger than the command-line limit, and verdicts change with the number of cores on the grading machine. Both are open.
- [human-eval PR #23, comment](https://github.com/openai/human-eval/pull/23#issuecomment-5781755077). The tests for HumanEval problem 116 pass in negative numbers, which its own specification excludes.
- [PolicyEngine #9374](https://github.com/PolicyEngine/policyengine-us/issues/9374). I reported two places where the rules engine differed from the law. Half of that report was my mistake: my probe had hardcoded one state. I retracted that half on the issue. The other half stands, and a fix is open as a draft pull request, [#9610](https://github.com/PolicyEngine/policyengine-us/pull/9610).

## Earlier work

Between June and August 2026 I built more than eighty smaller tools, mostly defense and national-security demonstrations. The rule above came out of them. [Glassbox](https://github.com/JakPot42/glassbox) is the library and specification I distilled from that work. Most of those repositories have no licence. The index is in [EARLIER_WORK.md](EARLIER_WORK.md).
