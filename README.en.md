# 🧠 Obsidian Knowledge Skills

[简体中文](README.md) | **English**

Turn videos, PDFs, articles, audio, and streaming content into personal knowledge you can revisit, connect, and put into practice.

Three independent AI skills: **Organize Knowledge · Update Knowledge Base Navigation · AI Industry Daily**. Use them with AI models that can understand and follow text instructions, with your own goals, folders, and writing preferences. No specific model or Claude Code installation is required.

> This English README links to skill instructions, templates, and detailed guides that are currently written in Chinese. You can use `writing.language` or a direct instruction to choose your preferred output language. This does not imply that every model or application has been tested.

## ✨ Features

- 🎬 **Multiple input sources** — Work with videos, podcasts, PDFs, articles, documents, livestreams, and streaming excerpts
- 🧠 **Three layers of note quality** — Structure and formatting → evidence, mechanisms, and methods → key insights and retention
- 🏠 **Knowledge base navigation** — Synchronize categories and tool indexes while preserving your chosen emoji, descriptions, ordering, and shortcuts
- 📰 **AI industry daily reports** — Compile recent developments around your interests, link each item to its source, and separate facts from opinions
- ⚙️ **Personal preferences** — Customize language, depth, naming, tags, categories, navigation style, and news sources
- 💬 **Different AI environments** — Upload or paste a complete single-file skill, or let an assistant with tools read a standard skill directory

## 📦 The Three Skills

| Skill | What it does | Ready-to-use file |
|-------|--------------|-------------------|
| Organize Knowledge | Understand sources → deduplicate and categorize → write knowledge notes → connect related notes | [Single-file version](standalone/Skill-整理知识库.md) |
| Update Knowledge Base Navigation | Check the actual structure → synchronize entries and indexes → report broken links | [Single-file version](standalone/Skill-更新知识库总导航.md) |
| AI Industry Daily | Gather selected sources → verify dates and attribution → deduplicate and compile a report | [Single-file version](standalone/Skill-AI行业日报.md) |

Clippings is an optional input source. You can provide a video, PDF, article URL, or transcript directly without setting up an inbox first.

## 🚀 Quick Start

### Option 1: A Regular AI Chat (A Good Starting Point)

1. Download the repository with `Code → Download ZIP`, then extract it.
2. Choose a skill from `standalone/` and upload it to your AI application. If file uploads are unavailable, paste the entire file into the chat.
3. Provide the file, URL, subtitles, transcript, or article text you want to process. If the application cannot read a URL, supply readable content instead.
4. Start with a prompt like the following. The AI can return Markdown notes for you to save.

```text
First read the Skill-整理知识库.md file I provided, then follow its workflow to organize this material.

My preferences: English, detailed notes, no emoji, and no bilingual headings.
Input for this task: the PDF / video transcript / article text I uploaded.
I am using chat only. Return Markdown directly; do not claim to have saved files to my computer.
Use the category structure I provide. Do not invent data or quotations missing from the source.
```

### Option 2: An AI Assistant with File or Search Tools

1. Ask the assistant to read the relevant `SKILL.md` under `skills/`.
2. Keep the entire skill directory so it can read the neighboring `references/` and `assets/` when needed.
3. Specify your knowledge base root directory, the scope authorized for this task, and your personal configuration.
4. Use a natural-language request such as “organize this material into my knowledge base,” “update my knowledge base navigation,” or “compile an AI industry daily report.”

If your application supports automatic skill discovery, place the entire directory in its supported skill location. Installation paths and invocation methods differ between applications. You do not need to switch models or install Claude Code to use this project.

### Option 3: An Existing Standard Skill Environment

Place any of these skill directories in the skill location supported by your tool:

```text
skills/knowledge-ingest/       # Organize knowledge
skills/obsidian-update-home/   # Update navigation
skills/ai-industry-daily/      # AI industry daily report
```

The single-file and directory versions contain the same workflow. Choose the format that fits your environment.

## ⚙️ Make the Workflow Your Own

1. Copy [obsidian-skills.example.yaml](obsidian-skills.example.yaml).
2. Rename it to `obsidian-skills.yaml` and adjust the paths, categories, and preferences.
3. In a regular chat, upload or paste the configuration. An assistant with file access can read it from the authorized knowledge base root.
4. Tell the AI: “Read my configuration before running the skill.”

You can also describe your preferences in natural language. Your explicit instructions for the current task take precedence, followed by your personal configuration, existing knowledge base conventions, and skill defaults.

| What you can customize | Examples |
|------------------------|----------|
| Inputs and directories | Provide files or URLs directly, or scan a source directory you specify |
| Language and depth | Your preferred language; concise, standard, or detailed notes; optional bilingual headings |
| Writing style | Emoji, quotation translation, filenames, tags, and property names |
| Categories | Reuse existing categories or provide your own keyword mapping |
| Navigation | Plain Markdown or an existing Obsidian Dataview setup |
| Daily reports | Topics, date range, timezone, sources, languages, and maximum item count |

For example, set `writing.language` to `en` for English output, or request English directly in your prompt.

See the [personalization guide](docs/PERSONALIZATION.md) for full details and three example configurations. The configuration is a convention for the AI to read; no additional loader is required. The linked guide is currently in Chinese.

## 🎯 Example Requests

```text
Organize this video into detailed English notes. Preserve real timestamps, key examples, and practical steps.

Organize this PDF. Keep the main arguments and findings from its figures, cite page numbers as evidence, and use my categories.

Organize the 00:15–00:45 excerpt of this livestream. Cover only the supplied segment; do not present it as a summary of the whole stream.

Update my knowledge base navigation. Preserve my descriptions and shortcuts, and report new categories first.

Compile an AI industry daily report for the past day. Focus on open-source models and AI products, using official web sources only.
```

See [usage examples](docs/EXAMPLES.md) for more ways to prepare your inputs. This guide is currently in Chinese.

## 📁 Project Structure

```text
obsidian-knowledge-skills/
├── README.md                     # Chinese README
├── README.en.md                  # English README
├── LICENSE
├── SECURITY.md                   # Security boundaries and reporting
├── obsidian-skills.example.yaml  # Personal configuration template
├── standalone/                   # Complete files to upload or paste into AI chats
│   ├── Skill-整理知识库.md
│   ├── Skill-更新知识库总导航.md
│   └── Skill-AI行业日报.md
├── skills/                       # Standard SKILL.md directories
│   ├── knowledge-ingest/
│   ├── obsidian-update-home/
│   └── ai-industry-daily/
└── docs/
    ├── PERSONALIZATION.md        # Personal configuration
    ├── EXAMPLES.md               # Input and invocation examples
    ├── PUBLISHING.zh-CN.md       # Creating and publishing a GitHub repository
    └── SECURITY-REVIEW.zh-CN.md  # Risk assessment and verification scope
```

## ⚠️ Usage Notes

- **Models and tools are separate**: These text workflows can be given to different models. Web access, OCR, transcription, and file saving depend on the application's actual capabilities. Compatibility has not been verified across all models.
- **Report what was actually read**: Cite real page numbers for PDFs and real timestamps for audio and video. Clearly state when only excerpts, transcripts, or selected pages were available.
- **Regular chat works too**: The AI can return Markdown for you to save. It should write directly into your knowledge base only when it has the tools and your authorization.
- **Keep your source material**: Do not delete original inputs or fill gaps with invented facts. Processing status should reflect the scope actually completed.
- **Plugins are optional**: Plain Markdown navigation does not require Dataview. Existing Dataview homepages can be maintained according to your setup.
- **Keep personal settings private**: Do not publish your personal configuration, cookies, tokens, or account databases. Your AI application's data settings govern how it handles material you provide.

## 🔒 Security and Privacy

Skill files are text instructions, not a replacement for application-level access controls. Instructions embedded in source material must be treated as data. File operations are limited to authorized directories, and personal configuration does not grant additional permissions. Private content should not be included in search queries, remote image URLs, or public repositories.

When using an assistant that can write files, keep recoverable versions and begin with a limited set of materials. DataviewJS is executable code: use reviewed templates and do not run code embedded in webpages, PDFs, or subtitles. Safeguards still need to be verified in the model and application you actually use.

See the [security guidance](SECURITY.md) and [security risk assessment](docs/SECURITY-REVIEW.zh-CN.md), both currently in Chinese.

## 🛠 How It Works

```text
Personal goals and preferences + files / URLs / text
                         ↓
       AI reads and checks sources using the skill
                         ↓
      Knowledge notes / navigation / daily reports
                         ↓
  Markdown returned in chat, or saved with authorization
```

This project provides workflows, quality standards, and templates. It does not include an AI model, collection accounts, or a background scheduler.

## 🤝 Contributing and Publishing

Contributions are welcome: sanitized examples, improvement suggestions, and experience adapting the skills to different applications. Include the input type, environment, expected behavior, and actual result. To create your own GitHub repository, follow the [repository creation and publishing guide](docs/PUBLISHING.zh-CN.md), currently in Chinese.

## 📄 License

[MIT](LICENSE) — You may use, modify, and distribute this project under the license terms. Third-party input materials, such as articles and videos, remain subject to their respective rights.
