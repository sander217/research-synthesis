**An always-visible sync indicator deserves a small, comparative prototype, but the supplied evidence does not establish that permanence is necessary or that an indicator will recover edits.** The May 4 case supports investigating a consequential reported failure. The May 21 update adds a second guide’s report, a narrowly tested engineering patch, and mixed prototype comprehension.

This assessment uses only R1–R7. These seven records contain **two independent guide incidents**, one internal QA scenario, and prototype observations from two other participants. They do not establish prevalence, a shared cause, or solution effectiveness.

**May 4, 2026: reconstructed decision baseline**

No completed decision record is supplied. The following reconstructs the evidence available by that date and provides a recommendation; it does not claim the team actually made that recommendation.

| Evidence available at the cutoff | What it establishes | Boundary |
|---|---|---|
| R1, interview May 2 about April 30, version 1.8 | P1 reported changing tomorrow’s meeting point on a train, later seeing the old point at the hotel, and messaging the group separately to avoid sending them to the wrong place. | Self-report; no device inspection or connectivity logs. Being on a train does not establish that the edit occurred offline. |
| R2, support Slack, May 3 | Support relayed R1 and opened TP-41 for that report. | The message and ticket are additional records of P1’s incident, not independent corroborating incidents. |
| R3, TP-41 status history, exported May 21 | Retrospectively documents Open on May 3 and In Progress on May 4. | Exact timing relative to the decision is unknown. The May 6 engineering note, Done status, and fix result cannot enter the May 4 rationale. |
| R7, PM Slack, May 4 | The PM proposed a permanent indicator, raised a recovery list, and identified a constraint of one designer for two days before planning. | This is stakeholder belief and planning context, not user evidence or proof of an adopted decision. |

R2 documents support’s awareness of R1. The records do not show precisely which evidence each decision-maker reviewed.

**Finding F1 — P1 needed confidence that the intended meeting point would reach the group.**

- **Fact:** P1 reported seeing the old meeting point after making an edit and substituted a separate message because of the risk of misdirecting the group. [R1, interview excerpt]
- **Interpretation:** The experience created uncertainty about which information others would receive and required work outside TrailPlan.
- **Hypotheses:** The edit might not have persisted, might have remained pending, might have been overwritten, or might have been hidden by a stale display. R1 does not distinguish these possibilities.
- **Confidence:** The reported problem and workaround are supported for P1. Technical cause is unknown. Indicator and recovery-list effectiveness are untested.

**Proposed May 4 decision D1:** Use the two designer days for a focused comparison of persistent status and contextual status, while keeping investigation connected to TP-41 rather than opening a duplicate defect effort. The justification is P1’s consequential uncertainty and workaround, balanced against the limited evidence and short design window. [R1; R2; R3, historical status; R7]

A feasible proposed scope is to draft the save–disconnect–reconnect experience on day one and use day two for short task-based checks if participants are available. Include a lightweight recovery action only as a concept whose feasibility remains to be checked.

| Candidate | Potential benefit—hypothesis | Important limitation |
|---|---|---|
| Always-visible status | Helps a guide distinguish a local save from information available to teammates. | No evidence yet that guides need continuous visibility. Status alone cannot restore missing content. |
| Contextual pending/error status | Draws attention when the guide needs to act. | May be missed; comparative usefulness is unknown. |
| Recovery list | Could let guides inspect and restore a retained edit. | Requires recoverable content and an understandable way to resolve competing versions. Neither is established. |
| Reliability repair without added UI | Could prevent the underlying failure. | TP-41 was in progress; neither its diagnosis nor outcome was established at the cutoff. |

**May 21, 2026: separate update**

| Added evidence | What changes | What remains unproven |
|---|---|---|
| R3, engineer note and Done status, May 6 | The engineer reports patching one queue-replay ordering bug, with fix version 1.9. | The engineer explicitly says P1 was not contacted and their device was not confirmed affected. Deployment and user outcomes are not documented. |
| R5, QA-9, May 6 | One internal tester on one Android device running 1.9 retained an updated meeting point after airplane-mode editing, reconnection, and reopening. | This supports that particular tested path. It does not cover other devices, conflict scenarios, or P1’s experience. R3’s reference to QA-9 is the same result, not a second test. |
| R4, interview May 9 about “yesterday,” therefore May 8 | A different guide, P2, reported a departure time reverting and checked with an assistant by phone. This adds a second independent incident and another external verification workaround. | Version and connectivity are unknown. Its occurrence after the patch date does not establish recurrence on 1.9, a regression, or patch failure. |
| R6, prototype sessions May 20 | P3 understood “Saved on this device” versus “Synced to your team” without prompting; P4 needed explanation. | Neither used the released app. Visibility persistence was not specified, and no task-success or retention comparison was conducted. |

**F1 remains current as a reported human problem.** It now covers two guides checking or communicating outside the app after seeing an earlier value. This strengthens the case for investigating uncertainty around saved and shared information, without establishing how common it is. Applicability to the currently deployed product needs rechecking because P2’s version and the 1.9 rollout are unknown. [R1; R4; R3]

**D1 remains a testing recommendation.** R6 offers limited support that the local-versus-shared distinction can be understood, while P4’s need for explanation challenges any assumption that the wording is self-explanatory. It provides no evidence that an always-visible indicator improves recovery. [R6]

Confidence is now: **problem supported for two interviewees; cause unresolved; intervention effectiveness unestablished.**

**What else could explain the experience**

These are competing hypotheses, not findings:

| Explanation | Discriminating evidence |
|---|---|
| Queue replay applied changes in the wrong order | Affected version, edit sequence, queue logs, and reproduction matching the incident. The reported patch makes this plausible but does not connect it to either guide. [R3] |
| The edit never persisted locally or remained pending | Local-save acknowledgement, retained local content, and upload/retry records. |
| Another change overwrote the edit | Revision history, actor identity, ordering, and conflict-resolution behavior. P2’s assistant is not evidence that she edited anything. [R4] |
| The display showed stale data while another copy retained the edit | Comparison of local, server, reopened, and teammate-visible values. |
| P2 used an older client or had not received the fix | P2’s build and the deployment timeline. This is relevant only to the later assessment. |

**Next step:** Verify the affected builds and deployment, then investigate local persistence, replay, conflicts, and display state within the existing defect work. Separately, compare persistent and contextual status in realistic disconnected, reconnecting, and conflicting-edit tasks. [R1; R3–R5]

The **proposed design criterion** is that guides can explain where their edit exists, identify whether teammates can access it, and take the appropriate recovery action without moderator explanation or overwriting a newer valid change. Treat messaging or phoning outside TrailPlan as a workaround when assessing in-app success. R1 and R4 motivate that criterion; it has not yet been measured.

Advance the permanent indicator only if comparison shows a useful advantage in those tasks. Advance a recovery list only after confirming that recoverable edits exist and guides can resolve them correctly. The patch, comprehensible labels, and successful recovery each require separate evidence.
