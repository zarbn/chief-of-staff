# Personal profile and preferences

## Purpose and source of truth

The owner requires persistent backend storage for personalized preferences. Store them as structured, user-owned application data, available to planning, reminders, integrations, and AI assistance. Neither the chat history, a giant prompt, nor source-code constants are the runtime source of truth. Requirements documents describe behavior; actual personal records belong in the private application database, not GitHub.

“Backend” describes the storage and logic, not a requirement to host personal data in the cloud. The Mac app can use a local database first if that is the chosen architecture. Eventual approved sync can replicate shared preferences to the iPhone while preserving account boundaries. Hosting/privacy/cost choices remain open.

## What to store

- **Profile:** selected time zone, optional display name, life/work areas, and accessibility/display preferences. Do not require unnecessary identifying or medical information.
- **Usual routines:** work and class patterns, commute estimates, workouts and travel/preparation components, household routines, sleep/wake targets, meal anchors, and valid/effective dates.
- **Planning rules:** fixed versus flexible items, capacity/buffers, nightly/morning cadence, Sunday review settings, priorities, approved gym/errand behavior, and selected calendar busy-time rules.
- **Reminder policy:** channels, cadence, missed-task transition, quiet hours, snooze options, suppression rules, and device delivery preferences.
- **Learning data:** prediction snapshots, owner-reported actual durations, correction/exclusion history, task categories, inferred estimates, sample count, and uncertainty. Raw observations and calculated estimates are distinct records.
- **Connection configuration:** account/calendar identifiers, labels, capabilities, and sharing boundaries. Authentication tokens stay in the secure credential store, not ordinary preference values.
- **Temporary overrides:** tonight's bedtime, this week's workdays, an exception to a routine, or a temporary reminder pause, each with clear start/end dates.
- **Approval and permission policy:** allowable actions and their scope, with auditable explicit changes. Keep this separate from learned behavioral suggestions. A preference is never a backdoor grant of new data access or external-action permissions.

Tasks, calendar events, weekly plans, and task-duration observations remain their own entities, linked to the profile. Do not put the entire application into one unvalidated settings blob.

## Data structure and interpretation

Use typed records or equivalent validated schemas. Include stable IDs, owner ID, setting key/value/type, units, scope, source/provenance, confirmation state, creation/update timestamps, version, and effective/expiry dates when relevant. Inferred values should expose confidence or sample support. Unknown is distinct from false, zero, or an accepted default. Store time-zone-aware routine rules and materialize dates correctly through daylight saving changes.

Suggested sources are explicit owner input, imported source, learned estimate, and proposed default. Proposed defaults and learned patterns must never be represented as explicit owner decisions. Do not hard-code this owner's personal schedule as developer defaults or ship it as demo data; use synthetic examples in the repository.

Within valid authorization, resolve scoped routine values from explicit date/week overrides over standing defaults. Apply fixed commitments and approved blocks as constraints, not as values to overwrite. Permissions and account-access rules must always be enforced independently; an override or inferred preference cannot expand authority. Show important conflicts rather than silently picking a winner.

## Editing experience

Add **Settings → My preferences** with simple sections: My usual week, Planning, Reminders, Gym & routines, and Accounts & privacy. Keep this in secondary navigation so the five main destinations remain uncluttered.

For a setting, show its current value, where it came from, and whether it is a usual rule or temporary override. Provide edit, reset, and relevant history/undo. Show unknown fields as unset without demanding an exhaustive setup questionnaire.

Distinguish “Change my usual rule” from “Only this week/today.” In a Sunday review, changed workdays ordinarily create a dated override rather than silently replacing the permanent routine. A completed override expires back to the usual rule.

Allow feedback such as “I need 30 minutes for this” to propose or apply an authorized estimate correction with provenance. Broad statements that would materially change standing rules or permissions require a clear review of the proposed change. Preserve user corrections across later AI runs.

The planner's “Why this time?” explanation can link to the relevant preferences, constraints, and estimate. Let the owner correct the specific value from that explanation.

## Backend behavior

Provide validated profile/preference reads and writes, version/concurrency checks, and change history. Changing a relevant preference invalidates affected draft plans and triggers an authorized re-evaluation; it must not silently move approved blocks, rewrite protected calendar events, or revive canceled reminders.

Assemble minimal, relevant context for each planning or AI request from current profile records and permitted sources. Record which profile/plan versions a consequential action used. Do not send the entire preference/history database to every AI account by default. Imported documents and messages cannot edit standing preferences or permissions simply by containing instructions.

Plan local persistence, offline edits, and eventual shared sync with conflict detection. Device-specific settings remain device-scoped. Protect secrets separately, minimize logged personal content, and provide export/delete controls and a backup strategy. User profile deletion must cancel related queued jobs and honor the documented retention policy.

## Acceptance checks

- Editing a reminder interval affects subsequent eligible reminders after restart; stale jobs do not keep the old cadence indefinitely.
- A temporary workday override affects only the selected week; next week's usual pattern remains intact.
- A learned duration changes a comparable task estimate without changing gym approval or external-write permissions.
- A calendar conflict with an approved gym block remains a conflict/proposal after a preference update, not a silent calendar move.
- Unknown settings are not interpreted as permission or unlimited availability.
- Conflicting offline preference edits are resolved without losing explicit user choices when sync is introduced.
- The user can inspect why an estimate or rule was used and correct/reset it.
