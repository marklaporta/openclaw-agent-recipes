# More Personal-Agent Automation Recipes

Copy a prompt below into your agent. Each describes a capability, not a working integration: the agent must discover available tools and establish access before scheduling it. Names, locations, identifiers, thresholds, and destinations are supplied privately by the person setting it up.

For each recipe, explain the proposed behavior, reuse preferences already supplied, and ask only for missing choices that affect scope or delivery. Agree on unresolved choices before enabling the schedule. Existing authorization need not be requested again.

## 1. Learning Progress Reports

```text
Set up learning-progress updates from my child's school learning platform, such as TimeBack.

Establish authorized parent access, which student and sources to monitor, school-day timing, meaningful milestones, report frequency, and a private destination. If access or a required source is unavailable, identify the gap rather than inventing a report.

Keep timestamped observations for activity, assessments, course progress, and goals. Send change-only updates and a periodic retrospective. Prioritize new assessments and learning milestones; use activity to help parents understand what their child is working on.

Distinguish activity points from mastery and logged activity from continuous study time. An open goal is not necessarily overdue or assigned; check assignment evidence and known app outages. Preserve assessment type and result. Deduplicate the same result across views, label corrections, and keep last-good observations when a source fails. Missing data is not no progress.

Keep other students' identities out of reports. Compare equivalent periods with source coverage stated; use the initial collection as a baseline, not a flood of old alerts.
```

## 2. School Photo Relay

```text
Relay new classroom photos from an authorized school portal to my chosen private family destination.

Establish portal access, the exact class/group, who may receive the photos, and check frequency. Use the class's own feed where a general feed may omit posts. If login expires, report the access problem without treating the feed as empty.

Send new photo sets with brief source/date context. Inspect attachments to distinguish classroom photos from unrelated graphics; do not identify other children. Keep the school portal read-only: no reactions, comments, or posts.

Use stable post/image identifiers to deduplicate. Download permitted attachments while temporary links remain valid; do not publish signed URLs or cookies. Record successful delivery only after a confirmed receipt, and reconcile uncertain sends before retrying. Keep downloaded images and state private with an agreed retention period.
```

## 3. After-School Conversation Prompts

```text
Send one relevant, open-ended question to help me talk with my child about a scheduled activity.

Use my activity calendar or supplied schedule, timezone, preferred delivery time, and private destination. Check known cancellations, breaks, and schedule corrections before sending. Skip canceled activities and reminders too late to be useful.

Mention the scheduled activity, then ask one fresh question inviting explanation, demonstration, or reflection. Avoid repeating recent questions. Do not invent the day's lesson, recipe, project, or sport, or claim attendance merely because an event was scheduled. Keep the message to about two sentences.
```

## 4. Flight Disruption Watch

```text
Monitor my booked flights for actionable disruptions.

Establish itinerary access or privately supplied flight numbers, dates, airports, timezones, monitoring windows, and destination. Use flight-status sources that distinguish the exact dated leg; include inbound-aircraft status when available.

Alert on material delays, cancellations, or other travel-changing updates. When useful, show plausible same-day alternatives with source timestamps, distinguishing published schedules from verified seat availability. Do not rebook or purchase anything.

Stay silent outside the travel window and when nothing material changes. Missing or stale source data is not an on-time result. Deduplicate alerts, define when each leg's watch ends, and retire completed itineraries. Keep booking references and passenger details out of notifications unless needed by the authorized recipient.
```

## 5. Home Temperature And Equipment Monitoring

```text
Monitor selected rooms for temperature problems and connected heating/cooling equipment left running.

Establish authorized sensor/device access, room labels, preferred thresholds, sustained-duration requirements, equipment runtime limits, check frequency, and a private alert destination. If only temperature is available, do not infer that equipment is on.

Log timestamped readings and optionally provide overnight trends with outdoor context when available. Alert on sustained threshold crossings or excessive verified runtime, with cooldown/recovery rules to prevent repeated messages. Distinguish stale or unavailable sensors from normal readings.

Default to observation and alerts. Change device settings only within explicitly authorized control rules; a temperature alert alone does not authorize turning equipment on or off.
```

## 6. Local Earthquake Alerts

```text
Set up location-filtered earthquake notifications using an authoritative feed such as USGS.

Privately establish the reference location, distance/magnitude criteria, check frequency, and destination. Use event identifiers and source timestamps; report magnitude, distance, event time, and an official link. Label preliminary values and alert on revisions only when they materially change relevance.

Record notification state after confirmed delivery so failed sends remain recoverable. Distinguish feed failure from no qualifying events. Keep the reference address or precise home coordinates out of messages and public artifacts.

Describe this as a post-event information watch, not earthquake prediction or a substitute for official early-warning or emergency alerts.
```

## 7. Personalized Media Recommendations

```text
Create a periodic shortlist of films, series, and documentaries matched to the intended viewers.

Establish shared tastes, dislikes, completed titles, time budget, region, streaming services, list length, cadence, and destination. Use explicit feedback to maintain watched/liked state; receiving a recommendation does not mean someone watched it.

Verify current regional availability, distinguishing subscription access from rental or purchase. Recommend fresh options without spoilers; explain the fit, time commitment, and a concrete reason each might miss. Keep an existing watch queue separate from new suggestions and avoid repeatedly pitching the same titles.

If availability or feedback is stale, label that limitation rather than claiming a fresh check. Do not subscribe, rent, or purchase automatically.
```

## 8. Release Watches And Reread Planning

```text
Watch selected books or other media for verified release news, with optional reread planning for a book series.

Establish titles, preferred edition/format and region, authoritative sources, check cadence, destination, and reading-duration estimates. Verify announcements against author/publisher or equivalent official sources; retailer placeholders and rumors are not confirmed dates.

Send only material new announcements or due reminders. For rereads, calculate a start date from the release date and reading duration, label estimates, and recalculate when either changes. Flag overlapping plans or insufficient time rather than promising an impossible finish.

Keep observation state separate from confirmed notification history. Increase checks near relevant dates if useful, avoid spoilers, and retire the watch after its agreed completion condition. Do not preorder automatically.
```

## 9. Personalized Research Briefings

```text
Monitor selected publications, newsletters, or podcasts and brief me on new material relevant to my interests or decisions.

Establish authorized access, source scope, interests, cadence, private delivery destination, and whether a searchable personal archive is wanted. Respect subscription access; share original links and concise analysis, not subscriber-only source copies.

Detect new or changed items before generating a briefing. Read the complete relevant source, retaining its date, version, and attribution; label incomplete coverage. Claim a change only after comparing versions.

Separate the author's position, guest opinions, research findings, and your interpretation. State the specific takeaway and what it changes or confirms for me, checking current personal context only where needed. Preserve uncertainty and check stronger/current evidence before consequential recommendations. Do not automatically change medication, treatment, or training plans.

Stay silent on unchanged content and distinguish access failures from successful no-change checks.
```

## 10. Saved-Links Digest

```text
Maintain a private read-later queue and periodically resurface unfinished items.

Establish how I save links, the digest cadence, maximum items, destination, and completion commands such as done or drop. Keep each item's URL, title, saved date, and optional reason; deduplicate repeated saves without losing useful context.

Show only open items, with links and enough context to recognize why I saved them. Mark items completed or dropped only from explicit feedback, not because a digest was delivered. Stay silent when the queue is empty.

Keep authenticated, private, or token-bearing links out of public outputs. If an item cannot be retrieved, retain the saved reference and say so rather than inventing a summary.
```
