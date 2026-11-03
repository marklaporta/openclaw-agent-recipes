# OpenClaw Cron Capability Examples

Generalized capability patterns for personal-agent crons. The examples intentionally avoid personal names, addresses, private domains, exact chat IDs, private health details, family composition, and exact reminder cadences.

## Capability Inventory

These are generalized capability patterns, not a literal dump of any one person's cron registry.

| Capability | Minimal summary |
| --- | --- |
| Time-sensitive email response watch | Polls for a specific high-stakes reply and escalates at deadline if needed. |
| Actionable email scan | Periodically scans email for actionable personal/household/admin items. |
| Calendar/source reconciliation | Reconciles household or school calendar entries against source emails/notes. |
| Memory promotion | Promotes repeatedly useful short-term memories into long-term memory. |
| Recent-context wiki harvest | Backfills durable knowledge from recent notes into a structured wiki. |
| Deep memory harvest | Maintenance pattern for deeper memory harvesting when tool access supports it. |
| OAuth expiry watch | Refreshes or alerts on expiring model/provider auth credentials. |
| Embedding refresh | Refreshes semantic indexes for memory/wiki/session search. |
| Wearable recovery flag | Sends health alerts only when wearable signals are actionable; supports fallback timing. |
| Tax deadline reminder | Handles advance and due-day tax reminders. |
| Plugin update evaluation | Checks pinned plugins for available updates; does not auto-update. |
| Exact reminder scheduler | Handles simple recurring or one-shot reminders without exposing private details. |
| Documentation proof reminder | Reminds a user or household to gather proof for a paperwork workflow. |
| Weekend activities digest | Finds kid-friendly weekend outings, respecting calendar constraints. |
| Weekly system improvement review | Reviews tips, crons, system hygiene, and proposes improvements. |
| Wiki maintenance | Runs wiki lint, graph/entity reports, and alerts on material changes. |
| Weekly health report | Synthesizes weekly health data into a short action report. |
| Household week-ahead summary | Sends household logistics summary for the coming week. |
| Household service reminder | Reminds household before a recurring service or maintenance task. |
| Personal weekly briefing | Personal weekly ops review, distinct from household summary. |
| Important date reminder | Handles birthday, anniversary, and milestone reminders generically. |
| Home/admin deadline reminder | Tracks one-shot household, warranty, registration, or admin deadlines. |
| Monthly ops audit | Audits cron/session/system hygiene monthly. |
| School paperwork reminder | Reminds a household to prepare school or medical paperwork. |
| Personal maintenance reminder | Recurring personal maintenance reminder. |
| Domain status and expiry watch | Checks registration, lock, and expiry status and sends expiry reminders. |

Additional setup prompts: [learning, home, travel, media, research, and saved links](additional-capabilities.md).

## Public Setup Prompt Families

Each prompt family is written for someone asking their own OpenClaw or Hermes agent to stand up the capability. Replace bracketed placeholders before use.

When a prompt refers to a wiki, it means a Karpathy-style LLM Wiki: a local, agent-maintained markdown knowledge base with schema/resolver instructions, source notes, cross-links, and maintenance/lint passes. Reference: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f. If the platform has native wiki/memory tools, use them; in OpenClaw this maps to `wiki_search`, `wiki_get`, `wiki_apply`, `wiki_lint`, and `wiki_status`. In Hermes or a simpler local setup, use a markdown vault/folder plus filesystem access and explicit agent instructions.

### 1. Email Triage And Deadline Watch

Consolidates:
- time-sensitive email response watch
- actionable email scan
- deadline fallback/escalation
- waiting-on-reply nudges

```text
Set up an email triage and deadline-watch capability.
First, explain this capability in plain English. Then ask what I want to customize: email source, watched topics/senders, scan cadence, quiet hours, actionable categories, deadlines, escalation behavior, alert destination, tone, and exclusions. Recommend sensible defaults if I am unsure, confirm the final shape, and only then wire it up.

Goal:
Use connected email to surface only messages that require action, while also watching specific high-stakes threads until a deadline.

Prerequisites to check first:
1. Email access is connected, such as Gmail, IMAP, or a local email-search script.
2. There is a deterministic gate script or query that prints nothing/NO_REPLY when nothing actionable exists.
3. I have defined actionable categories, such as deadlines, forms, appointments, finance, legal, insurance, travel, school, household, or other admin.
4. I have chosen an alert destination.
5. Optional: a durable source-notes file for events or facts that later need calendar/source reconciliation.

If a prerequisite is missing:
- Help me connect email or provide a local export/search command.
- Help me create a deterministic gate script.
- Ask which categories count as actionable.
- Ask where alerts should go.
- Create a source-notes file if I want later reconciliation.

Implementation:
Create one or more crons as needed:
1. General actionable-email scan during my chosen waking window.
2. Optional focused watcher for a specific thread/sender/topic.
3. Optional one-shot deadline fallback that rechecks once and tells me to escalate if there is still no reply.
4. Optional waiting-on-reply digest: find my outbound requests still awaiting a human response after an agreed business-day interval. Recheck full threads and related replies; exclude automated mail, resolved requests, and messages that did not ask for a response. Agree on holiday handling, a per-thread cooldown, and an age limit. Remind me without automatically drafting or sending follow-ups.

Rules:
- Run deterministic search/gate logic first.
- If nothing actionable exists, final response exactly NO_REPLY.
- Summaries should include only action, deadline, date/time/location if relevant, and source clue.
- Do not quote whole emails.
- Do not send status chatter.
- If an email contains an event/source fact needed later, append one compact source note.
```

### 2. Calendar And Source Reconciliation

Consolidates:
- calendar/source conflict audits
- advance reminders
- household or school week-ahead summaries
- school paperwork reminders

```text
Set up a calendar and source-reconciliation capability.
First, explain this capability in plain English. Then ask what I want to customize: calendars, source documents/emails, look-ahead window, reminder lead times, travel/departure logic, alert destination, household scope, dedupe rules, and how cautious the audit should be. Recommend sensible defaults if I am unsure, confirm the final shape, and only then wire it up.

Goal:
Prevent missed events and calendar/source mistakes by comparing calendar entries against source emails, notes, or documents, then sending only useful reminders or conflict alerts.

Prerequisites to check first:
1. Calendar access is connected.
2. Source emails, documents, or durable source notes exist.
3. A delivery route exists for the relevant person or household.
4. A helper script/tool can list upcoming events.
5. Timezone and optional location/travel assumptions are clear.

If a prerequisite is missing:
- Help me connect calendar access or create a calendar export command.
- Create a durable source-notes file and start populating it from future messages.
- Ask where reminders should be delivered.
- Ask what categories matter: school, childcare, medical, travel, events, pickups/dropoffs, forms, or other household logistics.

Implementation:
Create the smallest set of crons that fits the user's desired workflow:
1. Rolling audit: scan the next [N] days for missing locations, suspicious times, source/calendar conflicts, or source events missing from the calendar.
2. Reminder pass: send today/tomorrow/[lead-time] reminders for events that passed reconciliation.
3. Optional week-ahead summary: summarize the next [N] days of household logistics.
4. Optional paperwork reminder: alert before forms, records, or documents are needed.

Rules:
- Treat calendar entries as provisional.
- Prefer source emails/notes/documents when they conflict with calendar entries unless a newer correction exists.
- Deduplicate repeated risk alerts unless new information appears or urgency materially changes.
- Include time, location, action needed, and departure guidance only when useful.
- Do not include weather unless explicitly requested.
```

### 3. Reminder And Deadline Scheduler

Consolidates:
- medication schedule reminders
- tax or admin deadlines
- household service reminders
- important dates
- personal maintenance reminders
- documentation/proof collection
- domain or account expiry reminders when only a deadline is needed

```text
Set up a reminder and deadline scheduler.
First, explain this capability in plain English. Then ask what I want to customize: reminder items, schedules, timezone, lead times, recurrence, delivery destination, exact wording, disable conditions, whether multiple schedules need multiple crons, and whether any reminder contains private details that should be generalized. Recommend sensible defaults if I am unsure, confirm the final shape, and only then wire it up.

Goal:
Create reliable one-shot or recurring reminders with minimal agent reasoning and no unnecessary personal detail.

Prerequisites to check first:
1. Reminder text for each item.
2. Schedule/timezone/lead time for each item.
3. Delivery destination.
4. Whether each item is one-shot, recurring forever, recurring until a completion condition, or recurring until a date.
5. Whether grouped reminders should be one cron or separate crons.

If a prerequisite is missing:
- Ask for the missing reminder text, schedule, timezone, delivery target, or completion rule.
- For medication or other private reminders, ask whether there are multiple items or schedules. Create separate crons when schedules or delivery rules differ enough that separate reminders are clearer.
- For paperwork/proof workflows, ask what completion means and when to disable the reminder.

Implementation:
Prefer deterministic reminders over LLM reasoning when the platform supports it. Otherwise create exact-text crons that:
- send exactly the reminder text
- add no commentary
- use the cheapest reliable model
- return NO_REPLY after successful delivery when appropriate

Safety:
- Avoid exposing private medication names, dosing cadence, child ages, family composition, addresses, account IDs, or sensitive source details in public examples.
```

### 4. Health Data Signals

Consolidates:
- wearable recovery flags
- wearable sync fallback checks
- weekly health reports
- manual health export reminders when treated as a reminder

```text
Set up a health-data signal capability.
First, explain this capability in plain English. Then ask what I want to customize: data sources, health goals, metrics, baseline window, alert thresholds, check cadence, fallback timing, weekly report format, delivery destination, privacy level, and what should stay silent. Recommend sensible defaults if I am unsure, confirm the final shape, and only then wire it up.

Goal:
Use wearable or health exports to alert only when the data should change behavior, and optionally produce a concise periodic report.

Prerequisites to check first:
1. Health data source is available, such as Oura Ring, Apple Health export, Garmin, Whoop, training log, scale, or lab/body-composition data.
2. A script can produce structured data, preferably JSON.
3. Baseline windows are defined.
4. A state file exists to prevent duplicate same-day alerts.
5. A health alert destination exists.

If a prerequisite is missing:
- Help me connect/export health data.
- Create a structured health-report script.
- Create a state file keyed by date.
- Ask which goals matter: illness detection, recovery, training readiness, body composition, adherence, or long-term trend monitoring.

Implementation:
Create one or more crons:
1. Daily signal check: alert only for meaningful changes that should affect today's behavior.
2. Optional fallback check: rerun later if early data often arrives late.
3. Optional weekly report: compare the latest complete period against recent baselines and produce a concise bottom line.

Rules:
- If core data is missing, return NO_REPLY unless missing data itself needs attention.
- Alert only on interpretation-changing signals or combinations.
- Use underlying metrics, not only app-generated readiness scores.
- Keep alerts short: changed metric, likely interpretation, one concrete action.
- Never invent missing data.
```

### 5. Knowledge, Memory, And Wiki Maintenance

Consolidates:
- long-term memory promotion
- recent-context wiki harvest
- semantic embedding refresh
- wiki lint/graph maintenance
- deep memory harvest when supported

```text
Set up knowledge, memory, and wiki maintenance.
First, explain this capability in plain English. Then ask what I want to customize: memory sources, wiki scope, promotion thresholds, harvest cadence, source retention, evidence rules, lint/graph checks, embedding/index refresh, alert destination, and what should remain private or short-term only. Recommend sensible defaults if I am unsure, confirm the final shape, and only then wire it up.

When explaining the wiki, reference Karpathy's LLM Wiki gist and the platform capability that supports it. For OpenClaw, use `wiki_search`, `wiki_get`, `wiki_apply`, `wiki_lint`, and `wiki_status` where available. For Hermes/local agents, use a markdown wiki folder with source notes, schema/resolver instructions, and filesystem access.

Goal:
Keep useful knowledge findable without letting raw logs, transient chatter, or private sludge dominate long-term memory.

Prerequisites to check first:
1. Short-term memory, daily notes, transcripts, or session logs exist.
2. A compact long-term memory file or database exists.
3. A Karpathy-style wiki or notes vault exists if domain knowledge should live outside memory: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f.
4. A schema/resolver explains what belongs where.
5. Optional: embedding/index refresh exists.
6. Optional: lint, graph, and maintenance-log scripts exist.

If a prerequisite is missing:
- Create a compact long-term memory file with clear sections.
- Create a wiki root with schema/resolver instructions if domain knowledge matters.
- Create daily notes/transcripts as source material.
- Add lightweight lint/check scripts before adding heavier graph/entity reports.
- Add a deterministic gate that returns NO_REPLY when nothing changed.

Implementation:
Create the smallest set of maintenance jobs needed:
1. Memory promotion: promote only compact facts above clear thresholds.
2. Wiki harvest: review recent context and file durable domain knowledge with evidence pointers.
3. Index refresh: update embeddings/search indexes and alert only on failures or stale collections.
4. Wiki maintenance: run lint/graph/entity checks and alert only on material changes or blockers.

Rules:
- Prefer updating existing pages over creating duplicates.
- Preserve source pointers.
- Avoid raw chat dumps.
- Keep control-plane behavior rules separate from substantive domain knowledge when useful.
- Return NO_REPLY when there is no meaningful change.
```

### 6. Agent Ops And Reliability

Consolidates:
- OAuth/auth expiry watch
- plugin update evaluation
- weekly system improvement review
- monthly ops audit
- doctor/smoke checks

```text
Set up agent ops and reliability maintenance.
First, explain this capability in plain English. Then ask what I want to customize: monitored providers, auth profiles, plugin/update policy, cron/session audit scope, smoke tests, review cadence, alert destination, and what actions require approval. Recommend sensible defaults if I am unsure, confirm the final shape, and only then wire it up.

Goal:
Keep the agent healthy without allowing maintenance jobs to make risky changes silently.

Prerequisites to check first:
1. CLI commands exist for cron list/runs, session list/cleanup dry run, doctor/health checks, and provider auth status.
2. Plugin install metadata includes pinned versions or enough information to evaluate updates.
3. One or two smoke tests exist for important capabilities.
4. An Ops alert destination exists.
5. Approval boundaries are clear.

If a prerequisite is missing:
- Locate or create the missing CLI inspection command.
- Pin plugin versions before scheduling update checks.
- Create dry-run maintenance commands before enabling automatic fixes.
- Ask where Ops alerts should go.

Implementation:
Create one or more maintenance jobs:
1. Auth watch: refresh silently when safe; alert when manual login is needed.
2. Plugin update review: report available updates, but do not install automatically.
3. System improvement review: classify tips/ideas as adopt, investigate, or reject.
4. Monthly ops audit: inspect crons, sessions, doctor output, smoke tests, and recurring failures.

Rules:
- Do not update, restart, delete, or enforce cleanup unless explicitly allowed.
- Return NO_REPLY when clean.
- Alert only on actionable findings, blockers, or approval-needed changes.
```

### 7. Planning And Briefing

Consolidates:
- weekend activity planning
- personal weekly briefings
- household week-ahead summaries when no source reconciliation is needed

```text
Set up a planning and briefing capability.
First, explain this capability in plain English. Then ask what I want to customize: audience, planning horizon, calendar sources, location or area, activity constraints, source preferences, briefing sections, delivery destination, and what should be excluded. Recommend sensible defaults if I am unsure, confirm the final shape, and only then wire it up.

Goal:
Turn recent notes, calendars, reminders, and current event sources into concise planning output.

Prerequisites to check first:
1. Calendar/reminder access or local exports exist.
2. Daily notes or activity logs exist if reviewing recent context.
3. Location/area and activity constraints are known for activity planning.
4. Web search or trusted local event sources are available if current events matter, such as 510families.com for Bay Area family activities.
5. Delivery destination exists.

If a prerequisite is missing:
- Connect calendar/reminders or use local exports.
- Create daily/activity logs going forward.
- Ask for area, audience, constraints, and preferred sources.
- For Bay Area family activity planning, consider 510families.com as a useful default source if the user wants local family events.
- Ask where to deliver the brief.

Implementation:
Create the desired briefing/planning cron:
- Weekend/activity digest: check commitments first, find realistic options, group by day/time fit, and include booking notes where useful.
- Personal weekly brief: cover week in review, week ahead, open loops, and prep needed.
- Household summary: organize the next [N] days by day and exclude irrelevant work-only/admin-only items.

Rules:
- Avoid generic filler.
- Avoid duplicating specialized logistics reminders.
- Keep output concise and action-oriented.
- Do not include weather unless explicitly requested.
```

### 8. External Asset Status Watch

Consolidates:
- domain status checks
- domain expiry reminders
- other external account/asset status checks where current state can be queried

```text
Set up an external asset status watch.
First, explain this capability in plain English. Then ask what I want to customize: asset type, identifier, expected provider/registrar/vendor, status fields to monitor, check cadence, expiry lead times, alert destination, and what changes are material. Recommend sensible defaults if I am unsure, confirm the final shape, and only then wire it up.

Goal:
Prevent losing or misconfiguring an important external asset by checking authoritative status and alerting only on material changes or upcoming expiry.

Prerequisites to check first:
1. Asset identifier, such as a domain, account, subscription, certificate, license, or registration.
2. Expected provider or authoritative lookup method.
3. Current expected status and expiry/renewal behavior if known.
4. Alert destination.

If a prerequisite is missing:
- Use an authoritative lookup where possible, such as RDAP/WHOIS for domains.
- Ask who owns billing/admin access.
- Ask what status fields matter.

Implementation:
Create one or more crons:
1. Periodic status check: fetch authoritative status and alert if provider, expiry, lock/renewal, or status changes unexpectedly.
2. Expiry reminder: alert before the renewal/expiry deadline with the action needed.

Rules:
- Do not include private account IDs or billing details in public examples.
- Alert only on material changes, upcoming expiry, or lookup failure.
```
