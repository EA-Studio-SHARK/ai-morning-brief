# AI 早报 Skill

Generate a bilingual AI morning briefing covering both international and Chinese AI ecosystem — formatted for sharing on WeChat, Zhihu, or as a daily digest.

## When to use this skill

- You want a daily summary of AI news without manually checking 10+ sources
- You need to create an AI早报 for your WeChat account, Zhihu column, or team newsletter
- You want to know what happened in the Chinese AI space (DeepSeek, Qwen, Kimi, GLM) alongside international news
- You're a content creator who publishes daily AI briefings

## Workflow

### Step 1 — Fetch international AI news

Fetch and parse these sources. Focus on the last 24 hours only:

**Lab blogs (RSS):**
- Anthropic News: `https://raw.githubusercontent.com/Olshansk/rss-feeds/main/feeds/feed_anthropic_news.xml`
- OpenAI Blog: `https://openai.com/blog/rss.xml`
- Google AI Blog: `https://developers.googleblog.com/feeds/posts/default`
- HuggingFace Blog: `https://huggingface.co/blog/feed.xml`
- Meta AI: `https://ai.meta.com/blog/feed/`
- Claude Code Changelog: `https://code.claude.com/docs/en/changelog/rss.xml`

**Aggregators:**
- The Decoder: `https://the-decoder.com/feed/`
- TLDR AI: `https://tldr.tech/ai` (fetch page, extract today's items)
- Hacker News: `https://hacker-news.firebaseio.com/v0/topstories.json` (fetch top 30, filter AI-related by title)

### Step 2 — Fetch Chinese AI news

**Chinese media (fetch homepage or RSS):**
- 机器之心: `https://www.jiqizhixin.com/` (fetch, extract today's headlines)
- 量子位: `https://www.qbitai.com/` (fetch, extract today's headlines)
- 极客公园: `https://www.geekpark.net/` (fetch, extract AI section)

**Model providers (check for updates):**
- DeepSeek: `https://api-docs.deepseek.com/news/` and `https://github.com/deepseek-ai` (recent releases)
- Qwen: `https://github.com/QwenLM` (recent releases/tags)
- Kimi: `https://kimi.moonshot.cn/` (announcement page if accessible)
- GLM/智谱: `https://github.com/THUDM` (recent activity)

**GitHub Trending (AI):**
- Fetch `https://github.com/trending/python?since=daily` and filter repos with AI/LLM/agent tags
- Note top 3 fastest-rising AI repos

### Step 3 — Classify and prioritize

Group findings into these categories, mark each item with importance:
- 🔴 **重大** — New model release, major product launch, significant research breakthrough
- 🟡 **重要** — Product updates, notable papers, significant funding/acquisition
- ⚪ **动态** — Minor updates, community discussions, tooling changes

Discard duplicates and items older than 24 hours.

### Step 4 — Generate the briefing

Output the following structure exactly:

```
# 🤖 AI 早报 | {TODAY_DATE}（{WEEKDAY}）

> 📌 **今日一句话**：{One sentence capturing the single most important AI development today}

---

## 🌍 国际动态

{List 3-6 items, format: 🔴/🟡/⚪ **[来源]** [标题/事件] — [1-2句中文说明影响或重点]}

---

## 🇨🇳 中文圈

{List 3-5 items covering Chinese AI labs and Chinese tech media, same format}

---

## ⭐ GitHub 今日趋势（AI）

{Top 3 AI repos trending today, format: `repo-name` — [描述] ⭐{stars}}

---

## 💡 今日洞察

{2-3 sentences: Claude's synthesis of what today's news means for the AI field. Be specific, not generic.}

---

**朋友圈版 ↓**（可直接复制）

🤖 AI早报 {SHORT_DATE}

{3-4 bullet points of the most shareable items, each ≤25 characters, casual tone}

👉 完整早报见评论区
```

### Step 5 — Quality check before output

- Verify all dates are actually today (not yesterday or older)
- Confirm Chinese lab section has at least 1 item (if none found, note "今日暂无中文圈重大动态")
- Ensure 朋友圈版 is ≤ 120 characters total
- If fetch fails for any source, silently skip it and use remaining sources

## Output format

Markdown. Ready to paste into WeChat editor, Zhihu, or Notion.

## Notes

- Always write in Simplified Chinese (简体中文) except for proper nouns (model names, company names keep original)
- Use concrete facts, not vague descriptions. "Claude 4.5 发布，支持 200K context" not "Anthropic 有新动态"
- If a Chinese lab releases something significant, lead with it — don't bury it in the middle
- This skill pairs well with `china-hot-mcp` for adding trending topic context
