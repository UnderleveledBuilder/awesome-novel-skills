# Awesome Novel Skills

**中文** · [English](README.en.md)

> AI 写小说 · 网文 Skill 精选：扫榜拆书、设定大纲、正文连载、长篇记忆、去 AI 味、短剧剧本、翻译、发布，装进 Claude Code / Codex 就能用。
>
> A curated list of agent skills for writing novels and web fiction with AI: market research, outlining, drafting, long-form continuity, de-AI revision, short-drama scripts, translation and publishing.

这里收录给 Claude Code、Codex、OpenClaw 等 agent 用的小说和网文 skill，覆盖选题扫榜、拆书、设定和人物、大纲章纲、正文续写、防吃书防 OOC、审稿去 AI 味、书名简介封面、翻译出海和发布，也收短剧剧本这类写剧情的 skill，以及拆书用的下载和书源工具。每个项目都经过人工核对，按类型、创作阶段和投稿平台整理。

收录 {{count}} 个 skill 和工具 + {{apps}} 个相关开源应用 · 元数据更新于 {{updated}}

## 定选题装哪个

第二轮实测（2026-10-20）：本清单里 10 个能从零出选题的 skill、短剧清单里的 0xsline/short-drama 和一个不装 skill 的对照组，给同一个以后能写网文、也能拍短剧的爽文故事定选题，各定 3 次；所有参赛者两两盲比，按积分排名。评审看的是交给 AI 拍出来，观众会不会一直看下去。两位 AI 评审（Opus 和 GPT）排出的前三名是同样三个 skill，三个都三次全赢了对照组，都收在本清单里：

| skill | 名次（Opus / GPT） | 适合 | 要注意 |
|---|---|---|---|
| [Tomsawyerhu/Chinese-WebNovel-Skill](https://github.com/Tomsawyerhu/Chinese-WebNovel-Skill) | 1 / 2 | 少见的法律职业加身份翻转，一句话卖点就懂，爽点打在对手脸上 | 有一次是常见的扮猪吃虎；撑长篇有限 |
| [lingfengQAQ/webnovel-writer](https://github.com/lingfengQAQ/webnovel-writer) | 2 / 3 | 金手指配有代价的规则，主角的缺点和能力绑在一起 | 三次都是头顶能看见数字一类；中段容易重复 |
| [Hao0321/ai-short-drama](https://github.com/Hao0321/ai-short-drama) | 3 / 1 | 新意最强，异能都有规矩，钩子有画面 | 规矩把主角限得太被动，爽点来得慢 |

这一轮的局限：
- 不装 skill 的对照组，两位评审都排第 9，有 3 个 skill 排在它后面。
- oh-story 和 chinese-longnovel-skill 定选题要先扫榜，沙箱不能联网，它们没拿到榜单，排在最后几名；联网时选得怎样，这一轮测不出来。
- 两位评审每对的结论，198 个里有 63 个不同，中间几名差得多。
- 只测了 claude-opus-5-5 一个模型；只比选题，不比正文。

全过程和逐个点评见[第二轮实测记录](https://shortdramaskills.com/evals/round-2/)。

**图例**：🌟 精选 · 📝 提示词文件（非标准 skill）· 🧩 完整应用 · 📚 针对的投稿平台 · 💤 超过 180 天未更新 · 📦 已归档 · ⚠️ 仓库失效

> [!NOTE]
> 「人工核对」指核对过仓库说明、目录结构和分类，不等于实测过效果，实测对比见 [evals/](evals/)。skill 可能附带脚本，安装前请先读一遍它的 SKILL.md。
