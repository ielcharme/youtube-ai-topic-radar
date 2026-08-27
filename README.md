# YouTube AI Topic Radar

A Codex skill for tracking recent AI topics across a curated multilingual set of YouTube creators and turning the findings into source-backed, original video-planning references.

一个用于追踪 YouTube AI 博主近期话题、发现跨语言趋势，并生成原创视频选题参考的 Codex Skill。

## Coverage

- 50 curated creators: 20 English, 10 French, 10 German, and 10 Spanish
- Biweekly refresh workflow
- Source links, publication dates, Chinese title translations, topic clustering, and opportunity scoring
- Original video ideas without copying scripts, titles, thumbnails, or distinctive phrasing

The current roster is maintained in [`references/creator-roster.md`](references/creator-roster.md).

## Install

Copy or clone this repository into your Codex skills directory:

```bash
git clone https://github.com/ielcharme/youtube-ai-topic-radar.git ~/.codex/skills/youtube-ai-topic-radar
```

Restart Codex after installation if the skill is not detected immediately.

## Example requests

```text
刷新过去两周这些 YouTube AI 博主发布的话题，并生成中文趋势报告。

比较英语、法语、德语和西班牙语 AI 博主最近都在讨论什么。

根据最新报告，为我提供 10 个原创视频选题、标题方向和开场钩子。
```

## Output

When a refresh is saved, the skill uses:

- `reports/YYYY-MM-DD.md` for dated snapshots
- `reports/latest.md` for the latest readable report
- `data/latest.json` for structured data

Generated reports and datasets are ignored by Git by default.

## Safety boundary

This skill uses public information for research. It does not automatically publish content, interact with creators, bypass platform controls, or treat creator videos as primary confirmation for consequential product, pricing, policy, or technical claims.

## License

No license has been granted yet. The repository is public for inspection and personal use subject to applicable copyright law.
