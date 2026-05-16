<div align="center">

# 🤖 AI 早报 Skill

**为 Claude Code / OpenClaw 设计的 AI 晨报技能**

**中文 AI 圈 + 国际动态 双轨聚合 · 朋友圈/公众号格式直出**

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude_Code-Skill-blueviolet)](https://claude.ai/code)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-compatible-orange)](https://openclaw.ai)
![GitHub stars](https://img.shields.io/github/stars/EA-Studio-SHARK/ai-morning-brief?style=social)

> 每天一条命令，自动抓取 15+ 来源，生成可直接发布的 AI 早报  
> 覆盖 Anthropic · OpenAI · Google · Meta · DeepSeek · Qwen · Kimi · GLM

**⭐ 如果觉得有用，请给个 Star！你的支持是持续更新的动力**

</div>

---

## 为什么需要这个 Skill？

**同类竞品的问题：**
- 现有 AI news skill 只覆盖英文来源（Anthropic/OpenAI/HuggingFace），**完全忽略中文 AI 圈**
- DeepSeek 发新模型、Qwen 更新、Kimi 上新功能，这些对中国用户最重要的事，别的早报 skill 根本抓不到
- 生成的内容是英文，还需要自己翻译再发布

**AI 早报 Skill 做到：**
- ✅ 国际 + 中文 AI 圈双轨监控
- ✅ 输出简体中文，直接可发
- ✅ 自带**朋友圈版**（≤120字，可直接复制）
- ✅ 自带**今日洞察**，不只是堆砌新闻
- ✅ 与 `china-hot-mcp` 联动，可叠加当日热搜背景

---

## 安装

### Claude Code

```bash
git clone https://github.com/EA-Studio-SHARK/ai-morning-brief.git ~/.claude/skills/ai-morning-brief
```

### OpenClaw

```bash
npx skills add https://github.com/EA-Studio-SHARK/ai-morning-brief --skill ai-morning-brief
```

---

## 使用方式

安装后，在 Claude Code 或 OpenClaw 中直接输入：

```
/skill ai-morning-brief
```

或者更具体地：

```
帮我生成今天的 AI 早报，重点关注中文 AI 圈的动态
```

```
生成今日 AI 早报，我要发公众号，需要 800 字左右的版本
```

```
生成今天的 AI 早报，结合当前微博热搜分析一下 AI 话题的讨论热度
```

---

## 输出示例

```
# 🤖 AI 早报 | 2026-05-16（周六）

> 📌 今日一句话：DeepSeek-V4 今日发布，多项基准超越 GPT-5，开源权重同步放出

---

## 🌍 国际动态

🔴 **Anthropic** Claude Code 新增 Skills Marketplace 官方目录，支持一键安装社区技能
🟡 **HuggingFace** 发布 SmolLM3，专为端侧推理优化，1B 参数跑赢此前 3B 模型
⚪ **OpenAI** GPT-4o 更新图像理解能力，支持更长的多图对话

---

## 🇨🇳 中文圈

🔴 **DeepSeek** V4 正式发布，数学/代码能力全面升级，API 同步开放
🟡 **Qwen** Qwen3-235B 开源，支持 MoE 架构，推理成本降低 60%
⚪ **量子位** 报道：国内多家大厂 Agent 产品进入公测，应用层竞争白热化

---

## ⭐ GitHub 今日趋势（AI）

`deepseek-v4` — DeepSeek 官方 V4 模型权重 ⭐ 8.2k
`qwen3` — 通义千问 Qwen3 系列 ⭐ 5.1k
`claude-code-skills` — Claude Code 技能市场 ⭐ 1.2k

---

## 💡 今日洞察

今日最值得关注的是 DeepSeek 和 Qwen 在同一天的双重发布。这并非巧合——
中国 AI 实验室正在形成类似美国大厂"卡位"发布的节奏。
对开发者而言，两者都值得立即评测，重点关注推理成本和 API 稳定性。

---

**朋友圈版 ↓**

🤖 AI早报 05/16

• DeepSeek V4发布，开源，超GPT-5
• Qwen3 235B开放，推理省60%
• HuggingFace 1B模型打败3B
• Claude Code 技能市场上线

👉 完整早报见评论区
```

---

## 覆盖数据源

### 国际
| 来源 | 类型 |
|------|------|
| Anthropic Blog | RSS |
| OpenAI Blog | RSS |
| Google AI Blog | RSS |
| HuggingFace Blog | RSS |
| Meta AI Blog | RSS |
| The Decoder | RSS |
| TLDR AI | 抓取 |
| Hacker News | API |
| Claude Code Changelog | RSS |

### 中文
| 来源 | 类型 |
|------|------|
| 机器之心 | 抓取 |
| 量子位 | 抓取 |
| 极客公园 | 抓取 |
| DeepSeek GitHub | Release 监控 |
| QwenLM GitHub | Release 监控 |
| THUDM (GLM) GitHub | 活动监控 |

---

## 与 china-hot-mcp 联动

配合 [china-hot-mcp](https://github.com/EA-Studio-SHARK/china-hot-mcp) 使用，可在早报中自动叠加当日微博/知乎对 AI 话题的讨论热度：

```json
{
  "mcpServers": {
    "china-hot": {
      "command": "china-hot-mcp"
    }
  }
}
```

安装后直接说：「生成今日 AI 早报，并告诉我 AI 相关话题今天在知乎/微博的热度」

---

## 适合谁用

- 📱 **AI 公众号运营者** — 每天一键生成早报内容，省去手动整理时间
- 👨‍💻 **开发者 / 研究者** — 快速了解昨晚发生了什么，不错过重要更新
- 📊 **内容创作者** — 早报作为选题参考，找今天最值得展开的话题
- 🏢 **团队 Newsletter** — 给团队发 AI 早报，保持技术敏锐度

---

## 相关项目

- [china-hot-mcp](https://github.com/EA-Studio-SHARK/china-hot-mcp) — 中国热搜 MCP，可与本 Skill 联动
- [awesome-mcp-zh](https://github.com/EA-Studio-SHARK/awesome-mcp-zh) — MCP 中国开发者实战工具包

---

## 联系

- 📬 Telegram：[@ExploreAllStudio](https://t.me/ExploreAllStudio)
- 💼 定制 AI 早报系统 / 自动化发布工作流：欢迎合作

---

<div align="center">

**⭐ 如果觉得有用，请给个 Star！你的支持是持续更新的动力**

</div>
