# Initial forward evaluation — 5 September 2026

Three independent agents each executed one case from an isolated copy of the skill and relevant references. They received neither the rubric nor an expected answer. This is one observed run per case, reviewed by the implementing agent, not a repeated benchmark or independent certification. The model identifier was not exposed by the runner; it inherited the parent session's model.

The working version was based on commit `43c4188dda3733128488f59947bdf2f17d929758`. [manifest.json](manifest.json) records exact input, instruction, and response hashes. The final references add navigation links after the evaluated snapshot; their research instructions are unchanged.

## Observed results

| Case and full response | Result | Evidence in the response |
|---|---|---|
| [01 — Time and provenance](01-time-and-provenance.md) | Acceptable in this run; no critical failure identified | Seven records retained; P1's interview, Slack relay, and ticket treated as one incident. May 4 evidence separated from the May 21 update. Done and one-device QA did not establish a field resolution. Unknown version did not become a regression claim. |
| [02 — Preferred solution, supplied sources only](02-preferred-solution-no-web.md) | Acceptable in this run; no critical failure identified | Retained both sellers' different needs; recommended testing batch approval rather than assuming universal auto-publication. The count of 17 did not become a rate; selected QA cases did not become population prevalence. The vendor's 42% claim remained unverified. |
| [03 — Live external research](03-live-waiting-research.md) | Acceptable in this run; no critical failure identified | Performed web research and produced an actual query/source log. Distinguished original studies from first-party guidance, used an accessible author manuscript when publisher access failed, and stated transfer limits. Did not invent completion percentages or treat an engineering estimate as measured latency. |

Cases 01–02 prohibited web and external connectors through task instructions; tools were not technically removed. The executing agents reported no external calls. Case 03 used live search and source retrieval. Its response includes seven actual queries, inspected locations, and access limits. The reviewer reopened the three original papers and Carbon guidance and checked material sample sizes, durations, findings, and progress-indicator claims against those sources.

## Static checks

- Skill frontmatter and naming passed the skill-creator validator.
- Relative Markdown file links resolved and code fences were balanced.
- All eight quotations in the corrected worked example matched the original input exactly; the input contained six distinct speakers and was unchanged.
- `git diff --check` passed before delivery.

## Limits

These outputs support a narrow behavioral smoke test. They do not establish cross-model consistency, repeated-run reliability, performance on large or private corpora, connector operation, or complete literature coverage. Tool traces were available in the execution session; the repository retains responses and source logs, not a full raw tool transcript. The briefs are deliberately detailed for inspection and do not establish a target report length for everyday use. See the [rubric](../../rubric.md) for subsequent runs.
