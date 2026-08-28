# Synthesis: support channel feedback · 2026-08-28
Input: 8 messages, single-day sample. N counts messages.
Sources: 6 unique users writing into a support channel, so this corpus holds people with problems and the occasional volunteered compliment. It cannot tell you what the silent majority experiences.

## TL;DR
- A possible double-charge (Customer F) is a churn threat and needs a same-day reply. Blocks money.
- Users cannot tell whether generation is running, failed, or finished; the same person hit it twice in one session. Blocks the core loop.
- Edge quality problems trace to input photos, not the model; a user discovered the fix themselves and it should be productized.

## Patterns

### 1. Billing error suspected  (N=1/8 messages · 1 reporter · severity: blocks money · single-source)
- FACT: One customer reports being charged twice and threatens to cancel.
- Evidence: "charged twice this month?? pls check, invoice attached. if this isn't fixed we're cancelling" (msg-06)
- INTERPRETATION: Regardless of whether the charge is real, response speed now determines retention.
- HYPOTHESIS: A duplicate charge usually means either a retried payment call or a subscription created twice. Nothing in this channel can tell them apart; the billing log can.

### 2. No feedback during and after generation  (N=2/8 messages · 1 reporter · severity: blocks core loop · single-source)
- FACT: One user closed the tab mid-generation because status was unclear; the same user later could not find the preview after saving.
- Evidence: "i couldnt tell if it crashed or was still working so i closed the tab" (msg-01)  ·  "where did the preview go after i hit save. i kept looking for it" (msg-07)
- INTERPRETATION: These are not two UI gaps but one: the product never shows its own state. Both moments sit at the point of highest user investment, which is why one produced abandonment and the other confusion. Adding a spinner to generation alone would leave the post-save half intact and the complaint would come back wearing different words.

### 3. Edge artifacts are an input problem users solve themselves  (N=2/8 messages · 1 reporter · severity: annoyance · single-source)
- FACT: A user hit white edges four times, then discovered plain-background photos fix it, and asked us to tell people.
- Evidence: "white edges around it? looks cheap. tried 4 times same thing" (msg-03)  ·  "if I upload a photo with plain background it works better. you should tell people that" (msg-04)
- INTERPRETATION: A workaround this clean is a free spec. Guidance at upload time (or an automatic background check) converts four failed attempts into one.

### 4. The waiting-game pattern is working  (N=1/8 messages · 1 reporter · positive · single-source)
- FACT: Unprompted praise for playing the template game during generation.
- Evidence: "the loading screen where you can play the old game while waiting is genius lol" (msg-08)
- INTERPRETATION: Keep and extend; this is the mechanism masking Pattern 2's wait, but it does not fix the missing status signal.

Logged, not synthesized: bulk export request (msg-05) is a solution prescription; the underlying problem is "agency-type customers deliver to many clients manually." Needs its own investigation before building.

## Actions

**Do now**
- Reply to Customer F today and audit the invoice. Success signal: resolution message sent within 24h, no cancellation.
- Give generation a single visible state (running / failed / done) and a persistent path back to the preview after save, per Pattern 2. Success signal: mid-generation tab-close rate drops and post-save "where did it go" messages stop.

**Test first**
- Upload-time photo guidance or an automatic background-quality check, per Pattern 3. Prototype the hint first; decision criterion: retry count per successful asset drops below 2.

**Watch**
- Count how many paying customers share the agency delivery pattern behind msg-05 before scoping bulk export.

## Open questions
- Is the double charge an isolated incident or systemic? Needs a billing log audit, not more feedback. Whoever owns payments can answer it today.
- How common is the multi-client agency workflow? One vocal customer is not a segment.
- Every pattern here is single-source in an 8-message sample. Treat all of them as leads to verify, not as trends.

## Quote bank
Pattern 1: msg-06. Pattern 2: msg-01, msg-07. Pattern 3: msg-03, msg-04. Pattern 4: msg-08. Logged request: msg-05. Positive, uncategorized: msg-02.
