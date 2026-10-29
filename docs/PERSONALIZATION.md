# ⚙️ 个人配置指南

三个技能共享同一份个人配置，但不要求你使用相同模型、目录或笔记风格。配置由 AI 在会话中读取，不是应用插件，也不会修改模型平台设置。仅解析已知数据字段；未知指令键、YAML 自定义标签和脚本表达式不执行。配置文件本身不授予文件、联网或对外传输权限。

## 方式一：直接用自然语言

不想编辑 YAML，可以直接发送：

```text
请按以下偏好使用这三个技能：
- 我用普通 AI 聊天，没有知识库文件读写权限，请直接返回 Markdown。
- 主要整理视频、PDF 和文章，不使用 Clippings 收件箱。
- 输出中文、深度笔记，不用 emoji，也不要双语标题。
- 分类沿用我随后提供的目录，不新建默认分类。
- 日报只关注开源模型和 AI 产品，只使用官方公告，不抓 X 或 YouTube。
- 日期按我指定的时区处理。
```

本次明确要求优先；同次会话沿用已确认偏好，新会话需重新提供，除非你使用的宿主有相应持久配置机制。

## 方式二：提供 YAML 文件

1. 复制根目录的 [配置示例](../obsidian-skills.example.yaml)。
2. 改名 `obsidian-skills.yaml`，按自己的情况修改。
3. 普通聊天：上传它，或粘贴文件内容，并要求 AI 先读取配置。
4. 文件助手：放在授权知识库根目录，并告诉助手位置。
5. 首次让 AI 简述生效配置，确认后开始任务。

这份个人文件可能包含学习目标、私有目录和关注主题，默认留在本地，不随技能公开。它已列入 `.gitignore`。手动网页上传文件时仍需自己排除，`.gitignore` 不会替你拦截网页选择的文件。

## 可调整的内容

| 配置段 | 作用 | 示例 |
|--------|------|------|
| profile | 学习目标、读者、时区 | 备考复习、研究梳理、工作实践 |
| execution | 仅聊天或允许保存 | mode: chat / files / auto |
| paths | 输入目录、知识目录、首页、日报、处理记录 | input_dirs 为空也能处理文件与链接 |
| writing | 语言、格式、深度、标题、emoji、引文翻译、命名 | concise / standard / deep |
| writing.field_map | 已有 frontmatter 的实际属性名 | summary 可以映射成 abstract |
| categories | 分类与关键词映射 | 不填时沿用已有目录 |
| ingest | 新分类门槛、关联数、反向链接、可选剪藏标签 | 不要求每份素材都带标签 |
| navigation | 普通 Markdown / Dataview、候选数、最近更新数 | plain-markdown 免插件 |
| daily | 观察天数、主题、渠道、语言、收录上限 | 只要官方 Web 来源也可 |

execution.mode 为 chat 时只返回文本；files 也需要宿主具备工具和用户授权，配置不会自行授予权限。auto 按实际工具决定并说明采用方式。

所有相对路径相对于 paths.root 或本次明确指定的知识库根目录。未知路径不猜；配置里出现授权范围外路径时先取得实际访问授权。输入文件、PDF 和音视频原件默认保留。

writing.format 为 plain-markdown 时用普通标题、表格和链接；obsidian-markdown 可用 wikilink、frontmatter 和 callout。格式选项与 Dataview 是两回事：普通 Obsidian 笔记也可以不用 Dataview。

writing.field_map 修改后，导航中的查询字段也要修改。difficulty_values 修改后，同步导航分组条件；navigation.marker 和 filename_pattern 应一致，关闭 emoji 时可同时改成不带 emoji 的命名。

## 三种常见配置

### A. 普通聊天 + 多源材料

以下为覆盖项，其余沿用默认或已有约定：

```yaml
execution:
  mode: chat
writing:
  language: zh-CN
  format: plain-markdown
  depth: deep
  bilingual_headings: false
  emoji: false
navigation:
  mode: plain-markdown
  filename_pattern: "{category} 导航.md"
  marker: " 导航"
```

提供视频字幕、PDF 或文章正文后，AI 返回笔记和建议路径，你再保存。AI 不会因此获得电脑文件权限。

### B. 自己的 Obsidian 知识库

```yaml
execution:
  mode: files
paths:
  root: null
  knowledge_dir: "我的笔记"
  home_file: "Home.md"
  daily_dir: "报告/AI日报"
writing:
  format: obsidian-markdown
  depth: deep
  field_map:
    summary: abstract
    difficulty: level
navigation:
  mode: dataview
```

先向助手指定真实根目录。上述示例只列改动项，其他字段沿用已有约定；使用 Dataview 前需你已安装并启用所需能力，不由技能自动改设置。

### C. 只关注官方 AI 新闻

```yaml
profile:
  timezone: "Asia/Shanghai"
daily:
  lookback_days: 1
  topics: ["开源模型", "AI产品"]
  sources: ["Web"]
  social_languages: []
  max_items: 8
  include_watchlist: true
```

可以再明确“Web 只采用官方公告与项目发布记录”。没有联网时提供相关公告正文，报告会标注未独立联网核验。

## 配置不能代替实际能力

技能是可复用文本工作流，可交给不同 AI 模型理解执行；它本身不提供联网、OCR、语音转录、文件访问或后台监听。宿主不支持这些能力时，使用可读的材料与聊天输出方式；来源缺失时说明缺口，不编造结果。
