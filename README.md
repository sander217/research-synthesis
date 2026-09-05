# research-synthesis-sander

A skill for design research: understand people's goals and circumstances, synthesize mixed evidence, investigate relevant research and precedents, and make the next design decision explicit.

Give it design background, interviews, Slack conversations, Linear or Jira exports, reviews, product metrics, papers, or an existing proposal. It separates what the material actually establishes from interpretation and open hypotheses. Time and product version are part of the assessment, so an old report is neither silently discarded nor assumed to describe today's experience.

This repository contains instructions and examples, not an application or a research database. An agent follows the workflow using the files and tools available in its runtime. Output quality still depends on source quality, tool access, and the model; consequential decisions need review.

## Choose the research task

| Mode | Use it when | Useful output |
|---|---|---|
| **Synthesize** | You have raw material and need to understand what it means | People's goals, observed friction and workarounds, traceable patterns, contradictions, and next questions |
| **Explore** | The problem or solution is still unclear | A problem framing, related research and precedents, several design directions, and what to learn next |
| **Evaluate** | You have a proposed solution | Its assumptions, supporting and challenging evidence, alternatives, conditions for use, and a small validation plan |
| **Refresh** | New evidence, a release, or a changed context may affect an earlier finding | What still applies, what changed, what needs rechecking, and an update that preserves the earlier decision and its evidence |

You do not need to select a mode formally. Describe the decision; the agent can select or combine modes and state its working scope.

## What the workflow protects

- **People before features.** Look for the task, context, expectation, observed outcome, workaround, and cost. A request for bulk export can contain evidence of a difficult client-delivery workflow; the feature name does not erase that evidence.
- **Traceability before confidence.** Claims link to identifiable source passages, observed behavior, metric definitions, or research results. Quotes remain exact; paraphrases and uncertain transcript readings are labeled.
- **Separate levels of certainty.** A reported problem can be credible while its cause and the effectiveness of a proposed solution remain unknown. The report distinguishes these judgments.
- **Independent evidence.** One complaint copied into Slack, Jira, and a report is one original event. Internal QA, team beliefs, and customer experience are identified separately. Corpus counts do not become population rates.
- **Time and applicability.** Event or collection dates, publication dates, review dates, versions, and decision dates serve different purposes. Unknown dates remain unknown. A ticket marked Done is not proof that the person's problem is resolved.
- **Research that can change the answer.** External searches investigate supporting evidence, challenges, and alternatives. A competitor feature is a precedent, not proof of effectiveness; a paper's result needs a relevance check before it informs this product.
- **Useful uncertainty.** Missing evidence can lead to a research question, design principle, or prototype direction. A product change is not mandatory just to complete a report. Suggested targets are labeled as proposals, never presented as measured results.

## Install and use

Keep `SKILL.md` and the complete `references/` directory together in a folder named `research-synthesis-sander`. Use your agent runtime's supported skill installation mechanism; the relative paths inside the skill must remain intact. For a runtime that uses a project skill directory, the installed folder should contain:

```text
research-synthesis-sander/
  SKILL.md
  references/
    evidence-and-time.md
    external-research.md
    output-formats.md
```

Copying only `SKILL.md` is insufficient. If your runtime has no skill loader, provide the main instruction file and the relevant reference files as context; loading and tool behavior depend on that runtime.

Start by pasting material or attaching exported files. Preserve source IDs, timestamps, thread relationships, speaker roles, and product versions where available. A short context note is enough:

```text
專案與目標使用者：
目前要做的設計決定：
使用情境與限制：
現有解法（沒有也可以）：
要判斷現在的情況，或回顧哪個時間點：
資料與來源：
```

Leave unknown fields blank. The agent should make progress, identify assumptions, and ask only questions that materially affect the decision. Share only material you are authorized to provide; public searches should use general research concepts rather than confidential quotes or identifiers.

The prompts below are illustrative starting points. Replace the design context and bracketed input with your own material.

### Synthesize: understand raw feedback

```text
用 research-synthesis-sander 整理以下設計背景、Slack 對話和訪談稿。
先從使用者想完成什麼、期待與實際體驗的落差、替代做法和代價出發。
請分開事實、解讀和假說，保留來源，辨識重複轉述與矛盾。
我們下週要決定優先改善哪段流程；不要把票據數量當成受影響用戶比例。

[貼上背景與原始資料]
```

### Explore: find directions before choosing a solution

```text
我聽到創作者社區的點擊很少，但還沒有曝光分母或可靠的點擊率。
訪談中有人說封面與進去後看到的內容有落差。我目前沒有確定解法。
請先歸納人的使用情境與問題，再上網找相關研究、數據或前例。
說明每個來源能支持什麼、不能支持什麼，提出值得探索的設計方向。
資料不足的部分列成研究問題，不要自行補數字。

[貼上背景與訪談原文]
```

### Evaluate: test a proposed direction

```text
我考慮在社區卡片加入實際遊戲預覽，降低封面與內容的認知落差。
請拆解這個解法成立需要哪些假設，整合以下資料並搜尋外部證據。
同時找支持、挑戰與替代方案，區分「問題存在」「原因」「解法有效」的信心。
最後建議最小的驗證方式；任何目標值都要標成建議，不能寫成預期成效。

[貼上背景、資料與方案]
```

### Refresh: account for time and releases

```text
這是上一版研究結論、新訪談和本週的 Jira 更新。
請檢查舊洞察在目前版本是否仍適用，區分實際事件時間與建票時間。
標出仍適用、被新證據挑戰、需要複驗或已被取代的結論。
保留原本判斷與當時掌握的證據，再記錄這次為何改變。
Done 票據只有工作狀態；沒有驗證資料時，不要寫成問題已解決。

[貼上舊報告、新資料與版本資訊]
```

## Tool access and limits

- **Manual input works.** Paste conversations, attach transcripts and papers, or provide exported tickets and reviews. This repository does not install Slack, Linear, Jira, or other connectors and does not collect their content automatically.
- **Web research needs tools.** The runtime must supply search and page or document retrieval. The skill defines how to search, assess, and cite; it does not provide a search engine, paid-paper access, or guaranteed browsing capability.
- **Access gaps stay visible.** If a page cannot be read or search is unavailable, the agent should state what it could assess, continue with supplied evidence, and provide a concrete search plan. A search-result snippet is not a fully reviewed study.
- **Refresh is explicit.** Provide the previous report or decision record together with new material. This repository supplies no persistent memory service, scheduled monitoring, or automatic updates.
- **Research does not authorize execution.** Recommendations do not themselves send messages, change tickets, deploy a feature, or enroll participants. Those actions need the user's task authorization and suitable tools.

## Output and repository files

Reports should be proportional to the material. A single interview excerpt may need only a short finding, evidence, limitation, and next step. A larger decision can use an evidence table, source register, alternatives, and validation plan. There is no requirement to fill a long template when the material does not justify it.

- `SKILL.md` — entry point, mode selection, workflow, and core rules.
- `references/evidence-and-time.md` — source provenance, counts, confidence, and temporal applicability.
- `references/external-research.md` — search, source assessment, relevance, and stopping conditions.
- `references/output-formats.md` — compact reporting formats for the four modes and decision updates.
- `sample-input.md` and `sample-output.md` — a synthetic worked example. They are invented demonstration material, not actual customer research or measured product results.
- [evals/rubric.md](evals/rubric.md) and `evals/cases/` — three synthetic evaluation tasks and a separate behavioral rubric covering time/provenance, a preferred solution with no web research, and live external research.

For validation, judge whether an output preserves uncertainty, traces its claims, distinguishes evidence from assumptions, and changes the next decision usefully. A well-formatted report alone is not evidence that the research is correct.

The [initial evaluation record](evals/runs/2026-09-05/README.md) includes three independent case executions, their complete responses, and the limits of this first check. It is not a cross-model reliability claim.
