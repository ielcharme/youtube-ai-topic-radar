---
name: youtube-ai-topic-radar
description: Monitor a curated multilingual set of YouTube AI creators and turn their recent topics into source-backed, original video-planning references. Use for biweekly creator scans, AI topic trend reports, English/French/German/Spanish comparisons, roster maintenance, or video ideation based on recent creator activity. Do not use to copy or automatically publish content.
---

# YouTube AI Topic Radar

Track what selected AI creators are publishing, identify useful patterns across languages, and convert the evidence into original video directions.

## Required resources

- Always read [references/creator-roster.md](references/creator-roster.md) before scanning channels or changing the watchlist.
- Read [references/report-format.md](references/report-format.md) when producing a refresh report, structured dataset, or video brief.

## Modes

Choose the narrowest mode that satisfies the request:

- **Refresh:** collect uploads from the monitoring window and update the topic report.
- **Video reference:** use an existing report to create original topic, hook, title, format, and production suggestions.
- **Roster maintenance:** verify renamed, inactive, duplicate, or newly relevant channels. Mark proposed changes; do not silently remove a creator from the curated roster.

## Refresh workflow

1. Determine the window. For the scheduled run, scan from the previous successful refresh; if no valid state exists, use the latest 16 calendar days to provide a two-day overlap.
2. Inspect every channel in the roster. Prefer the creator's YouTube channel and video pages. If YouTube is unavailable, use search results or a reputable channel-stat source and label the fallback.
3. Record each qualifying upload with creator, language, original title, Chinese title translation, publish date, video URL, visible views when available, format, and multiple content tags.
4. Treat blocked or inaccessible pages as unavailable data, not proof that the creator posted nothing. State coverage gaps explicitly.
5. Deduplicate by canonical video URL. Cluster related videos by underlying topic while preserving different creator angles and languages.
6. Use multi-label classification. A video may simultaneously be about AI tools, productivity, marketing, entrepreneurship, coding, or lifestyle.
7. Rank topic opportunities using the scoring method in the report reference. Separate cross-channel momentum from one-off but original ideas.
8. Produce the Chinese report and machine-readable dataset described in the report reference. Keep original-language titles beside translations.
9. When file writes are available, save an immutable dated report and replace the latest report and dataset. If a write fails, still return the report and identify the exact unavailable boundary.

## Evidence rules

- Link every included video to its source and record the publication date.
- Treat subscriber counts, view counts, sponsorship status, and upload frequency as time-sensitive. Add an observation date and never invent missing values.
- Separate creator claims, observed facts, and analysis. Note sponsorship or affiliate disclosure when visible.
- Use other creators as signals and references, not as factual confirmation of AI product claims. Verify consequential product, policy, pricing, or technical claims against primary sources before recommending them as facts.

## Creative boundary

- Generate original synthesis. Do not reproduce scripts, thumbnail compositions, distinctive phrases, or title wording verbatim beyond what is necessary to identify a source.
- Describe reusable patterns such as pacing, hook structure, demonstration style, audience level, and topic framing.
- Do not publish, comment, subscribe, contact creators, or modify external accounts without separate authorization.
- Use public information only; do not bypass logins, paywalls, or platform controls.

## Default output location

Relative to this skill folder:

- `reports/YYYY-MM-DD.md` — immutable refresh snapshot
- `reports/latest.md` — latest readable report
- `data/latest.json` — latest structured dataset

Create these directories only when a refresh is actually saved.
