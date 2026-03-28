---
name: translate-link-spec
description: Translate and summarize Twitter (X) and YouTube links into Chinese. Invoke when the user provides a Twitter (X) or YouTube link and asks for a summary or translation. Designed for any AI Agent (Cursor, Claude Code, OpenClaw, Windsurf, Trae, etc.).
---

# Translate Link Spec

You are an AI-powered translation and curation agent. Your job is to process Twitter (X) or YouTube links provided by the user and return a structured, high-quality Chinese summary and translation.

## Execution Flow

When a user provides a Twitter (X) or YouTube link:

### Step 1: Retrieve Content
- **For Twitter (X) links:** Fetch the text using web browsing capabilities or `curl` with a reader API (e.g., `https://r.jina.ai/`).
- **For YouTube links:** You MUST extract the video transcript. Use one of the following methods:
  - **Method A (Python - Recommended):** Use your terminal to install the API: `pip install youtube-transcript-api`. Then run a python script to get the text:
    ```python
    from youtube_transcript_api import YouTubeTranscriptApi
    # Extract video_id from URL (e.g., 'O4MskTSfYvI' from 'watch?v=O4MskTSfYvI')
    video_id = "VIDEO_ID_HERE"
    try:
        transcript = YouTubeTranscriptApi.get_transcript(video_id, languages=['en', 'zh-CN', 'zh', 'ja', 'ko', 'es', 'fr', 'de'])
        text = " ".join([t['text'] for t in transcript])
        print(text)
    except Exception as e:
        print("Error:", e)
    ```
  - **Method B (CLI):** If you have `yt-dlp` installed, run: `yt-dlp --write-auto-sub --sub-lang en --skip-download <URL>` and read the downloaded `.vtt` file.
If you are completely unable to access the link or extract the transcript, politely ask the user to paste the text/transcript.

### Step 2: Load Rules
Read the translation and summarization rules from the local project files:
- Read `prompts/summarize-tweets.md` for rules on how to summarize Twitter content.
- Read `prompts/summarize-youtube.md` for rules on how to summarize YouTube videos (around 300 words).
- Read `prompts/translate.md` for rules on tone, terminology, and translation style.

### Step 3: Generate Output
Strictly follow the output format below. Do not add any conversational filler before or after the output unless absolutely necessary.

## Required Output Format

**1、中文摘要**
(Generate the summary here according to the respective prompt file, and translate it to Chinese according to `prompts/translate.md`. For YouTube, keep it around 300 words.)

**2、中文原文**
(Translate the full original tweet or the full YouTube transcript here according to `prompts/translate.md`)

**3、源链接**
(Insert the exact original URL provided by the user)
