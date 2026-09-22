# Product interview — living decision record

Status: requirements interview in progress. Do not treat suggested choices as confirmed preferences. Ask a few concrete questions at a time; keep later questions here rather than presenting a long questionnaire.

## Confirmed by the owner

- Installed app, not a website.
- ADHD-friendly, calm, easily navigable experience using the accepted design as a starting point.
- One system for personal life and business, not just business tasks.
- Include laundry, cooking, shopping, errands, and menial tasks.
- Run daily and proactively help schedule the day.
- Accept feedback and learn from estimated versus actual task durations.
- Preserve the original daily brief, inbox/follow-up, calendar/meetings, commitments, operations, and AI-coordination vision.
- Two Claude subscriptions, Business and Personal, each used for Chat, Code, and Cowork; one personal Codex account.
- Multiple Google/email accounts.

## Round 1 — answered and incorporated

Source: owner's direct answers in this conversation, September 22, 2026.

1. **Platforms:** Mac first, then iPhone; not Android. Owner wants eventual data synchronization. Shared data is a product requirement; provider, infrastructure, costs, and timing remain undecided.
2. **Planning:** automatically arrange flexible tasks. Preserve meetings and other events the owner puts on calendars. Assignments and miscellaneous work belong in the same planner. Substantial errands require approval of a continuous outing block; batch compatible stops rather than squeezing trips into meeting gaps. Friday morning is an example, not a fixed recurring commitment.
3. **Gym:** needs to fit changing weekly availability. Frequency, preferred time windows, full trip duration, and placement approval policy remain open.
4. **Duration feedback:** ask roughly how long after completion; let unanswered questions queue. Timers are not the primary input. Proposed implementation: one non-blocking prompt after owner-confirmed completion, with a quiet durable queue, approximate/custom answers, and skip/later controls. A scheduled end time alone is not confirmation of completion.

## Round 2 — asked, awaiting answers

- What weekly gym goal should the app plan toward, and how much time does a full trip take including travel and getting ready?
- When should it prepare the day, which hours may flexible tasks use, and what sleep/meal/downtime windows should be protected?
- If a task/reminder is missed, should it give one gentle check-in then replan, keep nudging within chosen hours, or collect it for the next review?

## Follow-up interview topics — not yet asked

- For gym: should the owner approve the week's proposed sessions together, or allow automatic placement and rearrangement within agreed rules?
- For errands: preferred days/locations, usual travel needs, outing approval details, and how to handle a newly added conflict.
- Should app-planned blocks be written to a separate external calendar or remain internal? Do not infer calendar-write approval from permission to arrange an internal plan.
- What three things most often slip through the cracks? Walk through a recent difficult day.
- Until an iPhone app exists, what reminder channel is useful away from the Mac?

## Round 3 — scope and onboarding

- Which three outcomes make the first version worth using: daily planning, household routines, email follow-ups, meeting help, or AI-work coordination?
- What task/calendar/list tools hold existing information? Import versus fresh start?
- Solo work, staff, contractors, or household sharing? Avoid adding collaboration complexity without a real use case.
- For food/shopping: simple meal reminders and grocery list, or recipes, pantry information, budgets, and meal planning? Any constraints the owner wants recorded?
- Which fields should be optional during capture and what feels like too much administration?

## Round 4 — connections and operation

- Claude Business plan and administrator access; which devices run Claude/Codex?
- First Google accounts and what data each may expose to the app and each AI account.
- Are private cloud processing and an ongoing operating cost acceptable, so planning can run while the Mac is off? What budget range?
- Which reminder channels and installation/distribution approach fit the selected devices?
- Confirm any additional low-risk automation scope. Flexible internal task placement is already approved; external messages and calendar changes remain reviewable.

## Decision log

Record each answer with date and source. Update the build prompt and priorities after each round. Retain unresolved questions. Distinguish confirmed decisions from reversible design recommendations.
