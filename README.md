**English** | [中文](README.zh-CN.md)

# Translate Link Spec

An AI Agent Skill designed to automatically fetch, summarize, and translate Twitter (X) and YouTube posts/videos into a standardized, high-quality Chinese format.

## What it does

When provided with a Twitter (X) or YouTube link, this Skill directs any compatible AI Agent to output three specific sections:
1. **中文摘要 (Chinese Summary)**: A concise summary of the core insights, technical discussions, or original opinions (for YouTube, around 300 words).
2. **中文原文 (Chinese Translation)**: A natural, conversational Chinese translation of the original tweet or YouTube transcript, carefully preserving AI and technical terminology (e.g., LLM, GPU, API) in English.
3. **源链接 (Original Link)**: The original URL for reference.

## How it works

This repository contains a pure **Agent Protocol (Prompt instructions)** rather than executable code. It relies on the AI Agent's built-in web browsing or tool-calling capabilities. 
- For **Twitter (X)**, the Agent reads the page text.
- For **YouTube**, the Agent is explicitly instructed in `SKILL.md` to use Python (`youtube-transcript-api`) or CLI (`yt-dlp`) to fetch the transcript automatically.
Once the content is retrieved, the Agent utilizes its LLM capabilities to perform the summarization and translation based on the rules defined in this repository.

## Installation & Usage

Because this is a standard Skill/Prompt repository, it works with any modern AI coding assistant or Agent (e.g., Trae, Cursor, Windsurf, Claude Code, OpenClaw).

1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com/your-username/translate-link-spec.git
   ```
2. Open the cloned folder in your preferred AI IDE (Trae, Cursor, Windsurf) or navigate to it using your CLI Agent.
3. Simply drop a Twitter or YouTube link into the chat and say:
   > "Translate this link" or "Summarize this tweet/video"
4. The Agent will automatically read `SKILL.md` and the rules in the `prompts/` directory to generate the standardized output.

## Customization

You can easily tweak the behavior by modifying the markdown files in the `prompts/` directory:
- `prompts/summarize-tweets.md` — Controls how Twitter summaries are generated.
- `prompts/summarize-youtube.md` — Controls how YouTube video summaries are generated.
- `prompts/translate.md` — Controls the translation style, tone, and specific terminology rules.

## Requirements

- An AI Agent with web browsing capabilities or code execution (to read the link or fetch transcripts). If the Agent cannot access the content, you can manually paste the text/transcript.
- No API keys are required for the skill itself, it relies entirely on your Agent's LLM.

## License

MIT
