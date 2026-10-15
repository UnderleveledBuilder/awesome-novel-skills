# 参与贡献

## 收录标准

满足以下全部条件：

1. **服务小说/网文创作**：选题扫榜、拆书、设定、人物、大纲、正文、长篇记忆、审稿、去 AI 味、书名简介封面、发布、翻译出海，以及拆书要用的下载和书源工具。短剧、漫剧、影视剧本里写剧情的部分（改编、集纲、剧本、审稿）也收；只做分镜和视频提示词的见 [awesome-short-drama-skills](https://github.com/UnderleveledBuilder/awesome-short-drama-skills)。
2. **能装进 agent 使用**：标准 `SKILL.md`、Claude Code 插件，或结构清晰的提示词工作流（标 📝）。完整的写作应用只收进「相关开源应用」，门槛是 1000★；应用里附带的 SKILL.md 能单独装进 agent 用的，按 skill 收。下载、书源类工具不受这条限制，CLI、桌面工具、浏览器脚本都收；翻译类的独立应用同样按 1000★ 门槛收进「翻译 · 出海」。
3. **有说明**：README 写清楚做什么；标准 SKILL.md 目录结构视为可以直接安装。
4. **还在维护**：近 6 个月有更新，或者内容足够稳定、不需要更新。
5. **能复用**：只为某一个人或某一部作品写死、换个题材就用不上的不收。
6. **有源码**：只给 exe / 安装包、仓库里没有源码的不收；照搬别人项目再塞安装包的不收。

星数不是门槛，冷门但有独到方法的项目同样欢迎。例外是完整应用和通用英文去 AI 味工具，门槛都是 1000★，以免列表被通用工具淹没；中文去 AI 味不设门槛。

fork 和改名换皮的不收。在原版基础上加了新的 skill、模块或功能的派生版可以收，条目说明里会注明上游。

## 怎么提交

**不想动代码**：[提交 issue](../../issues/new?template=submit-skill.yml)，填仓库地址和推荐理由即可。

**直接发 PR**：

1. 在 `data/skills.toml` 对应类型的分组下追加一条（字段见下文）。
2. 本地运行（需要 Python 3.11+，无第三方依赖）：

   ```bash
   python3 scripts/refresh.py --only owner/repo   # 抓取星数、许可证等元数据
   python3 scripts/build.py                       # 重新生成 README.md 和英文版 README.en.md
   ```

   跳过这一步也可以，合并后 GitHub Actions 会自动刷新并生成。
3. 提交 PR。CI 会校验数据格式。

## 字段说明

```toml
[[skills]]
repo    = "owner/repo"            # 必填，GitHub 仓库
desc    = "一句话说清做什么"         # 必填，≤ 80 字，写具体能力，少用形容词
desc_en = "One-line English desc"  # 可选，英文版用，≤ 260 个字符；不填时英文版显示中文
group   = "pipeline"              # 必填，类型，取值见 data/taxonomy.toml [groups]
stages  = ["drafting", "memory"]  # 必填，覆盖的创作阶段，见 [stages]
format  = "skill"                 # 必填，skill / prompts / app
lang    = "zh"                    # 必填，zh / en / multi（指 skill 正文的语言）
agents  = ["claude-code"]         # 可选，仓库明确说明支持的 agent，见 [agents]
sites   = ["fanqie"]              # 可选，仓库明确说明针对的投稿平台，见 [facet.values]
install = "npx skills add ..."    # 可选，默认生成 npx skills add owner/repo
name    = "显示名"                 # 可选，默认取仓库名
tier    = "featured"              # 可选，精选；默认 listed
note    = "需要注意的地方"           # 可选，显示在简介下方
note_en = "English note"          # 可选，note 的英文版
checked = 2026-10-13              # 可选，人工核对日期（TOML 日期，不加引号）
```

`agents` 和 `sites` 只填仓库里明确写了的，不要推测。星数、许可证、最近更新时间、skill 数量由 `scripts/refresh.py` 自动抓取，不用手填。

英文版 README.en.md 的分类名和简介在 `data/taxonomy.toml` 的 `*_en` 字段，界面文字在 `scripts/build.py` 的 `UI`。PR 里不会写英文简介也没关系，维护者合并时补上。

## 收录徽章

项目被收录后，可以在自己的 README 里加上收录徽章，代码见 [README 的「收录徽章」一节](README.md#badge)。

## 不收录的项目

看过但决定不收的项目记在 `data/ignore.toml`，并写明原因，这样 `discover.py` 不会再把它们列为候选。

## 维护者工作流

| 脚本 | 作用 |
|---|---|
| `scripts/refresh.py` | 刷新元数据，报告改名、失效、归档、久未更新的仓库 |
| `scripts/build.py` | 生成 README.md 和 README.en.md；`--check` 检查是否最新，`--validate` 只校验数据 |
| `scripts/discover.py` | 按 taxonomy.toml 里的关键词搜候选项目，输出待审清单 |

GitHub Actions 每周一自动刷新元数据、重新生成 README，并把新候选开成 issue。
