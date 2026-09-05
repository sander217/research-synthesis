# Case 01 — Offline itinerary edits across a release

All product details, people, records, and results below are synthetic evaluation inputs.

## Task

We build TrailPlan, an itinerary app for independent tour guides. Reconstruct the evidence available for our May 4, 2026 decision about helping guides recover offline edits. Then give a separate update using everything available by May 21. Assess whether an always-visible sync indicator deserves prototyping and identify what else could explain the experience. Use only the supplied records; web access is unavailable for this run.

## Supplied records

**R1 — Interview excerpt.** Conducted May 2, 2026. Participant P1 is a tour guide. Event: April 30, 2026. App version: 1.8.

> On the train I changed tomorrow's meeting point. When we got to the hotel, the old meeting point was back. I messaged the group separately because I couldn't risk them going to the wrong place.

The interviewer did not capture connectivity logs or inspect the participant's device.

**R2 — Slack, support colleague, May 3, 2026.**

> From P1's interview yesterday, R1: a guide changed the meeting point on a train and saw the old one at the hotel. I've opened TP-41 for that same report.

**R3 — Linear ticket TP-41.** Created May 3, 2026; origin: R1 via R2. Exported May 21. Status history: Open May 3; In Progress May 4; Done May 6. Fix version: 1.9.

Engineer note, May 6:

> Patched one queue-replay ordering bug. QA-9 passed. We have not contacted P1 or confirmed their device was affected by this bug.

**R4 — Interview excerpt.** Conducted May 9, 2026. Participant P2 is a different tour guide. Event: “yesterday.” App version and connectivity at the time: not recorded.

> I updated a departure time, then later it showed the old time. I asked my assistant which time she could see and we checked by phone.

**R5 — QA-9, May 6, 2026.** One internal tester, one Android device, version 1.9. Scenario: change a meeting point in airplane mode, reconnect, reopen itinerary. Result: updated meeting point retained. No other devices or conflict scenarios tested.

**R6 — Internal usability notes, May 20, 2026.** Two new participants, P3 and P4, tested a clickable prototype showing “Saved on this device” and “Synced to your team.” Neither used the released app. P3 described the difference correctly without prompting. P4 needed the moderator to explain it. No task-success or retention comparison was conducted.

**R7 — Slack, PM, May 4, 2026.**

> I think a permanent sync indicator will solve this. Could a recovery list be useful too? We have one designer for two days before planning.
