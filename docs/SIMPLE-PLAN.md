# The plan, in plain English

We are building a Mac app first, then an iPhone app. For now, the app’s saved data stays on your Mac. Later, a simple iPhone companion can show your day, accept quick input, and deliver reminders using a sync setup we choose then. It will help run your whole day: work, chores, meals, shopping, appointments, and everything you need to remember.

The design you approved is still our starting point. It is currently a clickable picture of how the app can work, not the actual installed app.

## The pieces

1. **The app:** the calm screen you open to see what matters next.
2. **The memory:** a private database saves tasks, promises, routines, and your preferences. “My preferences” lets you see and change what the app knows. “This week only” changes do not overwrite your usual routine.
3. **The planner:** automatically fits flexible tasks around your existing calendar. It asks before blocking a long errand outing and adjusts gym plans week by week.
4. **The learning:** asks “roughly how long?” when you mark something done. You can answer later; questions wait quietly in a queue. Your answers improve the next estimate.
5. **The connections:** brings in email, calendars, and supported information from your AI accounts.
6. **The reminders:** alerts you at useful times and lets you act, postpone, or adjust.
7. **The locks:** keeps account information separate and makes sure important outside actions need your approval.

The first version runs on your Mac. It cannot promise to perform new work while the Mac is off. Online AI voice is a separate option: the app can store your data locally while sending a spoken request and needed context to an AI service. That needs internet access, suitable API access, and a usage budget.

## What we're doing now

The core instructions are ready to build from. The app has not been built yet. Mac-only storage is settled. We still need to confirm voice processing/privacy and usage budget, whether approved blocks appear in Google Calendar, and notification settings. Smaller routine details can be chosen in the app’s settings.

We have settled Mac first, iPhone later; automatic flexible-task scheduling with approval for large errands; and short duration questions after completion.

Your usual gym week is now recorded, including preparation, walking, and cardio. Your workday wake time is 7:30 a.m. and approximate bedtime is midnight; an editable bedtime setting will help keep plans realistic. Your usual office days are Tuesday and Wednesday; classes are Monday, Tuesday, and Thursday evenings. The app will plan the night before, adjust in the morning, and nudge every 10 minutes, and help replan missed tasks. Tuesday dinner and travel are protected. After 20 minutes without a response, it proposes moving the task. You approve the week’s gym times before they are reserved.

Then we agree what the first version must do. The suggested starting point is daily planning, tasks, household routines, reminders, and better time estimates. Email/calendar assistance and deeper AI coordination follow in manageable steps; the original business features remain in scope.

## Talking to the app

The proposed voice feature lets you speak a request, have the app understand it, and use the same task/email/calendar controls as typing. For example: “Add an errand,” “What’s next?” or “Draft a reply.” Sending a message still follows your approval rules.

We would build this with supported voice APIs rather than export the ChatGPT app. You start a conversation once, then talk hands-free until you end it. Mute and End conversation stay visible. We are only clarifying whether the AI processing may happen online while saved data stays on your Mac.

## Three planning steps

**Sunday evening:** decide the shape of your week. Confirm office days, approve gym times, and choose suitable blocks for errands.

**Each night:** fit tomorrow's flexible tasks into that framework.

**Each morning:** adjust for anything that changed. Approved gym/errand blocks and your existing events stay protected.

If your week changes, update the plan then; you do not have to wait for the next Sunday.

## One example

You add “do laundry.” The app helps break it into starting the wash, transferring it, and putting it away. It knows machine waiting time is different from your working time. If you tell it folding took longer than expected, it allows more time next time.

For shopping, it might propose one Friday morning outing with several stops, then wait for your approval. It will not assume every Friday is reserved for errands.

If the day goes off track, you can say “I'm running late.” It helps you choose a smaller plan without changing your meetings or promises behind your back.

## What is ready

The updated build prompt, a capability review, the interview record, and the approved design. The installed app is not built yet.
