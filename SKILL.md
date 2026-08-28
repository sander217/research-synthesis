---
name: research-synthesis
description: Turn raw qualitative input into a same-day, decision-ready synthesis. Use this skill whenever the user provides customer calls, interview transcripts (including messy auto-transcribed ones), support tickets, Telegram/Slack feedback threads, app store reviews, UAT bug reports, survey open-ends, or session notes and wants to know what they mean or what to do about them. Trigger on phrases like "synthesize this", "what are users saying", "find the patterns", "summarize this call", "整理這些回饋", "這通電話的重點", or any time raw user/customer input is pasted or uploaded, even if the user only says "look at this". Do NOT use for quantitative-only data (metrics dashboards, funnels) with no verbatim text.
---

# Research Synthesis

Turn raw qualitative input into a one-page synthesis a team can act on the same afternoon. The output is always: patterns, verbatim evidence, recommended actions. Never a book report.

## Core principles

1. **Evidence before interpretation.** Every pattern must be backed by verbatim quotes. If you cannot quote it, you cannot claim it.
2. **Never invent or clean up quotes.** Copy them exactly, typos and broken grammar included, with a source marker (timestamp, ticket ID, or message index). A polished quote is a fabricated quote.
3. **Separate three layers and label them.** FACT (what was said or observed), INTERPRETATION (what it likely means), HYPOTHESIS (what we suspect but cannot confirm from this data). Never mix layers in one sentence.
4. **Count honestly.** "3 of 5 tickets" is a signal. "1 of 1 call" is an anecdote. Always state N, and add a low-sample caution when N < 5.
5. **End with decisions, not observations.** Every synthesis closes with actions sorted into: Do now / Test first / Watch. An action names what to change, why (link to pattern), and what evidence would prove it worked.
6. **One page.** If the synthesis exceeds one page, cut interpretations, never evidence.

## Workflow

### Step 1: Ingest and clean

- Accept any text input: files, pasted text, multiple sources at once.
- For auto-transcribed calls (Notta, Otter, Zoom): expect ASR garble. Reconstruct meaning from context but NEVER quote a reconstructed line as verbatim. If a key line is garbled, quote it as-is and add your reading in brackets: "five cats" [likely: five gates].
- Identify speakers/sources. In transcripts, map speaker labels to roles (interviewer, customer, agent) from context.
- Anonymize by default: replace personal names, company names, and contact info with roles (Customer A, Studio 3) unless the user says otherwise.

### Step 2: Extract observations

Go through the input once and pull out every observation that is one of:
- A pain point, complaint, or friction moment
- A workaround the user built (workarounds are unmet needs wearing a costume)
- A moment of delight or unprompted praise
- A feature request (record it, but treat the underlying problem as the observation, not the request)
- A behavioral signal (repeated action, abandonment, hesitation, revisit)

For each observation: verbatim quote + source marker + which of the five types it is.

### Step 3: Cluster into patterns

- Group observations that share a root cause, not a surface topic. "Checkout is slow" and "I gave up paying" belong together; "checkout is slow" and "checkout button is ugly" do not.
- Name each pattern as a problem statement, not a topic. Bad: "Onboarding". Good: "Users cannot tell whether generation is still running or has failed."
- Rank patterns by frequency x severity. Severity: does it block money, block the core loop, or just annoy?
- A pattern with N=1 but severe (data loss, payment failure, churn statement) still makes the list, flagged as single-source.

### Step 4: Write the synthesis

Use exactly this structure:

```markdown
# Synthesis: [source description] · [date]
Input: [what was analyzed, N of items, time range]

## TL;DR
- [The one thing to act on, one line]
- [Second most important, one line]
- [Third, one line]

## Patterns
### 1. [Problem statement]  (N=x/y · severity: blocks money / blocks core loop / annoyance)
- FACT: [what was said/observed]
- Evidence: "[verbatim quote]" (source)  ·  "[verbatim quote]" (source)
- INTERPRETATION: [what it likely means]

### 2. ...

## Actions
**Do now** (evidence is sufficient)
- [Change X because Pattern 1. Success looks like: metric/signal Y.]

**Test first** (plausible but unproven)
- [Prototype/experiment Z to validate Hypothesis. Decision criterion: ...]

**Watch** (signal too weak to act)
- [What to instrument or count before deciding.]

## Open questions
- [What this data cannot answer and what input would answer it]

## Quote bank
[Every extracted quote with source markers, grouped by pattern, for anyone who wants to check the work]
```

### Step 5: Deliver

- Output language mirrors the input language. Mixed Chinese/English input: write the synthesis in the dominant language, keep quotes in their original language.
- If the input is a single small item (one ticket, one short call), skip the pattern ranking and produce a mini version: TL;DR, facts, one action.
- Offer, do not auto-run: "Want me to draft the fix / the experiment / the reply to this customer?"

## Edge cases

- **Contradictory evidence**: surface it as its own pattern ("Users split on X"), never average it away.
- **The loud minority**: one angry user with ten messages is N=1, not N=10. Count sources, not messages.
- **Requests vs problems**: when a user prescribes a solution ("add a progress bar"), log the request but synthesize the problem ("no feedback during generation"). The Actions section may propose a different solution than the user asked for.
- **Interviewer bias in transcripts**: if the interviewer led the witness ("don't you think X is bad?"), flag the affected quote as prompted.
- **Nothing there**: if the input contains no actionable signal, say so in one paragraph. A null result delivered honestly beats a padded report.
