# Synthesis: supplied support messages (synthetic)

**Decision frame:** Identify worthwhile investigation and design directions. This framing is inferred; the input supplies no proposed solution, business metric, or decision deadline.

**Coverage:** All 8 messages from 6 distinct synthetic speakers were reviewed; none excluded. This selected support-channel sample includes problems and praise, but cannot establish prevalence or represent all customers. Message counts below describe corpus coverage, not independent users or incidents. The two quality messages describe one person's issue and subsequent workaround; the two messages from another person concern different tasks.

**Time and product context:** Event dates, collection dates, product versions, session relationships, and current fix status are unknown. “This month” has no known calendar anchor. The workaround follows its author's initial quality complaint; no other event sequence is established. This example uses supplied material only; no web research was performed and no external evidence is assessed.

## Decision brief

- Investigate the reported duplicate charge promptly. A cancellation threat is explicit; an actual billing error is unverified.
- Clarify the generation and post-save experiences separately. One speaker reports both problems, but neither a shared cause nor a shared session is established.
- Investigate repeated asset-quality attempts and multi-client delivery work. Both contain concrete effort or workflow signals; neither establishes the effectiveness of a proposed fix.

## Findings and implications

Every problem below is reported by one speaker. Confidence in the existence of these *reports* is high; frequency in the customer population is unknown. Confidence in root causes and solution effectiveness is low or unassessed.

| Finding | Reported fact and source | Interpretation and decision implication |
|---|---|---|
| Possible duplicate charge threatens this customer's continuation | 1/8 messages, 1 speaker: reports two charges and conditional cancellation (msg-06). The referenced invoice is not supplied. | Potential financial harm makes verification time-sensitive. Check the transaction history before attributing a cause or promising a correction. |
| Unclear generation status preceded leaving the tab | 1/8 messages, 1 speaker: says they could not tell whether generation crashed and closed the tab (msg-01). | The person needed enough information to choose whether to wait or recover. Inspect actual job states and prototype truthful status feedback; duration and job outcome are unknown. |
| A saved preview was difficult to find | 1/8 messages, 1 speaker: reports searching for the preview after saving (msg-07). | Investigate retrieval and save confirmation. Missing visibility is plausible; data loss and a connection to the generation problem are unproven. |
| One person reports repeated edge artifacts and a partial workaround | 2/8 messages, 1 speaker: reports four attempts with white edges, then says a plain background works better (msg-03–04). | Input guidance is a candidate to evaluate. Improvement does not prove elimination of artifacts, establish a root cause, or rule out a model problem. |
| Delivering to multiple clients requires repetitive downloads | 1/8 messages, 1 speaker: describes individual downloads for 12 clients taking their morning and requests bulk export (msg-05). | The useful research unit is completing client delivery. Observe download, naming, checking, and sharing before deciding whether batching addresses the costly part. Twelve clients are not twelve independent participants. |
| Two positive experiences identify things worth preserving in exploration | 2/8 messages, 2 speakers: one reports making a team-offsite game in 10 minutes (msg-02); another praises playing an old game while waiting (msg-08). | Preserve awareness of quick creation and enjoyable waiting when exploring changes. These distinct reports do not prove typical creation speed, reduced abandonment, or that the waiting game works for everyone. |

The rows cover msg-01 through msg-08 exactly once (1 + 1 + 1 + 2 + 1 + 2 = 8). Speakers overlap across rows; their counts must not be added to infer reach. These are groupings by task and experience, not established common causes.

## Next research and design decisions

**Investigate now:** Have the payments owner inspect the reported charges and communicate verified findings to the affected customer, subject to the team's usual authorization. Resolution means the ledger is reconciled and any confirmed error corrected; a response alone cannot guarantee retention. No message is sent by this synthesis.

**Test candidate directions:**

- Generation: compare understandable job status and recovery options against the current experience. Observe whether people correctly identify running, completed, and failed jobs and know their next action. A tab close can also mean leaving safely; it is not automatically failure.
- Saved preview: observe saving and reopening an output. Compare a visible return path only if retrieval is the issue. Keep this evaluation separate from generation status until evidence connects them.
- Asset quality: reproduce the reported behavior with matched inputs and record model/version settings before testing an upload hint. Compare artifact quality, usable-output rate, and attempts with guidance versus the current flow. No numerical improvement target is justified by this sample.
- Client delivery: observe an end-to-end delivery task, including any naming and verification work. Compare batching with other directions discovered in that work; assess total task time and delivery errors, not just clicks.

**Missing decision inputs:** Confirm which product versions and dates these reports describe, what has already changed, the actual billing outcome, and how the tasks appear outside this selected sample. Define any metric's numerator, denominator, time window, and success event before using it to prioritize. No implementation priority among the ordinary usability issues is established here.

## Quote bank

Exact message text from the synthetic input; source IDs retain traceability without repeating handles.

- **msg-01:** “generation took forever and i couldnt tell if it crashed or was still working so i closed the tab”
- **msg-02:** “Love the pacman template!! made one for my team offsite in 10 min”
- **msg-03:** “why does my character come out with white edges around it? looks cheap. tried 4 times same thing”
- **msg-04:** “ok update, if I upload a photo with plain background it works better. you should tell people that”
- **msg-05:** “We need bulk export. Right now I download games one by one for our 12 clients, takes my morning”
- **msg-06:** “charged twice this month?? pls check, invoice attached. if this isn't fixed we're cancelling”
- **msg-07:** “also where did the preview go after i hit save. i kept looking for it”
- **msg-08:** “the loading screen where you can play the old game while waiting is genius lol I almost didn't want mine to finish”
