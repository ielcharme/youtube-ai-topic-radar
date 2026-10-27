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

Add narrower free-form tags for the actual product, model, and development discussed, such as `Gemini`, `Meta AI`, `Llama`, `Grok`, `Jimeng/即梦`, `Claude Code`, `AI video`, or `local models`. These are examples, not a list to fill without evidence.

## Editorial focus

Rank internationally relevant frontier AI developments: important model and product releases, independent evaluations, multimodal tools, coding agents, open models, AI research, robotics, safety, and widely discussed uses. Report in Chinese for readability without defaulting to a China-market, Europe-market, or localization angle. A creator's language describes the source, not the market where the topic must be applied.

For products the user is watching, include a compact coverage check: number of qualifying videos and independent creators in the window, source links, and an official source for consequential claims. If no monitored creator covered a product, write `本期名单未覆盖` rather than `没有热度`; an official announcement alone is a watch item, not evidence of creator momentum. Track other important products that emerge during each refresh rather than limiting the scan to the example names.

## Opportunity score

Score each proposed topic from 0 to 25:

- **Recency (0-5):** how recently the evidence appeared.
- **Cross-channel signal (0-5):** independent creators or languages covering the same underlying development.
- **Global relevance (0-5):** importance of the development to international AI users, builders, researchers, or creators, supported by evidence rather than brand familiarity.
- **Production feasibility (0-5):** whether an original, demonstrable video can be produced with accessible evidence and tools.
- **Original explanatory gap (0-5):** opportunity to add an independent comparison, clear mechanism, practical test, limitations, or unanswered question that the source videos leave open.

Do not inflate a score because a creator is large. A single-source topic can still rank if it is unusually useful, but label it `emerging` rather than `cross-channel`.

## Markdown report

Write the report in Chinese with this order:

1. **Refresh metadata:** observation date, time window, roster size, channels checked, channels unavailable, videos collected, supplementary newsletter sources checked and unavailable.
2. **Executive summary:** no more than eight concise findings.
3. **Top topic opportunities:** ranked table with score, topic, evidence count, independent creators, languages, why it matters globally, and source links.
4. **Frontier product coverage:** compact table of products actually discussed by monitored creators, plus important watched products with no qualifying video clearly marked `本期名单未覆盖`. Include official links where product facts are mentioned.
5. **Supplementary newsletter findings:** AI-relevant items from the public sources in `newsletter-watchlist.md`, with source type, date, title/translation, link, and relevance. Keep this section separate from YouTube trend counts; label vendor claims as first-party.
6. **Cross-language comparison:** what English, French, German, and Spanish creators emphasize differently about global AI developments.
7. **Creator activity:** one compact row per creator with upload count, major topics, strongest reference video, and status.
8. **Original video briefs:** five to ten ideas. For each include audience, original angle, hook, working Chinese title, format, proof/demo needed, source inspiration, and copying risks to avoid. Anchor each brief to monitored videos; official-only watch items stay outside the brief list until the user explicitly requests them.
9. **Watch next:** emerging one-source signals, official-only watch items, and claims that need primary-source verification.
10. **Coverage gaps:** inaccessible channels or newsletter archives, missing metadata, and major global AI topics the roster did not cover.

## Structured dataset

Save `data/latest.json` with this top-level shape:

```json
{
  "observed_at": "YYYY-MM-DDTHH:MM:SS+TZ",
  "window_start": "YYYY-MM-DD",
  "window_end": "YYYY-MM-DD",
  "roster_size": 53,
  "channels_checked": 0,
  "channels_unavailable": [],
  "videos": [],
  "newsletter_sources_checked": 0,
  "newsletter_sources_unavailable": [],
  "newsletter_items": [],
  "topic_clusters": [],
  "frontier_product_coverage": [],
  "video_briefs": []
}
```

Each `frontier_product_coverage` item should name the product/development, count qualifying videos and distinct creators, link the supporting videos, state `covered` or `not_covered_in_roster_window`, and include an official source when a product fact is stated. Zero coverage is not a statement about global popularity.

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

Each `newsletter_items` entry should contain `source`, `source_type` (`university_news|vendor_changelog|vendor_editorial`), `title_original`, `title_zh`, `published_at`, `url`, `labels`, `narrow_tags`, and a short `evidence_note`. Use the original public article or release-note URL, never an email tracking link. These entries do not count toward `videos`, `frontier_product_coverage` video totals, or independent-creator counts. Keep private inbox data out of the dataset.
