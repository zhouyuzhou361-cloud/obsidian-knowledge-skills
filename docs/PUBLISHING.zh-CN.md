# 🚀 在 GitHub 新建仓库并发布

本指南采用网页操作，不需要 Git、命令行、Claude Code 或访问令牌。当前项目的目标是 `zhouyuzhou361-cloud/obsidian-knowledge-skills`；其他使用者替换成自己的账号和仓库名。

## 1. 准备发布文件

解压准备好的 `obsidian-knowledge-skills.zip`，打开里面的 `obsidian-knowledge-skills` 文件夹。仓库根目录应包含：

```text
README.md
LICENSE
SECURITY.md
.gitignore
.gitattributes
obsidian-skills.example.yaml
skills/
standalone/
docs/
```

上传的是上面这些内容，不要把外层文件夹再套进仓库。否则 README 会被放到子目录，仓库首页看不到项目介绍。也不要只上传 ZIP，那样读者无法直接浏览技能。

本发布包不含个人原始笔记。只选这些发布文件；自己的 `obsidian-skills.yaml`、Cookie、Token、账户数据库和材料原件留在本地。网页上传时要自己检查文件清单，`.gitignore` 不会过滤手动选中的文件。

## 2. 登录并新建仓库

1. 登录 [GitHub](https://github.com)，确认当前账号是 `zhouyuzhou361-cloud`。
2. 打开 [New repository](https://github.com/new)，也可以点右上角 `+ → New repository`。
3. 按下表填写。界面语言不同，按钮文字可能略有区别。

| 项目 | 填写/选择 |
|------|-----------|
| Owner | zhouyuzhou361-cloud |
| Repository name | obsidian-knowledge-skills |
| Description | 多模型通用的个人知识库技能：整理视频、PDF、文章与流媒体，维护导航并生成 AI 行业日报，支持个性化配置。 |
| Visibility | Public |
| Add a README file | 开启，便于进入正常文件页面 |
| Add .gitignore | None，稍后上传发布包里的版本 |
| Choose a license | None，稍后上传发布包里已有的 MIT LICENSE |

点击 **Create repository**。成功后地址应为：

`https://github.com/zhouyuzhou361-cloud/obsidian-knowledge-skills`

同名仓库已经存在时，打开它检查内容；不要为重试而删除它。若已有自己需要保留的文件，先确认本次上传不会覆盖。

以上操作依据 [GitHub：创建新仓库](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository)。

## 3. 上传文件

1. 在新仓库的 **Code** 页面，点击 **Add file → Upload files**。
2. 从本地解压文件夹中，将 `skills/`、`standalone/`、`docs/` 三个目录及六个根目录文件拖进上传区域。拖目录可以保留其内部层级。
3. 等待上传完成，检查列表中的路径：应直接出现 `README.md` 与 `skills/knowledge-ingest/SKILL.md`，不能变成 `obsidian-knowledge-skills/README.md`。
4. 根目录现有的初始化 README 可以由这次发布版 README 替换。确认 LICENSE、SECURITY.md、配置模板和两份点开头的文件也选中。
5. 下方提交说明填写：`Publish multi-source knowledge skills with personalized configuration`。
6. 这是你自己的全新仓库时，选择直接提交到默认分支（通常为 main）；如界面只能提出更改，则按提示创建并合并自己的 Pull Request。
7. 点击 **Commit changes** 或界面提供的 **Propose changes** 完成提交；若创建了 Pull Request，合并后才会出现在默认分支。

网页支持上传文件和目录，操作细节见 [GitHub：添加文件到仓库](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository)。

## 4. 检查发布结果

返回仓库 Code 首页，逐项检查：

- 首页直接显示项目介绍、功能特点、快速开始和配置说明。
- `standalone/` 中有三个可直接给 AI 使用的完整文件。
- `skills/` 中有 knowledge-ingest、obsidian-update-home、ai-industry-daily，且各自资源目录完整。
- README 的单文件版、个人配置、使用示例和发布指南链接都能打开。
- 根目录有 LICENSE，内容是 MIT，署名为你的 GitHub 账号。
- 文件清单没有私人配置、材料原件和认证信息。

随后点 **Code → Download ZIP**，解压检查目录。这是验证读者能否拿到完整发布包的方法；参见 [GitHub：下载源码压缩包](https://docs.github.com/en/repositories/working-with-files/using-files/downloading-source-code-archives)。

## 5. 填写仓库简介

在首页右侧 **About** 的编辑入口中，保存简短描述，并可添加与你项目有关的 Topics，例如：

```text
obsidian
ai-skills
knowledge-management
personal-knowledge-base
markdown
```

这些用于帮助读者发现项目，无需开启 GitHub Pages；技能文件发布到公开仓库后即可浏览和下载。

## 6. 将来更新

修改自己的发布版文件后，用同样的 **Add file → Upload files** 上传同一路径的新版本，并填写本次变更说明。保留相同层级，先检查将被替换的文件。

标准目录版发生变化时，重新生成对应单文件版，避免两者流程不一致。个人配置和原始知识材料继续留在本地。

## 7. 如果由 AI 助手继续上传

新库建立后，将仓库链接发给你使用的文件/代码助手，并明确“把已准备的发布包上传到这个公开仓库”。需要该助手的 GitHub 连接有这个仓库的写入权限；只开放特定仓库的连接可能需要你在正常授权界面选中新增仓库。

不需要把 GitHub 密码、Token 或 Cookie 发送到聊天。助手应先检查已有文件和默认分支，再上传并核对最终清单。
