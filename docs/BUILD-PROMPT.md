# Chief of Staff — complete build prompt

## Mission and working context

Build a private, ADHD-friendly personal chief of staff for the owner’s life and business. It should help the owner capture commitments, choose priorities, start work, manage schedules and meetings, follow up with people, coordinate AI work, and maintain business operations. It must proactively surface what matters without creating another overwhelming inbox.

Project folder: `/Users/agentic/chief-of-staff`
GitHub repository: `https://github.com/zarbn/chief-of-staff`
Working product name: Chief of Staff. “Daylight” is the provisional name used in the accepted design, not a final branding requirement.

The owner has two distinct Claude subscriptions: Business and Personal. Both are used for Chat, Code, and Cowork. The owner also has a personal Codex account. Information is spread across multiple Google/email accounts. The exact Claude Business plan and administrator access are not confirmed. Device setup, notification channels, hosting, budget, and which Google accounts are in scope are also not confirmed.

The owner approved the supplied clickable design as the starting point and expects to adjust it as the product develops. Preserve its calm, easily navigable structure. This is a full life-and-business assistant; do not reduce it to a usage dashboard or generic to-do list.

## Delivery rules

Inspect repository instructions and existing files before changing them. Preserve user work. Make a brief plan, then implement working increments and document what is complete, partial, or blocked. Do not claim a mocked connection, simulated task, queued notification, or drafted message has actually synced, run, delivered, or sent.

Use clear language in the product and progress reports. Make routine reversible choices without repeatedly asking for permission. Ask only when a missing answer affects privacy boundaries, spending, an external action, or a consequential product decision. Continue independent work while awaiting answers. Report real blockers plainly.

The initial handoff contains planning documents and a design reference, not an implemented application. Build incrementally from that foundation. Verify current official documentation before choosing integration methods or implementing provider-specific APIs. Treat the integration notes below as requirements to investigate, not promises that every provider exposes them.

## 1. Product experience and navigation

Use five main destinations, matching the accepted design:

- Today: one suggested next action, up to three daily priorities, upcoming commitments, and the few decisions that need attention.
- My tasks: quick captures, tasks, projects, personal responsibilities, business operations, recurring checklists, and later/someday items.
- Schedule: combined calendar view, meeting preparation, transition buffers, suggested focus blocks, and scheduling conflicts.
- Follow-ups: people the owner owes a reply to and people the owner is waiting on, with clear source accounts.
- AI work: assigned work across Claude Business, Claude Personal, and Codex Personal; priorities, progress, blockers, results awaiting review, and supported usage information.

Place Connections & alerts in secondary navigation. Keep quick capture available throughout the app. Business/personal filters belong where helpful without adding permanent visual clutter. Add deeper workflow pages under these destinations rather than expanding the main menu endlessly.

Match the design’s warm, restrained visual treatment, generous spacing, readable typography, clear button labels, and limited use of color. Support responsive desktop and phone layouts, light/dark appearance, keyboard navigation, screen readers, reduced motion, visible focus, adequate contrast, and comfortable touch targets. Do not hide essential actions behind hover or unlabeled icons.

## 2. ADHD-friendly behavior

Design for low effort, low shame, and easy recovery. Personalize these defaults rather than assuming every person with ADHD needs the same experience. Do not present the product as medical treatment.

- Show one next step, not the entire backlog, on the default home screen.
- Explain a recommendation in a short factual sentence: “Due tomorrow; Jordan is waiting.”
- Provide Simplify my view to hide optional panels while keeping navigation and capture available.
- Capture a task or thought without requiring a project, category, or due date. Include quick text capture first; add voice capture/transcription later with explicit recording controls.
- Convert vague work into concrete next actions. Preserve the original intent and let the owner edit suggestions.
- Offer optional short focus sessions, pause/resume, and an easy “make this smaller” action. Timers must behave correctly across refresh and device sleep.
- Use estimates, calendar availability, transition buffers, and optional energy input to make achievable plans. Distinguish estimated time from actual time.
- Treat priority, deadline, scheduled work time, and reminder time as separate things.
- Make “Not now,” rescheduling, and restarting easy. Avoid guilt messages, punitive streaks, or a constant red overdue wall.
- Preserve the owner’s explicit priority choices. Recommend changes transparently rather than silently rearranging everything.
- Support recurring tasks and weekly reviews that help close loose ends and select the next week’s priorities.

## 3. Tasks, commitments, and decisions

The central task system is the source of truth for work priorities. Provider activity enriches it but does not determine business importance by itself.

Each task can have: title, desired outcome, concrete next action, life/business area, project, priority, owner or assigned AI account, status, due date, estimated duration, dependencies, reminder policy, source links, completion criteria, and activity history. Make most fields optional at capture time.

Support captured, ready, scheduled, in progress, waiting, needs review, completed, and canceled states. Separate an AI run finishing from the business task being accepted as complete. Let users reopen tasks and undo routine changes.

Support commitments in both directions: “I owe someone” and “someone owes me.” Record the person, promised action, date, source, last checked time, and next follow-up. Show a small decision queue containing the issue, options, recommendation, relevant evidence, and decision deadline.

## 4. Google/email accounts and source information

Support separately authorized Google accounts and label them clearly. Begin with Gmail and Calendar, then add selected Drive documents when useful. Other email providers should fit the connection architecture, but implement them only after confirming the owner’s actual providers.

For every account, expose connection status, granted capabilities, last successful sync, and reconnection needs. Use supported authorization flows and secure server-side token handling. Do not ask the owner to paste passwords or session cookies into chat.

Keep source account identity, original item IDs, timestamps, permissions, and direct links. Group duplicate emails or shared calendar events for display without losing their separate account records. Support incremental sync, retries, revocation, deletion/tombstones, and partial failures. Label stale or unavailable data explicitly. Never infer “no reply” from a failed sync.

Keep an index and useful summaries rather than copying every document indiscriminately. Retrieve relevant permitted source information on demand. A combined dashboard must not silently share business content with a personal AI account. Enforce account/workspace boundaries on the server, including search, recommendations, background jobs, and generated summaries.

## 5. Inbox assistance and follow-ups

Help triage incoming requests, extract proposed action items, identify commitments, and draft replies. Link every extracted item to evidence and expose uncertainty. Make corrections easy; avoid duplicate tasks for the same commitment.

Distinguish replied, awaiting reply, follow-up due, snoozed, and resolved states. Let the owner review the conversation, approve a draft, choose a specific reminder time, or close the item. Only assert reply status when supported by sufficiently fresh source data.

LinkedIn follow-ups are explicitly in scope. First verify a supported, authorized integration. If unavailable, implement manual quick capture with a conversation link and last-reviewed date. Clearly label this as manual tracking; do not claim automatic inbox coverage or use unsupported scraping as a hidden dependency.

Prepare drafts by default. Sending messages or changing external systems must follow explicit owner-approved policies and any applicable tool permissions. Keep the selected sending account and recipients visible. Existing approval for a clearly defined action should not cause repeated confirmation prompts.

## 6. Calendar and meetings

Combine authorized calendars while preserving account origin. Handle time zones, daylight saving transitions, all-day events, recurring series, exceptions, and cancellations. Show calendar conflicts without resolving them silently.

Suggest realistic work blocks and buffers. Distinguish suggestions from confirmed calendar events. Allow accepting or moving a block using the intended calendar. Leave time for transitions and overruns instead of filling all free time.

Prepare meeting briefs from relevant permitted tasks, correspondence, prior notes, and decisions. Include purpose, agenda, open questions, and commitments to review. After meetings, turn user-provided notes or supported transcripts into proposed decisions, tasks, owners, and follow-up drafts. Do not assume meetings are recorded or record without explicit authorization.

## 7. Proactive reminders and daily briefing

Proactivity is a core feature. Use durable background scheduling so reminders can run when the browser is closed. A local-only version cannot promise phone delivery while its computer is asleep; explain deployment requirements honestly.

Support a morning brief, upcoming meetings, leave-time reminders when explicitly configured, approaching deadlines, promised replies, unanswered follow-ups, stalled tasks, AI work awaiting review, renewals, and a weekly review.

Give reminders an immediate action: open, start, complete, snooze to a concrete time, reschedule, dismiss, or prepare a reply. Routine items default to a digest; time-sensitive commitments can alert individually. Configure notification channels, quiet hours, frequency, and escalation. Avoid repetitive nagging, duplicate cross-device alerts, and notifications after completion or cancellation.

Implement an in-app notification center first. Select desktop/web push, mobile push, or email delivery only after confirming preferred channels and real platform support. Test at least one actual background delivery path before calling external reminders production-ready. Distinguish scheduled, attempted, delivered where verifiable, and failed notifications; do not invent delivery receipts.

Include retry policies, deduplication keys, missed-job recovery, and observable failures. Quiet-hour rules and time-zone changes must affect scheduled reminders correctly. Default notification previews should avoid exposing sensitive message content on lock screens.

## 8. Claude and Codex coordination

Model provider, product surface, authenticated account, device/environment, session, task assignment, and run as separate concepts. The three accounts must remain distinct. An account with Chat, Code, and Cowork is not automatically three independent usage budgets.

For each task, show assigned account, relevant conversation/project, objective, priority, deadline, next action, status, blocker, last update, and output requiring review. Clearly distinguish recorded status, observed activity, and inferred summaries.

Investigate supported Codex task listing/status and allowance/reset reporting through the authenticated environment. Do not assume a local connection reveals all cloud history or every device. Verify behavior before promising coverage.

Investigate Claude Code’s documented hooks/telemetry for activity and usage. For Claude Chat and Cowork, verify available integrations, account plan, and administrative permissions. Organizational analytics may be delayed and may not expose current task status. Do not claim universal live access to personal conversations or remaining subscription allowances.

If a needed connection is unavailable, provide useful manual assignment, links, status updates, and results tracking. Keep the app useful without unsupported integrations.

Separate subscription allowance, token consumption, monetary API cost, and estimated equivalent cost. Show units, source, scope, timestamp, and unknown states. Do not turn an estimate into a billing claim or assume consumer subscriptions pay for API-based features.

Dispatching work is a later capability: add it only through supported execution interfaces with explicit task instructions and scope. Include cancellation, duplicate-run protection, failure reporting, and completion review. Never dispatch the same work to multiple accounts accidentally. Credentials and execution access should stay in a narrow, authenticated service or local companion; do not expose provider runtime endpoints publicly.

## 9. Business operations and knowledge

Preserve the full earlier EA/CoS scope through reusable workflows:

- Client onboarding: required inputs, owners, handoffs, missing items, and readiness.
- Invoice follow-up: due dates, overdue tracking, and reminder drafts; no autonomous movement of money.
- Quotes/proposals: draft generation from approved information and tracked review.
- Approvals: decision owner, request age, supporting material, and next action.
- Renewals and recurring administration: due dates, reminders, checklists, and review dates.
- Knowledge: retrieval of selected approved documents with source links and freshness.
- Feedback and process issues: capture recurring problems, proposed improvements, and follow-through.
- Workload: identify overcommitment from tasks and calendar constraints.

These can begin as task/project templates rather than separate elaborate subsystems. Prioritize workflows the owner actually uses and keep the rest explicitly on the roadmap.

## 10. Technical structure and privacy

Propose a small, maintainable architecture after inspecting the repo. A typed responsive web frontend, server/API layer, relational database, and durable background worker are reasonable starting components, not a mandate to add every service. Prefer one coherent application over premature microservices. Document hosting and monthly cost assumptions before committing to paid infrastructure.

Keep these concerns distinct: interface; persistent tasks and priorities; external account adapters; scheduled jobs; notification delivery; and AI-assisted extraction, drafting, and recommendations. Core task management must work without an AI provider. Use deterministic scheduling for deadlines and reminders.

Provide a clearly labeled demo mode with synthetic data and a real mode with honest connection states. Isolate demo data from real records. Store secrets outside source control, encrypt credentials appropriately, minimize permissions, redact sensitive logs, and provide disconnect/delete controls. Use a secret manager in production and placeholder environment configuration locally.

Authenticate the app even if initially single-user. Enforce authorization on the server. Treat imported emails, documents, links, and AI outputs as untrusted data; their contents cannot override the owner’s permissions or trigger privileged actions. Separate evidence from instructions. Maintain an audit trail of significant external actions.

Design entity relationships for accounts, sources, projects, tasks, commitments, calendar events, decisions, AI sessions/runs, reminders, notifications, and user preferences. Use stable IDs, idempotent writes, migrations, backups, and safe reconnect/resync behavior. Retain only necessary content with a documented deletion policy.

## 11. Phased execution and acceptance criteria

Phase 0 — foundation: preserve the design; confirm the few necessary setup facts; document integration feasibility; choose the smallest stack; establish local setup, authentication approach, data model, and roadmap.

Phase 1 — useful daily app: implement the accepted navigation, persistent quick capture, tasks, projects, priorities, Today view, simplify mode, focus sessions, basic schedule, in-app reminders, and weekly review. Refreshing the app must not lose tasks or preferences. All visible controls must work or clearly explain their unavailable state.

Phase 2 — reliable connections and reminders: connect the first Google account, then a second; add calendar/email synchronization, source links, reply tracking, meeting briefs, follow-up drafts, and one real background notification channel. Verify cross-account isolation and reconnection. Keep LinkedIn capture usable even if direct integration is unavailable.

Phase 3 — AI coordination: represent all three accounts, assign priorities, track sessions and results through supported integrations, show accurately scoped usage, and handle unknowns. Add supported dispatch only after observation and permission boundaries are reliable.

Phase 4 — deeper operations: expand recurring business templates, selected document retrieval, better planning, additional communication sources, voice capture, and personalized reminder behavior based on feedback.

Test important behaviors: task persistence; capture and completion; keyboard/mobile usability; reminder cancellation/snoozing; time zones and daylight saving; duplicate and missed-job prevention; two-account separation; stale/revoked connections; prompt-injection resistance at action boundaries; accurate usage labels; and preventing unapproved external actions. Use focused unit/integration tests and a few end-to-end journeys, not tests that merely mirror implementation.

Before claiming completion, demonstrate a real end-to-end journey: capture a commitment, schedule a reminder, close the interface, receive the configured reminder, act on it, and confirm no duplicate reminder appears. A simulated journey is suitable for design review but must be labeled as such.

For every milestone, deliver working code, setup instructions, relevant checks, a plain-language summary, and an honest list of remaining work. Do not declare the full product finished after only building the interface.

## 12. First implementation response

Briefly explain what exists and what the first milestone will produce. Identify only the setup questions needed now: Claude business plan/admin access, device environment, first Google accounts, preferred reminder channel, and deployment/budget needs. Build independent foundation work while those answers are pending. Keep the owner’s experience simple and the full vision visible in the roadmap.

## Documentation starting points — verify before implementation

- Google authorization: https://developers.google.com/identity/protocols/oauth2/web-server
- Codex App Server: https://learn.chatgpt.com/docs/app-server
- Claude Code monitoring: https://code.claude.com/docs/en/monitoring-usage
- Claude Code hooks: https://code.claude.com/docs/en/hooks
- Claude analytics: https://platform.claude.com/docs/en/manage-claude/analytics-api

Provider capabilities and access rules change. Record what was actually verified for this owner’s accounts when implementing each adapter.
