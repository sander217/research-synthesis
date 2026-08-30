---
name: research-synthesis-sander
description: Turn raw qualitative input into a same-day, decision-ready synthesis. Use this skill whenever the user provides customer calls, interview transcripts (including messy auto-transcribed ones), support tickets, issue-tracker exports (Linear, Jira, GitHub, filtered or raw), Telegram/Slack feedback threads, app store reviews, UAT bug reports, survey open-ends, or session notes and wants to know what they mean or what to do about them. Trigger on phrases like "synthesize this", "what are users saying", "find the patterns", "summarize this call", "整理這些回饋", "這通電話的重點", "這兩週我們到底在面對什麼問題", or any time raw user/customer input is pasted or uploaded, even if the user only says "look at this". Do NOT use for quantitative-only data (metrics dashboards, funnels) with no verbatim text.
---

# Research Synthesis

Turn raw qualitative input into a synthesis a team can act on the same afternoon. The output is always: patterns, verbatim evidence, recommended actions. Never a book report.

## What this is, in plain words

Someone hands you a pile of complaints. The job is to notice that twenty complaints are really four problems, prove it with what people actually said, and tell the team which one to fix first.

Everything below comes from three rules. No quote, no claim: if nobody said it, you cannot write it. Keep "what they said" and "what I think it means" in separate sentences. Count carefully, because one person complaining ten times is still one person.

What matters most is how many people hit a thing, times how badly it hurts. Hurt has three levels: it stops them paying, it stops them doing the main thing, or it just annoys them.

The work runs in five moves: find out who gave you this data and what it leaves out, pull every complaint and workaround and compliment out of it, group the ones that share an underlying cause, rank them, then close with what to do now, what to test, and what to watch.

**Where this stops.** It reads words, so it cannot give you percentages of your users, cannot prove that one thing caused another, and cannot speak for anyone who never wrote in. Silence is not agreement, and ten angry messages are not a trend. When the input cannot answer the question, saying so and naming the data that would is the correct output, not a failure.

## Core principles

1. **Evidence before interpretation.** Every pattern must be backed by verbatim quotes. If you cannot quote it, you cannot claim it.

2. **Never invent or clean up quotes.** Copy them exactly, typos and broken grammar included, with a source marker (timestamp, ticket ID, or message index). A polished quote is a fabricated quote. This overrides whatever house style you are writing under: if a quote contains punctuation or formatting your style guide forbids, it survives inside the quotation marks. Style rules govern your prose, not other people's words. Markup is the one thing you may drop: bold markers and link syntax from a Slack or tracker export are the container, not the speech. Say once that you stripped them, and leave wording, spelling, and punctuation untouched. Where a language uses quotation marks for emphasis as well as speech (Chinese 「」 among them), keep them for quoted text carrying a source marker and emphasise by wording instead, since a paraphrase in quotation marks is indistinguishable from something a person actually said.

3. **Separate three layers and label them.** FACT (what was said or observed), INTERPRETATION (what it likely means), HYPOTHESIS (what we suspect but cannot confirm from this data). Never mix layers in one sentence. Sources often arrive with someone else's interpretation already inside them: an engineer's root-cause note in a bug report, a support agent's theory, a PM's diagnosis. Attribute it rather than absorbing it. Their conclusion is a fact about what they believe, and it may still be wrong.

4. **Count honestly, and say what you counted.** N counts independent observations in whatever unit the source arrives in: messages, tickets, calls, reviews. Keep the same unit on both sides of the fraction. "7 of 15 tickets" is a count; "2 messages of 6 users" is two different units glued together and tells the reader nothing. State the number of distinct people separately, because frequency and reach answer different questions. Count the person whose experience it is, not whoever typed it up: a PM transcribing five colleagues into tickets, or a salesperson relaying customers, is a relay and not five reporters. When author and originator differ, count the originator and name the relay, because a corpus that runs through one pair of hands inherits that person's attention. Patterns overlap, so the Ns will not sum to the total; say that once instead of forcing them to add up. Add a low-sample caution when N < 5. Before publishing any count, reconcile it: every item in the input should land in counted, excluded, or explicitly ungrouped, and those should account for the whole. Do the check mechanically rather than by eye, because an unverified count reads exactly as confident as a verified one, and that is what makes it dangerous.

5. **Name the population behind the data.** Before anyone reads a pattern they need to know whose voice this is. A support channel holds only users with problems. An internal QA sweep holds only paths the tester chose to walk. A review page holds the delighted and the furious and nobody in between. Say who produced the input and what that skews, in a line near the top. This matters most when the data was produced by the same team that will read it, because a team's own testing reads like customer signal and is not.

6. **End with decisions, not observations.** Every synthesis closes with actions sorted into: Do now / Test first / Watch. An action names what to change, why (link to pattern), and what evidence would prove it worked. Write the change as the thing someone would see, not as the architecture word for it. "Converge generation status into a single source of truth" describes the shape of a fix; "the five screens that each work out whether a job is finished should read one field from the backend instead" is the fix. If a reader would have to ask what a phrase means, it is not an action yet. When the thing failing is unreliable by nature, a model, a third party, a network, a manual step, split the action in two: lowering the failure rate, and making failure visible and recoverable. They are different work, they usually have different owners, and the second is cheaper and far more certain than the first. A synthesis that only asks for a lower failure rate leaves people stranded on the failures that remain.

7. **Earn the space.** Everything above the Quote bank should read in one pass: for a handful of sources that is one page, and for a hundred it is still only as long as the patterns justify. The Quote bank is an appendix that grows with the input and does not count against length. When you are over, cut interpretations and merge overlapping patterns. Never cut evidence. Cut the wind-up too: "it is worth noting that", "the real problem is not X but Y", "this line rewrites A into B" are throat-clearing that delays the point by a sentence each time. Start at the point.

## Workflow

### Step 1: Read the source before you read the content

Spend the first pass on what kind of corpus this is. It decides what one observation is, what you get for free, and what the data structurally cannot tell you.

- **Shape.** Chat thread, transcript, tracker export, review dump. This sets the counting unit for principle 4 and the source-marker format.
- **Who produced it.** Customers, internal QA, one loud channel, a sales team relaying secondhand? Write this down; it becomes the Sources line.
- **What the team is measured on.** Ask, or infer from the data, the one or two numbers this team is judged by right now, and rank against those. It beats a generic severity ladder, because "blocks the core loop" is true of half of everything and settles nothing. Pick numbers close enough to the work that some of it genuinely fails to move them: if every item maps to the metric, the metric is too high up to sort anything, and a company-level number like revenue always does this.
- **What that number actually counts.** A named metric is rarely a defined one, and three things decide what it means. Settle them from the data, ask, or state the reading you used so the reader can overrule it.
  - *The unit.* Is one delivery with five parts, three of them right, a success or a failure? Counting parts and counting deliveries produce different orders of work.
  - *Silent substitution.* When the system quietly supplies something else and reports success, does that count as success? Note that this is two failures, not one: the substitution, and the not saying. A team can decide to allow the first while never allowing the second.
  - *Where you measure.* At production, or at the point the person actually receives it? Work that completes correctly but never reaches anyone is invisible to any metric read at the production end, which is how a team ends up believing it is doing better than it is.

  When these are undefined, take the strict reading (partial is failure, silent substitution is failure, measure at receipt) and say that you did. A synthesis that flatters the team through its choice of definition is worse than none, and the strict reading is the one that surfaces work rather than hiding it.
- **What the corpus cannot contain.** A bug tracker holds almost no praise. A cancellation survey holds no happy customers. When a category is structurally absent, say so, because otherwise its absence reads as a finding. "No positive signal" and "this corpus cannot carry positive signal" are very different sentences.
- **Triage, when the input is unfiltered.** A raw export mixes real signal with scheduling stubs, spec documents, and refactor tasks. Deciding what carries qualitative signal is the highest-leverage judgment in the whole job, so make it auditable: publish what you excluded, with counts and reasons, and let the reader overrule you.
- **Metadata is evidence, in structured sources.** Status, priority, author, created date, time-in-state. Status changes the recommendation: a fix already staged needs the affected customer told, not the fix built again. A ticket sitting In Progress for three weeks is a signal about the team, not the product. Several closed items in one problem area, with the same complaint reappearing after them, is the clearest evidence you will get that the fixes were surface-only. Treat the tracker's own priority field as one input to severity rather than as severity itself; teams mark things Urgent for reasons that have nothing to do with user impact.
- **What the timestamps actually record.** Ask whether dates mark when something was discovered or when someone got around to writing it down. A spike in a creation histogram often means one person spent an afternoon back-filling, not that the product fell over that day. Getting this backwards turns a filing habit into a fake crisis.
- **Coverage.** If sources are truncated, sampled, or unreadable, say which patterns rest on partial text. Check whether the gaps are random: truncation that lands on the longest, most analytical items is not random, and it thins exactly the evidence you most wanted.
- **Cleaning.** Auto-transcribed calls (Notta, Otter, Zoom) arrive with ASR garble. Reconstruct meaning from context but never quote a reconstruction as verbatim; quote the garbled line as-is and put your reading in brackets: "five cats" [likely: five gates].
- **Anonymization.** Anonymize people who did not choose to be in the room: customers, end users, named third parties. Replace them with roles (Customer A, Studio 3), and always redact contact details and account identifiers. Do not anonymize the colleagues of the person who asked, because it destroys the two things that make an internal synthesis actionable: routing a question to whoever can answer it, and saying plainly that ten of these tickets came from one teammate. When you are unsure which side of that line someone falls on, keep the name and flag it.

### Step 2: Extract observations

Go through the input once and pull out every observation that is one of:

- A pain point, complaint, or friction moment
- A workaround the user built (workarounds are unmet needs wearing a costume)
- A moment of delight or unprompted praise
- A feature request (record it, but treat the underlying problem as the observation, not the request)
- A behavioral signal (repeated action, abandonment, hesitation, revisit)
- A diagnosis or decision already recorded in the source (an engineer's root cause, a call made in a meeting). Attribute it per principle 3.

For each observation: verbatim quote + source marker + which type it is.

Not every line in a structured source is an observation. Specs, checklists, and schedules are usually context. Pull them in only when they carry a claim about how the product actually behaves for someone.

### Step 3: Cluster into patterns

- Group observations that share a root cause, not a surface topic. "Checkout is slow" and "I gave up paying" belong together; "checkout is slow" and "checkout button is ugly" do not.
- Name each pattern as a problem statement, not a topic. Bad: "Onboarding". Good: "Users cannot tell whether generation is still running or has failed." A pattern made of praise is the exception: name it as the claim it is ("The playable loading screen is working") and give it a severity of "positive" so nobody reads it as a defect.
- The name has to survive the question "which one?". "Direction keeps getting overturned" fails it: the reader cannot picture anything and has to hunt through your evidence to find out what was overturned. "The preview-before-publish rule was reversed twice in two weeks" passes. Put the specific thing in the heading and let the evidence confirm it, rather than making the heading a category the reader has to unpack.
- When several surface complaints turn out to share one root cause, say that plainly and say what happens if only the surfaces get fixed. That sentence is usually the most valuable line in the document: it is the difference between confirming the team's existing list and changing what they build.
- Rank by what moves the team's numbers. Sort patterns by which stated metric they move and by how much, and say plainly when one moves neither, because that is a useful answer and it is how things get dropped. Give the size as a number whenever the data holds one, and when it does not, say that and name the count that would settle it. "Strong effect on success rate" is a hedge wearing a finding's clothes; "49 of 84 assets timed out" is a finding, and "nobody records which path an image took, so the size of this is unknown" is an honest stand-in for one. Without a stated metric, fall back to frequency x severity, where severity asks whether the thing blocks money, blocks the core loop, or just annoys. When a fix is already underway in the data, mark the pattern so the Actions section tracks it instead of proposing it again.
- A pattern with N=1 but severe (data loss, payment failure, churn statement) still makes the list, flagged as single-source.
- One source can hold two observations belonging to different patterns. Cite it in both with the relevant part scoped, for example "(ticket 214, the status half)", and never silently drop the second one to keep the arithmetic tidy. Counting stays in the source's unit, so a ticket reporting three distinct faults still counts as one; note when a pattern leans on compound sources, because the items carrying three problems at once are usually the ones worth reading in full.

### Step 4: Write the synthesis

Use this structure. The Sources and Excluded sections can be dropped when they would be empty, everything else stays. Keep the bracket under each heading to four items so it stays scannable, and move cautions to their own line rather than growing the bracket.

```markdown
# Synthesis: [source description] · [date]
Input: [what was analyzed, N of items, unit, time range]
Sources: [who produced this input and what it skews. Add a line, no more than three,
for anything the reader needs before trusting a number: what this corpus cannot
contain, the counting unit if it is not obvious, coverage gaps.]

## TL;DR
- [The one thing to act on, one line]
- [Second most important, one line]
- [Third, one line]

## Patterns
### 1. [Problem statement, naming the specific thing]
(N=x/y [unit] · [z] reporters · moves: [metric and how much, or "neither"] · severity: blocks money / blocks core loop / annoyance / moves neither)
[Caution line, only when one applies: low sample N<5 · single source · fix already in flight (ticket)]
- FACT: [what was said/observed]
- Evidence: "[verbatim quote]" (source)  ·  "[verbatim quote]" (source)
- INTERPRETATION: [what it likely means; if this is one root cause behind several symptoms, say what a surface-only fix would leave behind]
- HYPOTHESIS: [optional; what you suspect but this data cannot confirm, and what would settle it]

### 2. ...

## Actions
**Do now** (evidence is sufficient, ordered by effect on the team's metrics)
- [The change, written as what someone would see. Why: Pattern 1. Success looks like: signal Y.]
  - [When a pattern is built from several tracked items, say what happens to each: which to close, which to re-scope, which to leave alone. Whoever owns those tickets needs that, and a pattern-level recommendation does not give it to them.]

**Test first** (plausible but unproven)
- [Prototype/experiment Z to validate Hypothesis. Decision criterion: ...]

**Watch** (signal too weak to act)
- [What to instrument or count before deciding.]

## Open questions
- [What this data cannot answer, what input would answer it, and who can answer it]

## Excluded
[What was filtered out, with counts and reasons, and which calls were close. Skip when
the input arrived already filtered. This sits above the Quote bank because it is the most
contestable judgment in the document and the reader should reach it without scrolling
past an appendix.]

## Quote bank
[Every extracted quote with source markers, grouped by pattern, for anyone who wants to check the work]
```

### Step 5: Deliver

- Output language mirrors the input language. Mixed Chinese/English input: write the synthesis in the dominant language, keep quotes in their original language. The structural labels stay as they are (FACT, INTERPRETATION, HYPOTHESIS, and the section headings), because they are scaffolding rather than prose and a reader should recognize the shape of the document whatever language it is written in.
- If the input is a single small item (one ticket, one short call), skip the pattern ranking and produce a mini version: TL;DR, facts, one action.
- Offer, do not auto-run: "Want me to draft the fix / the experiment / the reply to this customer?" When the synthesis is a saved file rather than a chat reply, put that offer in your message, not at the bottom of the document.

## Edge cases

- **Contradictory evidence**: never average it away. When the split itself is the finding (two segments wanting opposite things), give it its own pattern. When it lives inside one pattern (most users blocked, one cohort fine), keep it as an inline contrast note; that contrast is often the clue to the root cause.
- **The loud minority vs the systematic reporter**: ten angry messages from one person about one experience is N=1, because it is one data point restated. Ten tickets from one QA engineer about ten distinct failures is ten observations, because it is one reporter covering ground rather than one user repeating themselves. The test is whether the observations are independent, not whether the author is. Report both the observation count and the reporter count and let the reader judge. When someone follows up on their own earlier report, let the Step 2 types settle it: "still broken, this is ridiculous" restates one pain point, while "turns out it works if I upload a plain background" is a second observation of a different type, and it is often the more valuable of the two.
- **Requests vs problems**: when a user prescribes a solution ("add a progress bar"), log the request but synthesize the problem ("no feedback during generation"). The Actions section may propose a different solution than the user asked for. The inverse applies when the author is a decision-maker rather than an end user: a PM filing a solution-shaped ticket is already past diagnosis, so do not recover a naive problem they never had. Check instead whether their decision is backed by evidence in the data, and say so when it is not. When most of the corpus already carries its own prescribed fixes, repeating them back is the book report this skill exists to avoid. Earn the Actions section by doing what a list of tickets cannot do for itself: sequence fixes that depend on each other, name the one that would invalidate another, and point out where two proposed fixes conflict.
- **Interviewer bias in transcripts**: if the interviewer led the witness ("don't you think X is bad?"), flag the affected quote as prompted.
- **Nothing there**: if the input contains no actionable signal, say so in one paragraph. A null result delivered honestly beats a padded report.
