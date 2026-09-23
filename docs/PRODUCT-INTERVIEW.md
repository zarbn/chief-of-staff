# Product interview — living decision record

Status: core product brief ready for a first implementation milestone; consequential setup decisions remain open. Further interviewing should focus on decisions needed for the next stage. Do not treat suggested choices as confirmed preferences. Ask a few concrete questions at a time; keep later questions here rather than presenting a long questionnaire.

## Confirmed by the owner

- Installed app, not a website.
- ADHD-friendly, calm, easily navigable experience using the accepted design as a starting point.
- One system for personal life and business, not just business tasks.
- Include laundry, cooking, shopping, errands, and menial tasks.
- Run daily and proactively help schedule the day.
- Run a guided Sunday review to decide the upcoming week’s framework, including changing office days and approving gym times.
- Accept feedback and learn from estimated versus actual task durations.
- Preserve the original daily brief, inbox/follow-up, calendar/meetings, commitments, operations, and AI-coordination vision.
- Two Claude subscriptions, Business and Personal, each used for Chat, Code, and Cowork; one personal Codex account.
- Multiple Google/email accounts; Google Calendar across multiple accounts is confirmed.
- Personalized preferences must be stored in the app backend/database, with an editable profile; actual hosting remains undecided.
- Existing to-do list is kept in Notes and can be pasted directly. Notes product is unspecified; paste-based onboarding avoids requiring a direct integration.

## Round 1 — answered and incorporated

Source: owner's direct answers in this conversation, September 22, 2026.

1. **Platforms:** Mac first, then iPhone; not Android. Owner wants eventual data synchronization. Shared data is a product requirement; provider, infrastructure, costs, and timing remain undecided.
2. **Planning:** automatically arrange flexible tasks. Preserve meetings and other events the owner puts on calendars. Assignments and miscellaneous work belong in the same planner. Substantial errands require approval of a continuous outing block; batch compatible stops rather than squeezing trips into meeting gaps. Friday morning is an example, not a fixed recurring commitment.
3. **Gym:** needs to fit changing weekly availability. The owner has since supplied a usual weekly split and initial duration/travel estimates; see the gym follow-up below and `GYM-PLAN.md`. Complete lifting-day outing lengths are recorded. Weekly gym times require owner approval; Tuesday cardio logistics remain unresolved.
4. **Duration feedback:** ask roughly how long after completion; let unanswered questions queue. Timers are not the primary input. Proposed implementation: one non-blocking prompt after owner-confirmed completion, with a quiet durable queue, approximate/custom answers, and skip/later controls. A scheduled end time alone is not confirmation of completion.

## Round 2 — partially answered

- Gym baseline answered: Sunday upper; Monday lower + cardio; Tuesday rest plus 30-minute cardio after class at night; Wednesday push; Thursday pull + cardio; Friday legs/lower + cardio. Preparation approximately 15 minutes. See `GYM-PLAN.md` for all supplied durations and conflicts.
- Partly answered: wakes at 7:30 a.m. on workdays, bedtime around midnight; wants a mechanism to set an approximate bedtime. Usual office days are now confirmed as Tuesday and Wednesday, 9 to 4 or 5; classes Monday/Tuesday/Thursday 6:30–9 p.m. Work-to-home and home-to-class are each confirmed at approximately 35 minutes one way; classes are in person. Plan the night before and adjust in the morning. Non-workday wake time, class logistics, exact planning clock times, quiet hours, meals, and wind-down remain open. Proposed control: editable Tonight’s bedtime with a standing default and one-night override.
- Owner chose nudges every 10 minutes, then replanning for missed tasks. After 20 minutes past planned start without a response, propose rescheduling. Quiet hours and class/meeting behavior remain to be configured. Duration-feedback questions keep their separate quiet queue.

## Gym follow-up — walking, duration scope, and cardio confirmed

Source: owner's follow-up answers, September 22, 2026.

- Upper and pull: 20-minute walk each way. Lower, push, and legs: 10-minute walk each way. This supersedes the initially conflicting walking-distance description.
- Session lengths are exercise time only; preparation and walking are additional.
- Add cardio only on specified days. Tuesday is explicitly 30 minutes. Owner subsequently confirmed about 25 minutes each for Monday lower, Thursday pull, and Friday legs.

The owner mentioned wanting lower and pull sessions shortened. No shorter target has been chosen. Saturday, Tuesday cardio venue/travel after the confirmed 9 p.m. class end, cleanup allowance, and cross-day flexibility are unresolved. Weekly gym times require owner approval before reservation. See `GYM-PLAN.md` for derived complete lifting-day outing totals; Tuesday logistics remain unresolved.

## Work/class/planning follow-up — incorporated

- Office generally Tuesday/Wednesday, 9 a.m. to 4 or 5 p.m.; Tuesday tries to leave around 4 to go home for dinner.
- Work-to-home commute about 35 minutes one way; home-to-class also 35 minutes one way, separately confirmed.
- In-person classes Monday/Tuesday/Thursday, 6:30–9 p.m. Tuesday sequence confirmed as work departure around 4, home for dinner, then class.
- Plan the night before; adjust in the morning. This decision is confirmed and should not be re-asked.
- Repeated nudges every 10 minutes, with replanning if a task is missed. Cadence is confirmed; after 20 minutes past planned start without a response, propose rescheduling.
- See `WEEKLY-SCHEDULE.md` for the distinction between usual patterns and guaranteed availability.

## Reminder and gym approval follow-up — answered

- At 20 minutes past planned start with no response, propose moving the task instead of continuing start nudges. Do not equate no response with confirmed failure. Keep a single pending proposal rather than repeated prompts for the same change.
- Show the week's gym times for owner approval first. Do not reserve proposed gym blocks automatically or silently move approved ones.
- These reminder and gym approval questions are resolved.

## Sunday framework review — Sunday evening confirmed

- Owner requested a specific Sunday workflow to set the week's framework, especially variable office days and gym times.
- Proposed guided flow is documented in `WEEKLY-REVIEW.md`: exceptions, priorities, gym approval, errand/life blocks, then framework approval.
- Weekly framework guides nightly planning and morning adjustment; approved blocks stay protected.
- Owner selected Sunday evening. Exact clock time is not specified. Upcoming Monday–Sunday remains the suggested dated coverage; do not treat it as an explicitly confirmed week boundary.

## Personalized preferences — confirmed requirement

The owner explicitly requested backend storage for personalized preferences. `PREFERENCES.md` defines structured private data, usual rules versus dated exceptions, provenance, learning versus explicit decisions, editing/reset, controlled replanning, and eventual sync. A local database can satisfy storage in the initial Mac app; the requirement does not decide cloud hosting. This belongs in the first implementation foundation.

## Readiness review

The main product behavior is defined. Three setup decisions deserve priority: local/private-cloud operation and budget; internal-only plans versus authorized Google Calendar write-back; and notification channels/quiet-time rules. Do not let lower-priority personal schedule questions delay independent app development once requested.

Exact personal routine times remain editable onboarding settings. Provider-specific capabilities are verified at their integration milestone. Real task intake remains private; date/status ambiguities affect scheduling those items, not app-building readiness. Retain separately confirmed tasks even when labels appear similar.

## Follow-up interview topics — not yet asked

- For errands: preferred days/locations, usual travel needs, outing approval details, and how to handle a newly added conflict.
- Should app-planned blocks be written to a separate external calendar or remain internal? Do not infer calendar-write approval from permission to arrange an internal plan.
- What three things most often slip through the cracks? Walk through a recent difficult day.
- Until an iPhone app exists, what reminder channel is useful away from the Mac?

## Round 3 — scope and onboarding

- Which three outcomes make the first version worth using: daily planning, household routines, email follow-ups, meeting help, or AI-work coordination?
- Answered: Google Calendar across multiple accounts, plus an existing Notes to-do list the owner can paste. The owner has now pasted the list and it was organized privately in conversation. No application import or account connection has happened. Keep actual task contents and clarifications out of GitHub; confirm account/calendar selection when connecting.
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
