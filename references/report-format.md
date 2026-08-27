# Refresh report and dataset format

## Topic classification

Assign every video one or more normalized labels:

- frontier models and releases
- AI tools and tutorials
- agents and automation
- AI coding and engineering
- creative AI: image, video, audio, design
- productivity and workplace
- business, monetization, and entrepreneurship
- marketing, ecommerce, and creator economy
- research and education
- policy, safety, privacy, and social impact
- other

Add narrower free-form tags when they improve retrieval, such as `Claude Code`, `n8n`, `MCP`, `EU AI Act`, `AI video`, or `local models`.

## Opportunity score

Score each proposed topic from 0 to 25:

- **Recency (0-5):** how recently the evidence appeared.
- **Cross-channel signal (0-5):** independent creators or languages covering the same underlying development.
- **Audience usefulness (0-5):** practical value for people using AI for work, business, marketing, ecommerce, or content creation.
- **Production feasibility (0-5):** whether an original, demonstrable video can be produced with accessible evidence and tools.
- **Localization gap (0-5):** opportunity to add a Chinese, French, German, Spanish, or European-market angle that current videos lack.

Do not inflate a score because a creator is large. A single-source topic can still rank if it is unusually useful, but label it `emerging` rather than `cross-channel`.

## Markdown report

Write the report in Chinese with this order:

1. **Refresh metadata:** observation date, time window, roster size, channels checked, channels unavailable, videos collected.
2. **Executive summary:** no more than eight concise findings.
3. **Top topic opportunities:** ranked table with score, topic, evidence count, languages, why it matters, and source links.
4. **Cross-language comparison:** what English, French, German, and Spanish creators emphasize differently.
5. **Creator activity:** one compact row per creator with upload count, major topics, strongest reference video, and status.
6. **Original video briefs:** five to ten ideas. For each include audience, original angle, hook, working Chinese title, format, proof/demo needed, source inspiration, and copying risks to avoid.
7. **Watch next:** emerging one-source signals and claims that need primary-source verification.
8. **Coverage gaps:** inaccessible channels or missing metadata.

## Structured dataset

Save `data/latest.json` with this top-level shape:

```json
{
  "observed_at": "YYYY-MM-DDTHH:MM:SS+TZ",
  "window_start": "YYYY-MM-DD",
  "window_end": "YYYY-MM-DD",
  "roster_size": 50,
  "channels_checked": 0,
  "channels_unavailable": [],
  "videos": [],
  "topic_clusters": [],
  "video_briefs": []
}
```

Each video should include:

```json
{
  "creator": "",
  "language": "en|fr|de|es",
  "title_original": "",
  "title_zh": "",
  "published_at": "YYYY-MM-DD",
  "url": "",
  "views_observed": null,
  "format": "short|long|live|podcast|unknown",
  "labels": [],
  "narrow_tags": [],
  "sponsorship_visible": null,
  "evidence_note": ""
}
```

Use `null`, not guesses, for unavailable fields. Keep only public metadata and short analytical notes; do not store transcripts or copied scripts.
