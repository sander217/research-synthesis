# research-synthesis-sander

Customer feedback piles up faster than anyone can read it. This reads it for you. It tells you those twenty complaints are really four problems, and it shows you who said what and where, so you can check its work. Quotes stay exactly as written, typos and all. What I like most is that it doesn't bluff: one person complaining ten times counts once, your own QA team never gets mistaken for customers, and when the data can't answer the question it just says so. Then it tells you what to fix now, what to test, and what to just keep an eye on. I fed it 104 raw Linear tickets. It threw out 41 that had nothing in them, told me which ones it threw out, and found something I'd missed: four tickets we'd marked Done had quietly come back somewhere else five days later.

The point is that anyone on the team can run it, not just the people who do research for a living, and get the same quality back.

## The rules it works by

Three rules carry everything else. No quote, no claim: if nobody said it, it does not go in. Keep "what they said" and "what I think it means" in separate sentences. Count carefully, because one person complaining ten times is still one person.

Ranking is how many people hit a thing, times how badly it hurts. Hurt has three levels: it stops them paying, it stops them doing the main thing, or it just annoys them.

**Where it stops.** It reads words, so it cannot give you percentages of your users, cannot prove one thing caused another, and cannot speak for anyone who never wrote in. Silence is not agreement, and ten angry messages are not a trend. When the input cannot answer the question, saying so and naming the data that would is the correct output.

## Why

Most teams turn a customer call into a deck three weeks later, or into nothing. By then the decision it should have informed has already been made. This skill compresses that loop to the same afternoon: raw input in, actionable synthesis out, every claim backed by a verbatim quote anyone can check.

## What it enforces

- Every pattern is backed by exact quotes with source markers. No quote, no claim.
- Quotes are copied exactly, typos included. Verbatim beats house style: a quote is never rewritten to satisfy a style guide.
- Facts, interpretations, and hypotheses are labeled separately and never mixed. Interpretation that arrived inside the source (an engineer's root-cause note, a support agent's theory) is attributed, not absorbed.
- Honest counting: N counts independent observations in the source's own unit, with the same unit on both sides of the fraction, and the number of distinct people stated separately. One person venting ten times is one observation; one tester filing ten distinct failures is ten.
- The population behind the data is named up front, because internal QA output reads like customer signal and is not.
- What was excluded is published with counts and reasons, so the filtering decision can be overruled by the reader.
- Feature requests are logged, but the underlying problem is what gets synthesized.
- Output ends with decisions sorted into Do now / Test first / Watch, each with a success signal.
- Length is earned. The analysis reads in one pass; the quote bank is an appendix that grows with the input.

## Use

Works with any agent runtime that supports skills (Claude Code, Claude.ai, Codex, or as a plain system prompt).

1. Copy `SKILL.md` into your skills directory (for Claude Code: `.claude/skills/research-synthesis-sander/SKILL.md`). The name carries a suffix because Anthropic's `design` plugin ships a skill called `research-synthesis` and the two are easy to confuse in the command picker.
2. Give the agent your raw input: transcript files, pasted tickets, exported chat threads. Messy auto-transcription (Notta, Otter, Zoom) is fine; the skill handles ASR garble without fabricating quotes. Unfiltered exports are fine too; triaging them is part of the job and the skill publishes what it dropped.
3. Ask for a synthesis, or just paste the input. The skill triggers on raw qualitative data.

### Getting better output

- **Keep the source markers.** Names or handles, timestamps, ticket IDs. They become the audit trail, and a quote nobody can trace back is worth less than one they can.
- **Do not pre-filter.** Deciding what counts as signal is part of the work, and the synthesis publishes what it dropped so you can overrule it. Filtering first hides your own assumptions inside the input.
- **Say who these people are** when it is not obvious from the data: paying customers, trial users, your own QA team. It changes what the synthesis is allowed to claim.
- **Say what decision is pending**, if there is one. Ranking against a real decision beats ranking in the abstract.
- **Mixed languages are fine.** The synthesis is written in the dominant language and quotes stay in whatever language they were spoken in.

## Input types tested

- Auto-transcribed customer and interview calls (including bilingual Chinese/English)
- Support tickets and bug reports
- Unfiltered issue-tracker exports mixing bug reports, feature specs, and scheduling stubs
- Telegram / Slack feedback threads
- App store reviews and survey open-ends

## Output

A markdown page: TL;DR, ranked patterns with evidence, actions, open questions, a full quote bank so anyone can audit the work, and the exclusion list when the input arrived unfiltered.

## Files

- `SKILL.md` is the skill itself, and the only file an agent needs.
- `sample-input.md` and `sample-output.md` are a synthetic worked example, invented for demonstration. No real user data.
