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

## 11. Family Photo Meme Generator

```text
Turn a photo stream of my choice into a private, searchable meme library and an on-demand meme-generation skill.

Establish read-only access to my chosen album, folder, shared stream, or photo service; a private index location; and tools for visual review and image rendering. Reuse existing preferences for source scope, exclusions, humor, intended audience, and delivery. Establish which local or hosted tools may process the photos, and a review cadence and processing budget. If a source or tool is unavailable, identify the missing capability rather than claiming the workflow is connected.

Index still images using stable source IDs and resolvable image pointers, not expiring download URLs or embedded credentials. Store source/version, review status, visible expressions and actions, composition, text/overlays, usable resolution, reaction tags, and caption-space notes. Attribute existing people labels to their source; do not infer identities from appearance. Keep visual observations separate from metadata-only inventory and hypothetical joke interpretations.

Score every reviewed photo for meme potential: 0 unsuitable, 1 context-dependent, 2 useful, 3 standout. Save a reason based on reusable comic reaction or contrast, readability at phone size, framing, and dependence on original context; cuteness alone is not a high score. Record likely comic perspectives, such as the pictured subject's imagined inner monologue, the photographer's viewpoint, or an observer's reaction, with suggested situations and why they fit. These are caption angles, not claims about anyone's actual thoughts or feelings.

Make ingestion incremental and restart-safe: deduplicate by source ID/version, retain completed enrichment, retry unavailable images without inventing labels, and process new or changed assets rather than relabeling the entire library. Track reviewed, pending, and unavailable counts separately. Preserve originals; keep generated derivatives linked to their source. Store explicit user ratings, rejected images, and recent selections to improve future choices.

Create and wire up a reusable skill triggered by requests for family-photo memes or new photo options. It must search the enriched index by the requested situation, reaction, and perspective; retrieve and visually inspect candidates; and distinguish genuinely new photos from new captions on an old selection. For options, return distinct numbered photos with one caption each. For finished memes, render the requested number of distinct selected images with exact captions, preserving expressions and keeping lettering clear of faces. Retain source provenance and deliver each result only once to the authorized destination.

Keep photos, thumbnails, names, source pointers, enrichment, feedback, and generated memes private and outside public repositories. Share only generic setup instructions or synthetic examples. Verify a small end-to-end sample: source retrieval, saved enrichment, incremental rerun without duplicates or lost reviews, index-based selection, and one requested rendered result. Report any unverified integration instead of presenting it as working.
```

## 12. Driveway Arrival And Help Alerts

```text
Recognize selected vehicles arriving in my driveway and send a timely private alert so someone can go out to help.

Establish authorized camera/event access with license-plate recognition and directional entry detection, a driveway-only detection boundary, privately supplied vehicle labels and exact plate mappings, and the intended helpers and destination. Define whether the useful cue is inward entry or confirmed parking, plus any time-of-day or vehicle-specific rules. If the system cannot distinguish these events, report that limitation rather than enabling generic motion alerts as a substitute.

Prefer native plate and directional events when supported. A plate read identifies a vehicle, not an arrival: associate the exact plate match with the same tracked vehicle's inward crossing or verified parking episode. Exclude street traffic, departures, already-parked vehicles, and repeated plate reads. Do not use fuzzy plate matches to assign a household identity, infer the driver or passengers, or interpret an unknown vehicle as a threat. If identity is uncertain, omit the name and send a generic arrival cue only if that fallback was requested.

Send one short alert per physical arrival using the private vehicle label and the requested help cue, such as “Known vehicle arrived — someone available to help unload?” Deduplicate repeated events durably without suppressing a second distinct arrival close behind. Record confirmed delivery separately from detection, reconcile uncertain sends before retries, and do not replay stale arrivals after an outage. Report camera or event-stream failure separately from no arrivals.

Let the alert prompt a person to respond. Contact or dispatch a helper automatically only under the user's explicit recipient and action rules; a plate match alone does not authorize paid services or emergency dispatch.

Keep plate numbers, household mappings, camera links, credentials, locations, and footage private; alert text usually needs only the chosen vehicle label. Agree on retention for event evidence. Validate in shadow mode against a real inward arrival and street-pass, departure, parked-car reread, duplicate, and close-arrival cases before enabling notifications. Distinguish simulated checks from observed camera behavior, and verify the next live arrival's timing and single delivery.
```
