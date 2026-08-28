# research-synthesis

An AI skill that turns raw qualitative input into a same-day, decision-ready synthesis. Drop in a customer call transcript, a batch of support tickets, or a feedback thread; get back one page: patterns, verbatim evidence, recommended actions.

Built so that anyone on a team, not just researchers or designers, can run customer input through the same standard and get the same quality of output.

## Why

Most teams turn a customer call into a deck three weeks later, or into nothing. By then the decision it should have informed has already been made. This skill compresses that loop to the same afternoon: raw input in, actionable synthesis out, every claim backed by a verbatim quote anyone can check.

## What it enforces

- Every pattern is backed by exact quotes with source markers. No quote, no claim.
- Facts, interpretations, and hypotheses are labeled separately and never mixed.
- Honest counting: N is always stated, single-source findings are flagged, one loud user is one source no matter how many messages they send.
- Feature requests are logged, but the underlying problem is what gets synthesized.
- Output ends with decisions sorted into Do now / Test first / Watch, each with a success signal.
- One page, always.

## Use

Works with any agent runtime that supports skills (Claude Code, Claude.ai, Codex, or as a plain system prompt).

1. Copy `SKILL.md` into your skills directory (for Claude Code: `.claude/skills/research-synthesis/SKILL.md`).
2. Give the agent your raw input: transcript files, pasted tickets, exported chat threads. Messy auto-transcription (Notta, Otter, Zoom) is fine; the skill handles ASR garble without fabricating quotes.
3. Ask for a synthesis, or just paste the input. The skill triggers on raw qualitative data.

## Input types tested

- Auto-transcribed customer and interview calls (including bilingual Chinese/English)
- Support tickets and bug reports
- Telegram / Slack feedback threads
- App store reviews and survey open-ends

## Output

A single markdown page: TL;DR, ranked patterns with evidence, actions, open questions, and a full quote bank so anyone can audit the work.
