# In-app voice assistant

## Owner intent and product scope

The owner requests voice inside the Mac app: speak naturally to add/manage tasks, prepare email replies, plan the day, and execute supported actions. This is a distinct interaction mode for the same chief-of-staff logic and personal profile, not a separate chatbot with different memory or permissions.

The product's database stays on the Mac for the initial release. A future iPhone companion may be deliberately simpler: view today's plan, capture a task/note, mark done, answer duration questions, and receive actionable reminders. Full desktop feature parity is not required. Sync and phone delivery are later work with their own infrastructure decisions.

## Feasibility, verified September 23, 2026

Official OpenAI documentation provides API-based conversational voice, with tool execution/delegation to application logic. The documented integration path is to build a voice experience with those APIs, not export the consumer ChatGPT app, its internal assistant, account memory, or model weights. Do not promise an identical ChatGPT voice, inherited subscription allowance, access to ChatGPT history, or offline execution of hosted OpenAI models.

Current documentation presents GPT-Live for new conversational applications, Realtime for its speech/session/tool model, and a speech-to-text → text agent → speech-generation pipeline as another supported architecture. Verify current model/access/pricing and native-client transport before implementation rather than freezing a model name in product requirements.

Sources:
- https://developers.openai.com/api/docs/guides/audio
- https://developers.openai.com/api/docs/guides/live
- https://developers.openai.com/api/docs/guides/realtime-conversations
- https://developers.openai.com/api/docs/pricing

Hosted voice requires internet access and transmits audio and relevant context to the provider. A locally stored database does not imply all processing stays on the device. The owner has been asked whether this is acceptable; response pending. API access and a usage budget need separate configuration before live calls. No API charges, credentials, or audio transmission have been enabled during this requirements work.

If the owner requires entirely on-device voice, investigate local speech recognition, synthesis, and reasoning alternatives separately. Do not imply they provide identical capability/quality or that offline speech recognition also makes reasoning offline.

## Intended experience

Provide a clearly labeled Talk control and visible listening/processing/speaking states, with stop/mute and a text fallback. A keyboard shortcut or click-to-talk is the recommended initial interaction; a session that stays hands-free until ended is an alternative. The choice is being interviewed, and passive always-on listening has not been requested or authorized.

Allow the owner to interrupt or correct speech. Keep concise spoken responses and a visible action receipt. Do not confuse stopping spoken playback with canceling a pending tool action: show actual action state and provide explicit cancellation where possible.

Examples of desired outcomes:

- “Add returning that package to my errands.” → create a private task, asking only for details needed now.
- “What should I do next?” → consult the current plan and explain the recommendation.
- “I'm running late; help me rearrange the afternoon.” → replan eligible flexible tasks and propose changes to protected/approved blocks.
- “Draft a reply saying I can meet next week.” → find or clarify the intended thread/account and show a draft.
- “That task took about 25 minutes.” → resolve the intended completed task and record approximate duration feedback.
- “This week I’m working on a different day.” → prepare the appropriate dated preference update and affected plan changes, without permanently replacing the standing routine or changing external meetings.

## Actions and approvals

Voice and typed interaction use the same validated action layer and permission policy. Expose narrow operations such as create/update task, get plan, propose a replan, record duration, draft email, or propose an approved-block change. Avoid granting a voice model arbitrary database/shell access.

Validate names, recipients, dates, time zones, selected Google account, and action arguments. Resolve genuine ambiguity with a short question; do not force a confirmation on every harmless private capture. Do not perform an action from partial or abandoned speech before the intended command is clear.

Email drafting is distinct from sending. Sending requires the actual connected account and explicit approval of exact recipients/body/attachments. Use a visible review panel for consequential actions; the method of approving by voice versus click is a later explicit design decision. The same applies to invitations, external calendar writes, and document sharing. Nothing about voice expands the permission tiers.

Only say an action succeeded after the application reports success. Distinguish proposed, drafted, queued, completed, failed, and uncertain states. Use operation IDs and idempotency so reconnection or repeated utterances do not duplicate tasks or messages. A failed/uncertain send must be reconciled before retrying.

Use a minimal authorized context from the profile, current plan, and selected source records. Untrusted email/document/tool content remains data and cannot override permissions. Keep business/personal sharing boundaries intact.

## Privacy, operation, and cost

Obtain microphone permission using the platform flow and make recording state unmistakable. End sessions deliberately on user request and handle network loss, app backgrounding, device sleep, and audio-device changes. No automatic meeting recording or background microphone capture.

Raw audio need not be retained by the application; any retained transcript or conversation history should have an explicit purpose, user-visible retention controls, and private storage. Do not imply that an app retention setting changes the provider's own data policy.

Keep API keys in protected local credential storage for a single-owner native app, with privileged networking/tool execution isolated from untrusted UI/model content. Do not embed a shared production secret in distributable clients. A future distributed phone app may need a different authenticated credential/session architecture.

Before enabling paid voice, select an API budget and implement usage visibility, session timeout, spending safeguards, and a text-only fallback. Distinguish configured estimates from provider-reported billing. No cost quote is fixed by this document; current rates must be checked at implementation.

## Implementation sequence and checks

Make voice a named planned milestone once persistent tasks/profile and their action layer work; do not bury it under optional distant research features. First voice actions can cover task capture, plan questions, and duration feedback. Email drafting becomes available when the corresponding account integration is ready; sending remains approval-bound.

The Mac-only phase cannot guarantee planning or phone notifications while the Mac is powered off. Already scheduled local notifications and background behavior need platform-specific validation; catch up missed app work on resume without duplicate alerts.

Verify actual microphone-to-action flows, ambiguous dates/contacts, interrupted corrections, permission boundaries, duplicate prevention, offline failures, cancellation state, credential protection, and accurate completion feedback. Keep synthetic demonstrations separate from live provider sessions. Test that a spoken task survives restart and that drafting an email never silently sends it.
