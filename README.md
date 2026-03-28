**English** | [中文](README.zh-CN.md)

# Translate Link Spec

An AI Agent Skill designed to automatically fetch, summarize, and translate Twitter (X) posts into a standardized, high-quality Chinese format.

## What it does

When provided with a Twitter (X) link, this Skill directs any compatible AI Agent to output three specific sections:
1. **帖子的中文摘要总结 (Chinese Summary)**: A concise 2-4 sentence summary of the core insights, technical discussions, or original opinions.
2. **帖子中文原文 (Chinese Translation)**: A natural, conversational Chinese translation of the original tweet, carefully preserving AI and technical terminology (e.g., LLM, GPU, API) in English.
3. **帖子原始链接 (Original Post Link)**: The original URL for reference.

## How it works

This repository contains a pure **Agent Protocol (Prompt instructions)** rather than executable code. It relies on the AI Agent's built-in web browsing or tool-calling capabilities to read the tweet, and its LLM capabilities to perform the summarization and translation based on the rules defined in this repository.

## Installation & Usage

Because this is a standard Skill/Prompt repository, it works with any modern AI coding assistant or Agent (e.g., Trae, Cursor, Windsurf, Claude Code, OpenClaw).

1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com/your-username/translate-link-spec.git
   ```
2. Open the cloned folder in your preferred AI IDE (Trae, Cursor, Windsurf) or navigate to it using your CLI Agent.
3. Simply drop a Twitter link into the chat and say:
   > "Translate this link" or "Summarize this tweet"
4. The Agent will automatically read `SKILL.md` and the rules in the `prompts/` directory to generate the standardized output.

## Customization

You can easily tweak the behavior by modifying the markdown files in the `prompts/` directory:
- `prompts/summarize-tweets.md` — Controls how the summary is generated (length, focus areas, handling threads).
- `prompts/translate.md` — Controls the translation style, tone, and specific terminology rules.

## Requirements

- An AI Agent with web browsing capabilities (to read the Twitter link). If the Agent cannot access the web, you can manually paste the tweet text along with the link.
- No API keys are required for the skill itself, it relies entirely on your Agent's LLM.

## License

MIT
