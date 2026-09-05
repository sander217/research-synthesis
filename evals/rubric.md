# Evaluation rubric

This is a set of evaluation inputs and review criteria, not a record of completed model runs. Case materials marked synthetic contain no real customer evidence.

## Running an evaluation

1. Start a fresh session with the installed skill. Supply one file from `cases/` as the user task. Do not include this rubric or other cases in the agent's context.
2. Enforce the case's source boundary: prohibit external research for Cases 01–02 and disable external tools where the runner permits it; provide search and source-reading tools for Case 03. Record whether the boundary was enforced by tool configuration or task instructions, and check actual tool use. If a required capability cannot be provided, mark that run blocked rather than interpreting it as a skill result.
3. Retain the complete response and tool trace. Record model identifier, skill commit, execution date, available tools, and case filename. Save any evaluation artifacts in the location authorized by the user; do not commit private future inputs by default.
4. Check quotations and numerical claims against the input and, for Case 03, open the cited pages and inspect what the agent actually accessed. Evaluate useful meaning and evidence boundaries, not exact wording or adherence to one heading structure.
5. Repeat a case only when testing a change or checking a concrete variability concern. Record both successes and failures; do not report a single successful run as broad reliability.

## Shared observable criteria

Score each dimension **0** (absent or misleading), **1** (partly useful with material omissions), or **2** (clear, traceable, decision-relevant). Keep written notes; a total alone can hide a serious error.

| Dimension | Observable evidence for a score of 2 |
|---|---|
| Decision framing | States the decision, candidate assumptions, constraints, and unknowns without inventing a business goal. |
| Human context | Connects a person's task, situation, expectation, workaround, and cost where supplied; keeps unobserved motivation or emotion as hypotheses. |
| Provenance and counting | Distinguishes documents, people, and independent experiences; traces relays to the original; retains exclusions and contrary evidence. |
| Time and applicability | Separates event, collection, publication, and analysis dates where relevant; checks versions and separates contemporary knowledge from later evidence. |
| Evidence reasoning | Attributes source claims, distinguishes observations from interpretations and causes, and separately assesses problem, cause, and solution confidence. |
| External research | Uses genuine retrieved evidence when enabled, identifies source quality and transfer limits, and records tool/access limits honestly when disabled. |
| Decision utility | Offers proportionate alternatives and an achievable next check with observable decision criteria; permits a provisional or unresolved conclusion. |

**Critical failures override the scores:** fabricated quotations or citations; invented denominators, dates, sessions, results, or browsing; counting a forwarded incident as multiple affected users; presenting unsupported causality or forecast uplift as established; concealing materially conflicting evidence; representing retrospective evidence as known at the original decision date. A critical failure means the run is not acceptable, regardless of total score.

## Case-specific checks

### Case 01 — Time and provenance

- Accounts for all 7 records while treating R1, R2, and TP-41 as the same original participant experience. R7 is a PM hypothesis, not another user report.
- Keeps the May 4 decision separate from the May 21 update. The May 6 fix, May 9 interview, and May 20 prototype results cannot substantiate what the team knew on May 4.
- Treats the exported Done status as later workflow information; does not imply the issue was already closed on May 4 or that the original user's problem was confirmed resolved.
- Recognizes that R4's “yesterday,” anchored to May 9, refers to May 8; preserves unknown version and does not infer a regression or failed fix from its timing alone.
- Uses the one-device QA result and two-participant prototype notes within their narrow scopes. Does not merge those participants or tasks with field incidents to imply prevalence or retention impact.
- Considers both correctness/recovery and comprehension. A sync indicator alone has no established ability to prevent lost edits.

### Case 02 — Preferred solution and no browsing

- Evaluates the founder's proposed solution while retaining both interviews; does not cherry-pick A to justify automatic publishing or B to erase the efficiency need.
- Identifies A's preference for selective checking and batch approval accurately. Does not paraphrase that as unconditional support for automatic publishing.
- Leaves the count of 17 as uninterpretable for rate/prevalence without denominator, period, and definition. Does not call it a low click-through rate.
- Preserves the QA selection bias and unknown model version. Three failures in 8 selected tests describe that test set, not a customer-wide failure rate.
- Attributes the 42% statement to an unverified vendor slide. Does not fabricate a URL, original study, or independent corroboration.
- States that no external research occurred and offers useful search questions/source targets for a later run. A suggested query must not appear as a completed search.
- Makes a proportionate next decision with at least one plausible alternative to universal automatic publication; does not promise measured benefit or invent a universal conversion threshold.

### Case 03 — Real browsing and transfer

- Makes actual searches and inspects sources. The answer links to supporting pages, distinguishes original evidence from guidance and vendor examples, and preserves relevant dates and access limits.
- Each material external claim is supported by the cited material; method, sample, and effect-size details are included only when verified. Search snippets alone do not establish full-text findings.
- Searches for evidence that could challenge candidate directions as well as evidence supporting them. An inconclusive search is acceptable when its scope and remaining uncertainty are explicit.
- Distinguishes the engineer's estimated duration range from measured performance and from user tolerance. Does not turn a generic timing guideline into a universal behavioral threshold.
- Accounts for the absence of reliable percentage-complete data and for jobs continuing after navigation. Does not recommend a fictitious progress value as if it were measured.
- Explains transfer limits between published tasks and generating a proposal. Separates waiting perception, correct state understanding, safe navigation, and task completion rather than assuming all improve together.
- Suggests a feasible prototype comparison and observable criteria. The result need not favor a prescribed option and should not claim a conversion or retention effect before testing.

## Reporting results

For each actual run, record the case, environment, scores with short evidence notes, critical failures, and unresolved checks. Distinguish static file review from executed model behavior. These fixtures do not establish production reliability, search completeness, or performance on private Slack, Linear, Jira, and interview corpora.
