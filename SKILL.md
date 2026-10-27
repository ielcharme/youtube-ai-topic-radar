---
name: youtube-ai-topic-radar
description: Monitor multilingual YouTube creators and selected public research/product newsletters for globally relevant frontier AI developments, then turn recent topics into source-backed, original video references. Use for biweekly scans, international AI product and research trends, English/French/German/Spanish comparisons, roster maintenance, or video ideation. Do not use to copy or automatically publish content.
---

# YouTube AI Topic Radar

Track what selected AI creators are publishing about internationally relevant AI products and frontier developments, identify useful patterns across languages, and convert the evidence into original video directions. Write the analysis in Chinese, but do not make China-specific use cases or localization the default editorial angle.

## Required resources

- Always read [references/creator-roster.md](references/creator-roster.md) before scanning channels or changing the watchlist.
- Read [references/newsletter-watchlist.md](references/newsletter-watchlist.md) before a refresh or when changing supplementary sources.
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
6. Use multi-label classification. Cover frontier model releases and evaluations, multimodal creation, agents and coding, open models, AI research, robotics, safety and other internationally discussed developments. Track the actual products in the uploads, including Meta AI/Llama, Gemini, Grok, 即梦/Jimeng, and other relevant tools when evidence supports them; this is an illustrative watchlist, not a fixed quota or a reason to invent coverage. Do not exclude a product because of its company or country of origin; verify its actual regional availability when that matters to a proposed demo.
7. Rank topic opportunities using the scoring method in the report reference. Give priority to globally significant, recent, independently covered developments and original demonstrations. Count distinct creators and languages rather than treating repeated Shorts from one channel as broad momentum. If a major product or development has no qualifying video in this roster/window, mark it as a coverage gap and, where useful, cite an official source for context; do not present it as a creator trend.
8. Scan the public archives in the newsletter watchlist over the same window. Include only dated, substantive AI items; record them separately from creator videos. A research article or vendor release note is context, not independent creator momentum. Mark inaccessible archives `unavailable`.
9. Produce the Chinese report and machine-readable dataset described in the report reference. Keep original-language titles beside translations.
10. When file writes are available, save an immutable dated report and replace the latest report and dataset. If a write fails, still return the report and identify the exact unavailable boundary.

## Evidence rules

- Link every included video to its source and record the publication date.
- Treat subscriber counts, view counts, sponsorship status, and upload frequency as time-sensitive. Add an observation date and never invent missing values.
- Separate creator claims, observed facts, and analysis. Note sponsorship or affiliate disclosure when visible.
- Use other creators as signals and references, not as factual confirmation of AI product claims. Verify consequential product, policy, pricing, or technical claims against primary sources before recommending them as facts.
- Make clear whether a finding comes from monitored creator videos, an official announcement, or your own synthesis. Never infer worldwide availability or comparative superiority from a launch headline.
- Use public newsletter archives only. Never put private email content, message IDs, recipient details, or tracking links in reports or this repository.

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
