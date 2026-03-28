[English](README.md) | **中文**

# Translate Link Spec (推特与YouTube翻译摘要技能)

这是一个专为 AI Agent 设计的 Skill，用于自动抓取、总结并将推特（X）帖子和 YouTube 视频内容翻译为标准的高质量中文格式。

## 核心功能

当提供一个推特（X）或 YouTube 链接时，此 Skill 会引导任何兼容的 AI Agent 输出以下三个特定部分：
1. **中文摘要**：提取核心洞察、技术讨论或独立见解（对于 YouTube 视频，生成约 300 字的结构化摘要）。
2. **中文原文**：将原推文或 YouTube 视频字幕翻译为自然、口语化的中文（像懂行的朋友聊天），同时严格保留 AI 和技术领域的英文术语（如 LLM, GPU, API 等）。
3. **源链接**：提供原始 URL 以便溯源。

## 工作原理

这个仓库包含的是纯粹的 **Agent 协议（Prompt 指令）**，而不是可执行的代码。它依赖于 AI Agent 内置的网页浏览或工具调用能力（例如使用 Python `youtube-transcript-api` 获取 YouTube 字幕）来读取内容，并利用 Agent 自身的 LLM（大语言模型）能力，基于本仓库中定义的规则来执行摘要和翻译。

## 安装与使用

因为这是一个标准的 Skill/Prompt 仓库，它适用于任何现代的 AI 编程助手或 Agent（例如 Trae, Cursor, Windsurf, Claude Code, OpenClaw）。

1. 将此仓库克隆到本地：
   ```bash
   git clone https://github.com/your-username/translate-link-spec.git
   ```
2. 在你喜欢的 AI IDE（Trae, Cursor, Windsurf）中打开这个克隆的文件夹，或者在 CLI Agent 中导航到该目录。
3. 直接在聊天框里丢一个推特或 YouTube 链接，并说：
   > "翻译这个链接" 或 "总结这篇推文/视频"
4. Agent 会自动读取 `SKILL.md` 以及 `prompts/` 目录下的规则，并生成标准化的输出。

## 自定义规则

你可以通过修改 `prompts/` 目录下的 markdown 文件来轻松调整它的行为：
- `prompts/summarize-tweets.md` — 控制推特摘要的生成方式（长度、关注点、如何处理长推文）。
- `prompts/summarize-youtube.md` — 控制 YouTube 视频摘要的生成方式。
- `prompts/translate.md` — 控制翻译风格、语气以及特定的术语保留规则。

## 运行要求

- 一个具备**网页浏览或代码执行能力**的 AI Agent（用于读取链接内容或获取字幕）。如果 Agent 无法访问网络或提取字幕，你可以手动将文本连同链接一起粘贴给它。
- 该 Skill 本身**不需要任何 API Key**，完全依赖你所使用的 Agent 的 LLM 能力。

## 许可证

MIT
