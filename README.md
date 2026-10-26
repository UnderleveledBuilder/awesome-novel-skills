<!-- 本文件由 scripts/build.py 生成，请勿手改。要改内容请编辑 data/ 或 templates/ 后重新生成。 -->

# Awesome Novel Skills

**中文** · [English](README.en.md)

> AI 写小说 · 网文 Skill 精选：扫榜拆书、设定大纲、正文连载、长篇记忆、去 AI 味、短剧剧本、翻译、发布，装进 Claude Code / Codex 就能用。
>
> A curated list of agent skills for writing novels and web fiction with AI: market research, outlining, drafting, long-form continuity, de-AI revision, short-drama scripts, translation and publishing.

这里收录给 Claude Code、Codex、OpenClaw 等 agent 用的小说和网文 skill，覆盖选题扫榜、拆书、设定和人物、大纲章纲、正文续写、防吃书防 OOC、审稿去 AI 味、书名简介封面、翻译出海和发布，也收短剧剧本这类写剧情的 skill，以及拆书用的下载和书源工具。每个项目都经过人工核对，按类型、创作阶段和投稿平台整理。

收录 205 个 skill 和工具 + 6 个相关开源应用 · 元数据更新于 2026-10-26

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

## 目录

- [本周新增](#new)（0）
- [推荐组合](#packs)
- [按类型](#by-group)
  - [全流程：开书 → 连载](#group-pipeline)（53）
  - [单项工具：拆书 · 设定 · 大纲 · 人物](#group-tools)（12）
  - [短篇 · 故事](#group-short)（6）
  - [剧本 · 短剧：用写网文的功夫写剧情](#group-script)（51）
  - [去 AI 味 · 润色](#group-companion)（30）
  - [写作基本功](#group-craft)（7）
  - [延伸：互动小说 · 改编](#group-beyond)（9）
  - [翻译 · 出海](#group-translate)（15）
  - [素材：小说下载 · 书源](#group-sources)（22）
  - [相关开源应用（完整应用，非 skill）](#group-apps)（6）
- [按创作阶段查找](#by-stage)
- [按投稿平台查找](#by-sites)
- [相关资源](#resources)
- [收录徽章](#badge)

<a id="new"></a>
## 本周新增

本周暂无新增。发现好项目欢迎[推荐](../../issues/new?template=submit-skill.yml)。

<a id="packs"></a>
## 推荐组合

> 初版组合依据仓库说明搭配，尚未实测，实测后会更新。

- **中文网文长篇**：从扫榜开书到百万字连载
  - 组合：[oh-story-claudecode](https://github.com/zenstory-ai/oh-story-claudecode) → [webnovel-writer](https://github.com/lingfengQAQ/webnovel-writer) → [Humanizer-zh](https://github.com/op7418/Humanizer-zh)
  - 思路：oh-story 负责扫榜、拆文和开书，webnovel-writer 负责长篇连载时的记忆和防遗忘（两者写作环节有重叠，择一为主），Humanizer-zh 最后去 AI 味
- **番茄短篇**：选赛道、写一篇番茄短故事
  - 组合：[fanqie-radar](https://github.com/WindXRan/fanqie-radar) → [fanqie-short-story.skill](https://github.com/aby-aby111/fanqie-short-story.skill) → [fiction-humanizer-zh](https://github.com/deedeekong07-alt/fiction-humanizer-zh)
  - 思路：fanqie-radar 看榜单热度选题材，fanqie-short-story 按赛道选题、出标题和分段结构，fiction-humanizer-zh 专修小说的梗概感和汇报腔
- **故事基本功（英文）**：体系化地学习和练习叙事技艺
  - 组合：[agent-skills](https://github.com/jwynia/agent-skills) → [story-skills](https://github.com/danjdewhurst/story-skills)
  - 思路：jwynia 拆得最细，单项技能多；story-skills 把故事圣经、章节、修订串成一个项目流程

<a id="by-group"></a>
## 按类型

<a id="group-pipeline"></a>
### 全流程：开书 → 连载

从选题、设定、大纲一路写到正文和审稿的完整写作系统，主要面向长篇连载。

- 🌟 **[inkos](https://github.com/Narcooo/inkos)** · ★ 10.8k<br>故事创作 Agent 系统：长短篇写作、续写、同人、仿写、拆文、市场调研、剧本、互动影游<br><sub>阶段：选题 · 大纲 · 正文 · 记忆 · 审稿 · 改编</sub><br><sub>更新于 2026-10-24 · 🧩 应用 · 多语言 · 21 个 skill · AGPL-3.0</sub>

- 🌟 **[oh-story-claudecode](https://github.com/zenstory-ai/oh-story-claudecode)** · ★ 8k<br>中文网文全流程：扫榜（起点/番茄/晋江/知乎盐言）、拆文、长短篇写作、去 AI 味<br><sub>阶段：选题 · 大纲 · 正文 · 审稿 · 包装</sub><br><sub>更新于 2026-10-23 · 中文 · 13 个 skill · MIT</sub><br><sub>📚 起点 · 番茄 · 晋江 · 知乎盐言</sub><br><sub>💡 同团队另有 DeepSeek Harness 版 oh-story-dsh</sub>

- 🌟 **[webnovel-writer](https://github.com/lingfengQAQ/webnovel-writer)** · ★ 7.7k<br>Claude Code 长篇网文插件：分阶段初始化设定与总纲、拆卷纲章纲，写章后多维审查并把事实提交进状态库与 RAG，可查伏笔角色，附只读面板<br><sub>阶段：选题 · 设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-10-24 · 中文 · 8 个 skill · GPL-3.0</sub><br><sub>💡 master 为 Claude Code 版，新功能在 v8 分支（DeepSeek Harness）</sub>

- 🌟 **[chinese-novelist-skill](https://github.com/PenglongHuang/chinese-novelist-skill)** · ★ 4.3k<br>从零生成 10–50 章中文小说：三层问答、创作记忆、每章悬念钩子、自动校验<br><sub>阶段：大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-10-20 · 中文 · MIT</sub>

- 🌟 **[story-skills](https://github.com/danjdewhurst/story-skills)** · ★ 352<br>端到端故事工程：故事圣经、角色、情节、章节、修订、连续性检查、读者评审团、投稿<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-10-20 · 英文 · 24 个 skill · MIT</sub>

- 🌟 **[long-novel-writer](https://github.com/jiaw-Zh/long-novel-writer)** · ★ 93<br>百万字长篇写作 skill：六层摘要冻结、实体档案、正典账本与 POV 知识边界，写后双 agent 校验，防止设定漂移<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 记忆</sub><br><sub>更新于 2026-06-18 · 中文</sub><br><sub>💡 思路来自桌面项目 AI_NovelGenerator；作者另有早期版 jiaw-Zh/long-novel-generator</sub>

- 🌟 **[chinese-longnovel-skill](https://github.com/xiaofeng-928/chinese-longnovel-skill)** · ★ 75<br>中文长篇网文工作流：扫榜开书、范文拆解与文风蒸馏、每 50 章分阶段细纲、事实锁与状态仓库、伏笔追踪、双审查自动修复<br><sub>阶段：选题 · 设定 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-09-12 · 中文 · MIT</sub><br><sub>💡 校验脚本需 Python 3；自然化环节内置 Humanizer-zh 规则（已注明来源）</sub>

- **[Chinese-WebNovel-Skill](https://github.com/Tomsawyerhu/Chinese-WebNovel-Skill)** · ★ 924<br>网文写作 skill：主路由分派到开头、转场、对白、章末、剧情逻辑、人物一致性、卷纲、去 AI 味等 10 个模块，写前检索本地语料范例<br><sub>阶段：选题 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-08-28 · 中文</sub><br><sub>💡 README 未写安装方式：SKILL.md 在仓库根目录，把整个仓库放进 skills 目录即可；附 166 篇短篇语料约 11MB，检索脚本需 Python 3</sub>

- **[awesome-novel-agent](https://github.com/modoojunko/awesome-novel-agent)** · ★ 839<br>小说创作搭档：世界观 → 角色 → 章节规划 → 正文，分步陪写整部小说<br><sub>阶段：设定 · 人物 · 大纲 · 正文</sub><br><sub>更新于 2026-09-25 · 中文 · AGPL-3.0</sub><br><sub>💡 名字带 awesome，但它是创作 agent，不是列表</sub>

- **[oh-story-dsh](https://github.com/zenstory-ai/oh-story-dsh)** · ★ 612<br>把 Oh Story 小说技能装进 DeepSeek Harness：加了文件树、编辑器、Chat 三栏的小说工作台，另带短剧、小说改游戏、视频解说工作台<br><sub>阶段：选题 · 设定 · 人物 · 大纲 · 正文 · 审稿 · 包装 · 改编</sub><br><sub>更新于 2026-10-19 · 中文 · 38 个 skill · MIT</sub><br><sub>💡 基于同团队的 zenstory-ai/oh-story-claudecode（打包的 Oh Story 0.8.5，小说技能文件与原版相同）和 novel-to-game，另加 DSH Web 工作台界面和短剧、视频解说技能。只能在 DeepSeek Harness 里用，需要 Node.js 24+；Claude Code 用户用原版</sub>

- **[novel-writing-framework](https://github.com/LAY-lgtm/novel-writing-framework)** · ★ 266<br>五份网文写作方法论：通用长篇流程、番茄快节奏、起点慢热、智斗权谋专项、完稿改良诊断，含三章一轮自检和 AI 指纹量化指标<br><sub>阶段：大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-05-31 · 📝 提示词 · 中文 · MIT</sub><br><sub>📚 番茄 · 起点</sub><br><sub>💡 每份是单独的 .md，需自己放进 skills 目录或手动加载</sub>

- **[Lorn.NovelWriteSkills](https://github.com/lornshrimp/Lorn.NovelWriteSkills)** · ★ 244<br>长篇网文写作资产库：题材定位、人物、大纲、章节创作闭环、审阅润色、去 AI 味、13 个平台改写与分发，附字数/相似度门禁脚本<br><sub>阶段：选题 · 设定 · 人物 · 大纲 · 正文 · 审稿 · 包装 · 发布</sub><br><sub>更新于 2026-09-04 · 中文 · 350 个 skill</sub><br><sub>📚 起点 · 番茄 · 七猫 · 知乎盐言</sub><br><sub>💡 README 只写了 VS Code + GitHub Copilot 用法（.github/skills、.github/prompts 结构）；约 350 个 SKILL.md 也可单独复制到其他 agent；仓库约 22MB，大部分是写作研究资料</sub>

- **[webnovel-writer-opencode](https://github.com/lujih/webnovel-writer-opencode)** · ★ 223<br>webnovel-writer 的 OpenCode 移植增强版：在初始化、规划、写章、审查之外加了批量写、重写、修复、导出和番茄/七猫发布<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿 · 发布</sub><br><sub>更新于 2026-10-21 · 中文 · 16 个 skill · GPL-3.0</sub><br><sub>📚 番茄 · 七猫</sub><br><sub>💡 基于 lingfengQAQ/webnovel-writer，另加 8 个 skill：批量写章、重写、修复、删除、导出（EPUB/DOCX/PDF 等）、番茄风和七猫风写作约束、自动发布到番茄；v2.8 起借鉴 inkos 的事件溯源设计。用 npx @cszx/webnovel-writer-opencode init 安装，Claude Code 用户直接用原版</sub>

- **[sumeru](https://github.com/xindoo/sumeru)** · ★ 216<br>网文全流程 7 个 skill：选题（含榜单分析）→世界观大纲→章节批量撰写→时间线/OOC 审查→润色→多平台导出，可断点续写<br><sub>阶段：选题 · 设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-08-23 · 中文 · 7 个 skill</sub><br><sub>📚 起点 · 番茄 · 晋江</sub>

- **[Distilled-Novel-Toolbox](https://github.com/dama-cyber/Distilled-Novel-Toolbox)** · ★ 192<br>网文写作知识库 13 个 skill：题材、人设、世界观、节奏、爽点、情绪、文风、商业化、合规、润色去 AI 味与 AIGC 检测应对<br><sub>阶段：选题 · 设定 · 人物 · 大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-06-09 · 中文 · 13 个 skill</sub><br><sub>📚 起点 · 番茄 · 晋江 · 知乎盐言</sub><br><sub>💡 README 未写安装方式：把各 novel-* 目录复制到 agent 的 skills 目录即可；每个模块附 test-prompts.json</sub>

- **[awesome-novel-studio](https://github.com/MJbae/awesome-novel-studio)** · ★ 159<br>网文创作 Claude Code 插件：设定、角色、情节钩子、润色、重写<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-04-14 💤 · 英文 · 10 个 skill · Apache-2.0</sub>

- **[tianming-skill](https://github.com/zy-zmc/tianming-skill)** · ★ 157<br>长篇协同创作指令系统：用五份知识库约束世界观与人物，按「天命：大纲/目录/正文/体检/存档」逐步推进<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 记忆</sub><br><sub>更新于 2026-06-06 · 中文</sub><br><sub>💡 CC BY-NC-SA 4.0 非商用许可；README 同时推广作者的同名桌面软件</sub>

- **[novel-harness](https://github.com/manhai934/novel-harness)** · ★ 131<br>网文陪写 harness：开书规划，把章节拆成作者自己填的写作块，审稿去 AI 味，维护角色状态、伏笔和章节摘要<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-08-06 · 中文 · 6 个 skill</sub><br><sub>💡 附本地 Studio Dashboard（需 Python + Node）；可选知识包从作者服务器（阿里云 OSS）下载 zip</sub>

- **[ani-book-skill](https://github.com/ExplosiveCoderflome/ani-book-skill)** · ★ 107<br>长篇中文小说生产：可恢复的 Markdown 工作流，贯通灵感、规划、章节写作、审校与连续性管理<br><sub>阶段：大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-10-15 · 中文 · Apache-2.0</sub>

- **[chinese-webnovel-skills](https://github.com/tance-mang/chinese-webnovel-skills)** · ★ 90<br>网文工坊 Claude Code 插件：选题、起名、大纲、金手指、人设、扩写、爽点、追读诊断、连贯检查、去 AI 味、投稿等 30+ 技能<br><sub>阶段：选题 · 设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿 · 包装</sub><br><sub>更新于 2026-06-13 · 中文 · 33 个 skill · MIT</sub><br><sub>📚 起点 · 番茄 · 晋江 · 知乎盐言 · Royal Road</sub><br><sub>💡 另有接自有 API 的终端 CLI 版；含一个短剧剧本技能</sub>

- **[fanqie-novel-skill](https://github.com/304769384-png/fanqie-novel-skill)** · ★ 80<br>番茄长篇写作 skill：写前读状态文件，写后去 AI 味并跑 8 项最小审计（字数、因果链、战斗、对话占比、话疗、循环等）<br><sub>阶段：大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-06-03 · 中文</sub><br><sub>📚 番茄</sub><br><sub>💡 工作流和状态文件（current_state、pending_hooks、character_matrix 等）沿用 Narcooo/inkos，另加番茄平台规则、商业审查和战斗/对话/话疗/循环审计</sub>

- **[DaisyWriter](https://github.com/ricky-theseus/DaisyWriter)** · ★ 76<br>网文与中短篇写作 skill 合集：扫榜、拆书、开书、大纲、批量写作、审查、去 AI 味、封面生成、番茄自动发布<br><sub>阶段：选题 · 设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿 · 包装 · 发布</sub><br><sub>更新于 2026-07-08 · 中文 · 23 个 skill · GPL-3.0</sub><br><sub>📚 起点 · 番茄 · 晋江 · 七猫 · 知乎盐言</sub><br><sub>💡 基于 lingfengQAQ/webnovel-writer（init/plan/write/review 等 8 个），另加扫榜、拆书、批量写、设定审查、去 AI 味、中短篇 5 个 skill 和封面生成；番茄发布取自 amm10090/fanqie-publisher-skill；另含技术博客/公众号/小红书技能</sub>

- **[dreampowers](https://github.com/skyfiredao/dreampowers)** · ★ 74<br>OpenCode 中文小说技能包：14 个 skill，覆盖构思、七维文风问卷、设定文件隔离、大纲伏笔、分场景写作、冷读与一致性审查<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-07-02 · 中文 · 14 个 skill · GPL-3.0</sub><br><sub>💡 依赖 oh-my-openagent；成人场景技能为选装（install.sh --all 才装）</sub>

- **[oh-story-claudecode](https://github.com/qin1473692580-ux/oh-story-claudecode)** · ★ 69<br>oh-story 派生网文 skill 包：扫榜拆文、长短篇写作、去 AI 味、封面，另加后台数据诊断、资料考证、发布物料和番茄自动发布<br><sub>阶段：选题 · 大纲 · 正文 · 记忆 · 审稿 · 包装 · 发布</sub><br><sub>更新于 2026-09-01 · 中文 · 18 个 skill · MIT</sub><br><sub>📚 番茄</sub><br><sub>💡 基于 zenstory-ai/oh-story-claudecode，2026-08 起独立演进、不同步上游；另加 story-data-analyze、story-research、story-explore、story-release-package、story-publish 五个 skill，以及错别字门禁、新题材包、TRAE/WorkBuddy 适配</sub>

- **[ai-fiction-writer](https://github.com/Wooooooooood/ai-fiction-writer)** · ★ 66<br>长篇网文十个 skill：扫榜拆文、大纲、角色、知识库、世界与地图、逻辑矩阵、进度、正文、去 AI 味质检、多视角审稿<br><sub>阶段：选题 · 设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-10-10 · 中文 · 10 个 skill · MIT</sub><br><sub>💡 README 只写了克隆仓库，需自行把「纯净版skill/」下各目录放进 agent 的 skills 目录</sub>

- **[ultimate-novel-creation-skill](https://github.com/Fly143/ultimate-novel-creation-skill)** · ★ 51<br>长篇小说全流程 skill：书名立项、世界观人设、黄金开篇、单章写作、记忆圣经与强约束、读者审稿、写后流水线<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿 · 包装</sub><br><sub>更新于 2026-10-22 · 中文</sub><br><sub>💡 须先把 system_prompt.md 配成宿主的系统提示词，流程才会被严格执行；写后流水线内置朱雀 AIGC 检测对策</sub>

- **[novelops-skill](https://github.com/qiyan233/novelops-skill)** · ★ 32<br>长篇小说状态化流水线：truth files 记设定与角色认知，生成下一章工作包，LLM 起草，审计修订，状态回写，快照 diff<br><sub>阶段：大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-09-28 · 多语言 · MIT</sub><br><sub>💡 基于 Narcooo/inkos 的思路（truth files、审计-修订-状态回写），用纯 Python 标准库重写成不绑宿主的 skill；另加角色知情边界检查、可配置审计规则、快照/diff、同人与番外的 canon 处理。draft 默认调用本地 Ollama。SKILL.md 以英文为主</sub>

- **[novel-master](https://github.com/bbroot/novel-master)** · ★ 30<br>OpenClaw 长篇小说 skill：策划书、分卷大纲与细纲、三层伏笔追踪、角色状态机与节点压缩图谱、每章四维审计<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-07-14 · 中文 · MIT</sub><br><sub>💡 ClawHub 上装到的是 v1，v2 脚本需从 GitHub 获取</sub>

- **[vibe-noveling](https://github.com/TulanCN/vibe-noveling)** · ★ 29<br>Claude Code 网文插件：苏格拉底式设定讨论、救猫咪全书规划、雪花法事件卡、写后 AI 味检测、标记返修、知识图谱<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-06-02 · 中文 · 16 个 skill · MIT</sub><br><sub>💡 针对 GLM-5 调优，作者要求关闭思考模式；默认风格基线是男频爽文</sub>

- **[book-writer-skill](https://github.com/kshanxs/book-writer-skill)** · ★ 25<br>英文长篇写作：Story Forge 开书问答，Book Memory Bank 自动维护人物/世界/进度，含节奏蓝图、专项修订与简介/query letter<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿 · 包装</sub><br><sub>更新于 2026-07-10 · 英文 · MIT</sub>

- **[webfiction-write](https://github.com/qingyabailu-git/webfiction-write)** · ★ 24<br>Codex 网文工具集 15 个 skill：构思、扫榜、拆文、卷纲细纲、写作与改稿、审查、去AI味、设定查询、导入导出，附项目状态脚本<br><sub>阶段：选题 · 设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-07-31 · 中文 · 15 个 skill · MIT</sub><br><sub>📚 番茄 · 起点 · 七猫</sub><br><sub>💡 基于 zenstory-ai/oh-story-claudecode 与 lingfengQAQ/webnovel-writer 融合，另加 fiction.py（初始化、章节提交、审查指标、导出）和正文检查脚本；需 Python 3.8+</sub>

- **[xt-webnovel-writing](https://github.com/xiaotiewinner/xt-webnovel-writing)** · ★ 24<br>OpenClaw 网文 skill：参考文本拆解、立书（书名/人设/简介）、剧情设计、爽点与文笔、25 项反 AI 味体检、磁盘记忆<br><sub>阶段：选题 · 人物 · 大纲 · 正文 · 记忆 · 审稿 · 包装</sub><br><sub>更新于 2026-04-30 · 中文</sub><br><sub>💡 方法论底本是一篇知乎文章，仓库内存档了全文；仓库没有许可证</sub>

- **[novel-flow-one-by-one](https://github.com/ZhangDongyang800/novel-flow-one-by-one)** · ★ 19<br>6 个协作 skill：脑暴→大纲→逐场景写作→六维审稿→设定同步，总控按状态路由，内置冷白描/系统爽文/怪诞悬疑三种文风<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-07-18 · 中文 · 6 个 skill · MIT</sub><br><sub>💡 README 以 Trae 目录结构为例</sub>

- **[long-novelist-skill](https://github.com/tianshiemo7/long-novelist-skill)** · ★ 17<br>百万字长篇中文小说：13 步配置问答、副本弧线三级大纲、角色状态档案、JSON 伏笔清单、跨会话恢复，附 11 个网文素材库<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 记忆</sub><br><sub>更新于 2026-06-01 · 中文 · MIT</sub><br><sub>💡 基于 PenglongHuang/chinese-novelist-skill 改写（仓库未注明），另加副本弧线规划、角色状态追踪、伏笔 JSON 清单和网文素材库</sub>

- **[silver-novel-skills](https://github.com/jialanhu0915/silver-novel-skills)** · ★ 16<br>男频/女频双系统网文写作：世界观/人物/情节三个框架 agent，按题材加载模板，12 项通用加男女频专项审稿 agent<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-07-07 · 中文 · MIT</sub>

- **[opencreator-novel](https://github.com/xwcai999/opencreator-novel)** · ★ 13<br>中文小说 Codex 插件：读者契约与章节控制卡、待兑现承诺账本、确定性校验脚本、整书文学审稿与跨章结构相似度检查、封面<br><sub>阶段：大纲 · 正文 · 记忆 · 审稿 · 包装</sub><br><sub>更新于 2026-09-07 · 中文 · 3 个 skill · Apache-2.0</sub><br><sub>💡 wawa-* 两个子 skill 是非官方的蛙蛙写作投稿/统计适配，可不装</sub>

- **[human-novel-writer](https://github.com/huahuakandaima/human-novel-writer)** · ★ 12<br>长篇网文全流程：项目骨架与三总控文件、黄金三章合同、角色入场门禁、每章 8 步循环、拆文选题审稿封面，去AI味双门禁脚本<br><sub>阶段：选题 · 设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿 · 包装</sub><br><sub>更新于 2026-10-07 · 中文 · MIT</sub><br><sub>📚 番茄</sub><br><sub>💡 整合 oh-story-claudecode、KKKKhazix/human-writing、writing-dna-skill 与贴吧《小说ai行文规范》，另加角色门禁、黄金三章合同和密度检查脚本；朱雀在线检测需腾讯云 API Key，封面依赖 foxtrai 生图 skill</sub>

- **[novel-assistant-skill](https://github.com/duiniwukenaihe/novel-assistant-skill)** · ★ 12<br>单入口网文助手：短篇/长篇写作、审阅、拆文、扫榜、导入、去AI味，带任务断点续写、按步召回记忆、改纲影响链和章节扩容迁移<br><sub>阶段：选题 · 设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-08-10 · 中文 · 16 个 skill · MIT</sub><br><sub>💡 基于 worldwonderer/oh-story-claudecode（现 zenstory-ai/oh-story-claudecode），另加单入口路由、工作流断点、记忆召回、影响链与健康门；作者称短篇已稳定、长篇仍在打磨</sub>

- **[plotrail](https://github.com/waylean/plotrail)** · ★ 12<br>长篇工作流两件套：plotrail 建 canon、章节合同、写后连续性审稿和作者改稿偏好；plotrail-intake 诊断精修已有旧稿再交接续写<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-06-21 · 英文 · 2 个 skill · MIT</sub><br><sub>💡 skill 正文为英文，README 与示例为中文网文</sub>

- **[wangwenwrite-skill](https://github.com/Thatgfsj-easyRep/wangwenwrite-skill)** · ★ 11<br>男频系统流网文单文件 skill：黄金三章、爽点节奏公式、系统设定法则、反 AI 味清单、书名公式与平台差异化<br><sub>阶段：选题 · 设定 · 大纲 · 正文 · 审稿 · 包装</sub><br><sub>更新于 2026-05-04 · 中文 · Apache-2.0</sub><br><sub>📚 番茄 · 起点</sub>

- **[novel-writing-skill](https://github.com/cnskycn/novel-writing-skill)** · ★ 10<br>长篇连载单文件提示词：大纲 6 步、章节 7 步、人物三锚点、伏笔 P1-P3 分级、六维质检，附追踪与记忆文件模板<br><sub>阶段：大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-05-23 · 📝 提示词 · 中文</sub><br><sub>💡 单个 .md 文件，README 按 Trae .trae/skills/ 安装；风格设定偏「孔二狗式」都市江湖叙事</sub>

- **[novel-writer-skill](https://github.com/liuxiao20051106-prog/novel-writer-skill)** · ★ 9<br>中英双语小说写作 skill：构思、人设、章纲、逐章写作与章节衔接检查、去 AI 味，附草稿量化体检脚本和 11 套追踪模板<br><sub>阶段：选题 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-09-17 · 多语言 · 2 个 skill · MIT</sub><br><sub>💡 另附 ChatGPT、DeepSeek、Gemini 等网页端的系统提示词用法</sub>

- **[chinese-novelist-skill](https://github.com/lvyu-cmd/chinese-novelist-skill)** · ★ 6<br>中文长篇小说 skill：五项输入自动生成设定，逐章或子 Agent 并行写作，三层记忆、七维自动校验、章节评分和三级修订<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-06-17 · 中文</sub><br><sub>💡 基于 PenglongHuang/chinese-novelist-skill，另加 SQLite 持久化、三层记忆、修订模式和 8 个校验/评分脚本；README 里的 clone 地址写成 chinese-novelist-skill-master，要换成本仓库</sub>

- **[general-novel-skill](https://github.com/xiaoyuCR7/general-novel-skill)** · ★ 6<br>长篇网文 skill：每章正文与摘要、角色状态、伏笔、时间线按事务一起提交，7 道去 AI 味闸口，34 题材与多平台规则按需加载<br><sub>阶段：选题 · 设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿 · 包装</sub><br><sub>更新于 2026-10-23 · 中文 · MIT</sub><br><sub>📚 番茄 · 起点 · 晋江 · 知乎盐言 · 七猫</sub><br><sub>💡 体量大（47 个脚本、118 份参考、24 个 MCP 工具），附五章示例书和去 AI 味前后对照</sub>

- **[novel-webfiction](https://github.com/zlbigger/novel-webfiction)** · ★ 6<br>OpenClaw 网文连载 skill：开书问 4 个问题建档，每章先读设定、大纲和最近 3 章再写，正文按章存进 Obsidian<br><sub>阶段：设定 · 大纲 · 正文 · 记忆</sub><br><sub>更新于 2026-06-28 · 中文 · MIT</sub><br><sub>💡 单文件、规则较简单，适合轻量连载</sub>

- **[open-novel-fanqie](https://github.com/kongxcer555/open-novel-fanqie)** · ★ 6<br>番茄网文长篇流水线 12 个 skill：拆对标书出套路 JSON、换壳选切入点、书名简介与事件、大纲人物设定、细纲、正文、审稿、滚动摘要<br><sub>阶段：选题 · 设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿 · 包装</sub><br><sub>更新于 2026-06-12 · 中文 · 11 个 skill · MIT</sub><br><sub>📚 番茄</sub><br><sub>💡 原仓库 mosonlab/open-novel-fanqie 已失效，这里是转存；README 里的 git clone 地址要换成 kongxcer555/open-novel-fanqie。脚本依赖 bun，p7 去 AI 味尚未完成</sub>

- **[web-novel-master](https://github.com/tinylion1024/web-novel-master)** · ★ 6<br>网文创作工作流：快速、专业、工业、一次生成四种模式，含 11 个赛道的作者文风卡、套路库、平台定位包和项目初始化与校验脚本<br><sub>阶段：选题 · 设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿 · 包装</sub><br><sub>更新于 2026-07-20 · 中文 · MIT</sub><br><sub>📚 起点 · 番茄 · 晋江</sub><br><sub>💡 基于 PenglongHuang/chinese-novelist-skill（情节结构、人物塑造、对话、扩写等指南沿用原版），另加四种创作模式、作者文风卡、平台定位包、市场数据和项目管理脚本</sub>

- **[fanqie-xiaoshuo-skill](https://github.com/soultt/fanqie-xiaoshuo-skill)** · ★ 5<br>番茄风网文 11 个 skill：设定、总纲与章纲的设计和审查、正文写作和审查、签约潜力评估、日更工作流<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-06-26 · 中文 · 11 个 skill</sub><br><sub>📚 番茄</sub><br><sub>💡 README 安装说明简略；仓库描述里的「包签约」是宣传语，实际是签约评估模板</sub>

- **[novel-craft](https://github.com/dongyanyuxuana/novel-craft)** · ★ 5<br>通用小说 skill：主控加 7 个子代理，访谈立项、资料拆分、逐章写作、逐段 17 维审查、修订发布，附 34 位作家技法库<br><sub>阶段：选题 · 设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-09-06 · 中文 · MIT</sub><br><sub>💡 含成人向场景参考文档，按受众分级启用</sub>

- **[novel-engine](https://github.com/jiangying3222880/novel-engine)** · ★ 5<br>网文写作引擎：拆对标书建素材池，细纲、正文、检验打回、落库四段流水线，管长篇状态，另有短故事模式和 BM25 检索<br><sub>阶段：选题 · 设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-10-17 · 中文 · 12 个 skill</sub><br><sub>💡 门禁、检索、同步脚本需 Python，不装时降级为手动校验；生成的「叙事总览」目录可作为 Obsidian 库查看</sub>

- **[novelist-skill](https://github.com/chanceline-max/novelist-skill)** · ★ 5<br>Codex 中文小说 skill：从灵感到卷纲章纲、正文续写与改稿，维护人物、世界观、伏笔、时间线和章节总结文件<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-07-23 · 中文 · MIT</sub>

- **[web-novel-writing-skill](https://github.com/XINGANLIU/web-novel-writing-skill)** · ★ 5<br>网文 10 阶段流水线：灵感、世界观、人物、总纲、卷纲、章纲、黄金三章、正文、质检、状态同步，含人物漂移和反派降智检查<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-06-11 · 中文 · MIT</sub>

- **[novel-craft](https://github.com/chaserr/novel-craft)** · ★ 4<br>Claude Code 长篇写作与审稿插件：5 个 skill + 12 个 agent，用 RTK.md 定题材风格，管大纲、前情、伏笔、人物档案和逐章审稿<br><sub>阶段：人物 · 大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-09-18 · 中文 · 6 个 skill · MIT</sub><br><sub>💡 作者另有同流程的桌面版 novel-craft-studio</sub>


<details><summary>安装命令</summary>

```bash
# 默认命令基于 skills CLI，未逐个验证，以各仓库 README 为准
# oh-story-claudecode
npx -y skills add zenstory-ai/oh-story-claudecode --agent claude-code
# webnovel-writer
npx skills add lingfengQAQ/webnovel-writer
# chinese-novelist-skill
npx skills add PenglongHuang/chinese-novelist-skill
# story-skills
npx skills add danjdewhurst/story-skills
# long-novel-writer
npx skills add jiaw-Zh/long-novel-writer
# chinese-longnovel-skill
npx skills add xiaofeng-928/chinese-longnovel-skill
# Chinese-WebNovel-Skill
npx skills add Tomsawyerhu/Chinese-WebNovel-Skill
# awesome-novel-agent
npx skills add modoojunko/awesome-novel-agent
# oh-story-dsh
npx skills add zenstory-ai/oh-story-dsh
# Lorn.NovelWriteSkills
npx skills add lornshrimp/Lorn.NovelWriteSkills
# webnovel-writer-opencode
npx skills add lujih/webnovel-writer-opencode
# sumeru
npx skills add xindoo/sumeru
# Distilled-Novel-Toolbox
npx skills add dama-cyber/Distilled-Novel-Toolbox
# awesome-novel-studio
npx skills add MJbae/awesome-novel-studio
# tianming-skill
npx skills add zy-zmc/tianming-skill
# novel-harness
npx skills add manhai934/novel-harness
# ani-book-skill
npx skills add ExplosiveCoderflome/ani-book-skill
# chinese-webnovel-skills
npx skills add tance-mang/chinese-webnovel-skills
# fanqie-novel-skill
npx skills add 304769384-png/fanqie-novel-skill
# DaisyWriter
npx skills add ricky-theseus/DaisyWriter
# dreampowers
npx skills add skyfiredao/dreampowers
# oh-story-claudecode
npx skills add qin1473692580-ux/oh-story-claudecode
# ai-fiction-writer
npx skills add Wooooooooood/ai-fiction-writer
# ultimate-novel-creation-skill
npx skills add Fly143/ultimate-novel-creation-skill
# novelops-skill
npx skills add qiyan233/novelops-skill
# novel-master
npx skills add bbroot/novel-master
# vibe-noveling
npx skills add TulanCN/vibe-noveling
# book-writer-skill
npx skills add kshanxs/book-writer-skill
# webfiction-write
npx skills add qingyabailu-git/webfiction-write
# xt-webnovel-writing
npx skills add xiaotiewinner/xt-webnovel-writing
# novel-flow-one-by-one
npx skills add ZhangDongyang800/novel-flow-one-by-one
# long-novelist-skill
npx skills add tianshiemo7/long-novelist-skill
# silver-novel-skills
npx skills add jialanhu0915/silver-novel-skills
# opencreator-novel
npx skills add xwcai999/opencreator-novel
# human-novel-writer
npx skills add huahuakandaima/human-novel-writer
# novel-assistant-skill
npx skills add duiniwukenaihe/novel-assistant-skill
# plotrail
npx skills add waylean/plotrail
# wangwenwrite-skill
npx skills add Thatgfsj-easyRep/wangwenwrite-skill
# novel-writer-skill
npx skills add liuxiao20051106-prog/novel-writer-skill
# chinese-novelist-skill
npx skills add lvyu-cmd/chinese-novelist-skill
# general-novel-skill
npx skills add xiaoyuCR7/general-novel-skill
# novel-webfiction
npx skills add zlbigger/novel-webfiction
# open-novel-fanqie
npx skills add kongxcer555/open-novel-fanqie
# web-novel-master
npx skills add tinylion1024/web-novel-master
# fanqie-xiaoshuo-skill
npx skills add soultt/fanqie-xiaoshuo-skill
# novel-craft
npx skills add dongyanyuxuana/novel-craft
# novel-engine
npx skills add jiangying3222880/novel-engine
# novelist-skill
npx skills add chanceline-max/novelist-skill
# web-novel-writing-skill
npx skills add XINGANLIU/web-novel-writing-skill
# novel-craft
npx skills add chaserr/novel-craft
```

</details>

<a id="group-tools"></a>
### 单项工具：拆书 · 设定 · 大纲 · 人物

只做一两件事，可以单独用，也可以给全流程系统补短板。

- **[Fanfic-background-assistant](https://github.com/Elowwwen/Fanfic-background-assistant)** · ★ 103<br>同人文背景研究：梳理时代、地点、职业、制度等资料并附来源，检查草稿里的事实错误，维护背景手册，不碰剧情<br><sub>阶段：设定</sub><br><sub>更新于 2026-09-19 · 中文 · MIT</sub>

- **[chinese-erotic-fiction-writing](https://github.com/xWebt/chinese-erotic-fiction-writing)** · ★ 54<br>中文成人向（H）小说写作 skill：动笔前勘察偏好，按写作规范写作、扩写、重写，可学习本地书库文风，会话记忆逐步收敛口味<br><sub>阶段：大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-08-04 · 中文</sub><br><sub>💡 本地 CLI 需 Python ≥3.10（pip install -e .），可把本地 txt 书库建成 SQLite 索引，统计技法密度；用户偏好存在 sessions/，不进 git</sub>

- **[xin-skills](https://github.com/oscar-wang-xin/xin-skills)** · ★ 33<br>122 个文风锁定 skill：从番茄热门书和金庸、古龙等指定小说萃取十维风格规范，只仿文笔不抄剧情<br><sub>阶段：正文</sub><br><sub>更新于 2026-09-25 · 中文 · 122 个 skill</sub><br><sub>💡 每个技能附对应原作的段落摘录作风格样本</sub>

- **[fanqie-publisher-skill](https://github.com/amm10090/fanqie-publisher-skill)** · ★ 24<br>番茄小说作者后台章节发布：解析本地 Markdown 章节，用 Playwright 自动填写，立即或定时发布，带仅填写模式和发布后状态核验<br><sub>阶段：发布</sub><br><sub>更新于 2026-10-25 · 英文 · MIT</sub><br><sub>📚 番茄</sub><br><sub>💡 需 Node.js、Python 3、可经 CDP 连接的 Chrome 和番茄作者账号；走网页自动化而非官方接口，后台改版可能失效。README 有中文版</sub>

- **[wenfeng-skill](https://github.com/XTmingyue/wenfeng-skill)** · ★ 22<br>给一部小说文本，提炼叙事模型、语言指纹、母题、人物与情节技法，生成可直接调用的仿写 SKILL.md<br><sub>阶段：选题 · 正文</sub><br><sub>更新于 2026-05-26 · 中文 · MIT</sub><br><sub>💡 仓库不含原作文本，需自备有权处理的小说文本</sub>

- **[analyze-hit-novel](https://github.com/ciel-oliver/analyze-hit-novel)** · ★ 17<br>爆款小说拆文：六维拆书、双时间线、三维节奏、人物关系图 PNG，提炼爆款机制并附章节证据<br><sub>阶段：选题</sub><br><sub>更新于 2026-09-04 · 中文</sub>

- **[fanqie-radar](https://github.com/WindXRan/fanqie-radar)** · ★ 14<br>番茄榜单扫榜选书：内置榜单快照和采集器，算题材热度、多日趋势差分和六维仿写适合度评分，附 MCP 服务与看板<br><sub>阶段：选题</sub><br><sub>更新于 2026-09-07 · 中文 · MIT</sub><br><sub>📚 番茄</sub><br><sub>💡 只采集公开榜单元数据，不下载正文；需 Python 3.10+</sub>

- **[fictional-erotica](https://github.com/rs-skills-lab/fictional-erotica)** · ★ 9<br>中英双语成人情色场景写作与修订：可调明确度、语域、对白密度和场景重心，保持人物声口和身体动作连续，支持原创与同人<br><sub>阶段：正文 · 审稿</sub><br><sub>更新于 2026-08-27 · 多语言 · MIT</sub><br><sub>💡 仅限 18+；skill 在 fictional-erotica/ 子目录，tests/ 附测试提示词和评分表</sub>

- **[auto-fanqie](https://github.com/Kirby980/auto-fanqie)** · ★ 8<br>番茄作家后台自动发章：先校验字数，再用 Playwright 打开本机 Chrome，按书名和分卷新建章节、填正文并处理发布弹窗<br><sub>阶段：发布</sub><br><sub>更新于 2026-05-14 · 中文 · 3 个 skill</sub><br><sub>📚 番茄</sub><br><sub>💡 需 Node.js 和 @playwright/cli，首次要手动扫码登录；Go 引擎用 go run 运行 fanqie-go/main.go 源码，仓库里的 fanqie-go/main 二进制不会被调用；发布设置默认勾选「不使用 AI」，书名和分卷默认值要改成自己的；README 的 clone 地址是占位符</sub>

- **[novel-project-strategy](https://github.com/wgwtest/novel-project-strategy)** · ★ 6<br>Codex 长篇项目管理 skill：定义加载顺序、章节状态与同步规则，新会话不读全文也能恢复项目，防止大纲、设定、正文互相漂移<br><sub>阶段：记忆</sub><br><sub>更新于 2026-04-18 💤 · 英文 · MIT</sub>

- **[character-card-fiction-workflow-skill](https://github.com/shigehaomingzi1/character-card-fiction-workflow-skill)** · ★ 5<br>从草稿、聊天记录或小说提炼角色设定和原文证据，生成酒馆 AI（SillyTavern）角色卡，也能扩写、续写小说<br><sub>阶段：人物 · 正文</sub><br><sub>更新于 2026-06-18 · 中文 · GPL-3.0</sub>

- **[Creative-writing-skill](https://github.com/xbraindance/Creative-writing-skill)** · ★ 5<br>用 Verbalized Sampling 一次给出多版点子、开头、大纲和人物，草稿自动归档进项目 wiki，带卡文诊断和批评命令<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-04-28 💤 · 英文 · MIT</sub><br><sub>💡 通用创意写作（含诗歌），非长篇专用；仓库附 12MB 论文 PDF</sub>


<details><summary>安装命令</summary>

```bash
# 默认命令基于 skills CLI，未逐个验证，以各仓库 README 为准
# Fanfic-background-assistant
npx skills add Elowwwen/Fanfic-background-assistant
# chinese-erotic-fiction-writing
npx skills add xWebt/chinese-erotic-fiction-writing
# xin-skills
npx skills add oscar-wang-xin/xin-skills
# fanqie-publisher-skill
npx skills add amm10090/fanqie-publisher-skill
# wenfeng-skill
npx skills add XTmingyue/wenfeng-skill
# analyze-hit-novel
npx skills add ciel-oliver/analyze-hit-novel
# fanqie-radar
npx skills add WindXRan/fanqie-radar
# fictional-erotica
npx skills add rs-skills-lab/fictional-erotica
# auto-fanqie
npx skills add Kirby980/auto-fanqie
# novel-project-strategy
npx skills add wgwtest/novel-project-strategy
# character-card-fiction-workflow-skill
npx skills add shigehaomingzi1/character-card-fiction-workflow-skill
# Creative-writing-skill
npx skills add xbraindance/Creative-writing-skill
```

</details>

<a id="group-short"></a>
### 短篇 · 故事

番茄短篇、知乎盐言、儿童故事等短篇体裁。

- **[bookflow-skill](https://github.com/LanyXiaosheng/bookflow-skill)** · ★ 207<br>番茄短篇项目化生产：选题、对标、人物、大纲、beat、正文、QA、复盘<br><sub>阶段：选题 · 人物 · 大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-09-18 · 中文 · MIT</sub><br><sub>📚 番茄</sub>

- **[lengdu](https://github.com/asass-11/lengdu)** · ★ 43<br>中文短篇创作与冷读：先写完正文，再由独立校准 Agent 和全新读者 Agent 首读，检验看懂、流畅、好看<br><sub>阶段：正文 · 审稿</sub><br><sub>更新于 2026-10-22 · 中文 · MIT</sub><br><sub>💡 PolyForm Noncommercial 许可，禁止任何商业使用</sub>

- **[sun-yuchen-writing](https://github.com/AAAAAAAJ/sun-yuchen-writing)** · ★ 24<br>冷峻账单式第一人称短篇：先建数字、物件、劳动、空缺四本素材账和叙述者盲点表，按新题材重造双层故事，排六到八个场景、结尾回收物件；附十维审稿量表<br><sub>阶段：大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-08-27 · 中文</sub><br><sub>💡 写法提炼自孙宇晨《我的女友景甜》，SKILL.md 要求不复用原文句子、人物关系和情节；仓库附带原文全文</sub>

- **[fanqie-short-story.skill](https://github.com/aby-aby111/fanqie-short-story.skill)** · ★ 18<br>番茄短故事创作：8 条赛道逐级选题、标题生成打分、5 段式结构与章末三层钩子、字数校验与手机排版<br><sub>阶段：选题 · 大纲 · 正文 · 包装</sub><br><sub>更新于 2026-05-13 · 中文 · GPL-3.0</sub><br><sub>📚 番茄</sub><br><sub>💡 README 未写安装步骤，目录示例为 CodeBuddy skills 路径；输出路径默认写死为 Windows D 盘</sub>

- **[horror-weird-fiction-skill](https://github.com/EnderRomantice/horror-weird-fiction-skill)** · ★ 8<br>怪异恐怖短篇写作 skill：从日常场景放入单一异常，按同一方向升级 2 到 4 次，不解释来源收尾，避开鬼怪、血腥和惊吓桥段<br><sub>阶段：正文</sub><br><sub>更新于 2026-06-26 · 中文</sub><br><sub>💡 附两篇示例；CC BY-SA 4.0</sub>

- **[jiamama-bedtime-story-skill](https://github.com/leonluo2008-ops/jiamama-bedtime-story-skill)** · ★ 4<br>中文儿童睡前故事，从 2101 篇语料蒸馏出的叙事人格<br><sub>阶段：正文</sub><br><sub>更新于 2026-06-15 · 中文</sub>


<details><summary>安装命令</summary>

```bash
# 默认命令基于 skills CLI，未逐个验证，以各仓库 README 为准
# bookflow-skill
npx skills add LanyXiaosheng/bookflow-skill
# lengdu
npx skills add asass-11/lengdu
# sun-yuchen-writing
npx skills add AAAAAAAJ/sun-yuchen-writing
# fanqie-short-story.skill
npx skills add aby-aby111/fanqie-short-story.skill
# horror-weird-fiction-skill
npx skills add EnderRomantice/horror-weird-fiction-skill
# jiamama-bedtime-story-skill
npx skills add leonluo2008-ops/jiamama-bedtime-story-skill
```

</details>

<a id="group-script"></a>
### 剧本 · 短剧：用写网文的功夫写剧情

短剧、漫剧和网文是同一套剧情功夫，只是呈现方式不同。这里收写剧情的部分：改编、集纲、钩子、剧本、审稿。分镜和视频提示词见 [awesome-short-drama-skills](https://github.com/UnderleveledBuilder/awesome-short-drama-skills)。

- **[shuohao-skills](https://github.com/eternityspring/shuohao-skills)** · ★ 5.1k<br>短剧制作 skill 集：拆角色、改编大纲、场景与道具美术设定、剧本、分镜<br><sub>阶段：人物 · 大纲 · 正文 · 改编</sub><br><sub>更新于 2026-10-26 · 多语言 · 7 个 skill · Apache-2.0</sub>

- **[drama-skills](https://github.com/zenstory-ai/drama-skills)** · ★ 3.4k<br>短剧/漫剧全链路：拆小说、开发、剧本、角色资产、分镜、图/视频提示词、审查<br><sub>阶段：人物 · 正文 · 审稿 · 改编</sub><br><sub>更新于 2026-10-20 · 中文 · 12 个 skill · MIT</sub>

- **[Seedance2-Storyboard-Generator](https://github.com/liangdabiao/Seedance2-Storyboard-Generator)** · ★ 2.7k<br>把小说或故事改成多集视频剧本和分镜，产出 Seedance 2.0 提示词<br><sub>阶段：正文 · 改编</sub><br><sub>更新于 2026-09-21 · 中文</sub>

- **[screenwriting-skills](https://github.com/jtydhr88/screenwriting-skills)** · ★ 1.8k<br>编剧理论最系统的一套：结构、Truby、场景、对白、剧集圣经、编剧室，含日韩法美与中国戏曲案例<br><sub>阶段：人物 · 大纲 · 正文 · 审稿 · 改编</sub><br><sub>更新于 2026-10-03 · 中文 · 26 个 skill · MIT</sub><br><sub>💡 skill 正文为中文，README 有五种语言</sub>

- **[manju-laoli-skill](https://github.com/lixiaoxiao9888-create/manju-laoli-skill)** · ★ 1.7k<br>漫剧老李：AIGC 漫剧导演全流程，门控剧本、资产锁定、分镜、投喂提示词、规则化质检<br><sub>阶段：正文 · 审稿</sub><br><sub>更新于 2026-10-21 · 中文 · 13 个 skill · MIT</sub><br><sub>💡 作者标注为测试版，整合了其他开源内容</sub>

- **[shanyin-screenwriting-master](https://github.com/Shanyin-ai/shanyin-screenwriting-master)** · ★ 1.4k<br>山音超级编剧大师：概念超短片、叙事短片、长片、多集剧集四种格式的人物、大纲、场景拆解和完整剧本<br><sub>阶段：人物 · 大纲 · 正文</sub><br><sub>更新于 2026-04-01 💤 · 中文 · MIT</sub><br><sub>💡 以 .skill 文件分发，不能用 npx skills 安装</sub>

- **[seedance-2-5-video-director](https://github.com/liyue-aigc/seedance-2-5-video-director)** · ★ 731<br>Seedance 2.5 视频导演：提示词、脚本、诊断、人物锁定、续写、编辑、转场<br><sub>阶段：正文 · 审稿</sub><br><sub>更新于 2026-08-26 · 中文 · MIT</sub>

- **[XiaoLuo-AI-Drama-Skill](https://github.com/zhurui0523/XiaoLuo-AI-Drama-Skill)** · ★ 495<br>小逻系列：剧本分析、原创改编、分镜脚本、角色三视图/服装/表情、场景布局<br><sub>阶段：人物 · 正文 · 改编</sub><br><sub>更新于 2026-07-23 · 📝 提示词 · 中文</sub><br><sub>💡 一组提示词 .md，不是标准 SKILL.md</sub>

- **[screen-creative-skills](https://github.com/VanGong1999/screen-creative-skills)** · ★ 476<br>影视策划与评估：小说/IP 评估、情节点拆解、人物小传与关系、大纲、小说改编短剧或长剧<br><sub>阶段：选题 · 人物 · 大纲 · 改编</sub><br><sub>更新于 2026-10-20 · 中文 · 31 个 skill · MIT</sub><br><sub>💡 31 个 skill 在仓库里有两份副本</sub>

- **[short-drama-factory](https://github.com/lixiaoxiao9888-create/short-drama-factory)** · ★ 466<br>抖音/红果短剧工业化编剧：一句创意或一部网文 → 60–100 集带付费卡点的剧本，配钩子、断章、反转公式和机检规则<br><sub>阶段：大纲 · 正文 · 审稿 · 改编</sub><br><sub>更新于 2026-10-24 · 中文 · MIT</sub>

- **[OnlyShot](https://github.com/A-cat-with-carrots/OnlyShot)** · ★ 337<br>神仙鱼短剧流水线：一句话 → 剧本、分镜、分镜图、视频、剪辑五步，沉淀 17 种失败模式<br><sub>阶段：正文</sub><br><sub>更新于 2026-07-07 · 中文 · MIT</sub>

- **[Micro-Drama-Skills](https://github.com/zhaihao118/Micro-Drama-Skills)** · ★ 326<br>短剧全流程自动化：剧本、角色设计、分镜、出图出视频与提交<br><sub>阶段：正文</sub><br><sub>更新于 2026-02-23 💤 · 中文 · 4 个 skill</sub>

- **[smy-seedance-storyboard](https://github.com/liangdabiao/smy-seedance-storyboard)** · ★ 203<br>故事 → 上美影复古手绘风格的短剧制作文档：剧本、分镜、资产生图提示词，附完整示例项目<br><sub>阶段：正文 · 改编</sub><br><sub>更新于 2026-10-08 · 中文</sub>

- **[short-drama-production](https://github.com/suihe1/short-drama-production)** · ★ 187<br>短剧生产总控：小说大纲/人物/剧本、导演分镜、提示词、声音资产、粗剪与 QC（默认 16:9）<br><sub>阶段：大纲 · 正文 · 改编</sub><br><sub>更新于 2026-09-16 · 中文 · 8 个 skill · Apache-2.0</sub><br><sub>💡 有 5 个 skill 与 shuohao-skills 同名，可能同源</sub>

- **[qisi-video-remix](https://github.com/wyuzhi/qisi-video-remix)** · ★ 183<br>视频创意改编：参考视频 → 剧本 → 分镜 → 分段生成提示词<br><sub>阶段：正文 · 改编</sub><br><sub>更新于 2026-09-11 · 中文 · MIT</sub>

- **[workrally](https://github.com/Tencent/workrally)** · ★ 179<br>腾讯开源：面向 AI Agent 的 AIGC 漫剧视频创作全流程工具集<br><sub>阶段：正文</sub><br><sub>更新于 2026-09-29 · 中文</sub>

- **[film-studio-skills](https://github.com/machina-exm/film-studio-skills)** · ★ 160<br>剧本 → 锁定、可直接生成的镜头：7 个 skill 复刻商业 AI 视频制作流程<br><sub>阶段：正文</sub><br><sub>更新于 2026-08-14 · 英文 · 7 个 skill</sub>

- **[infinite-creation](https://github.com/SwotAtmk/infinite-creation)** · ★ 129<br>提交小说或剧本，用本地 ComfyUI + MiniMax H3 + Agent 自动连续生产视频，不限时长<br><sub>阶段：改编</sub><br><sub>更新于 2026-10-26 · 中文 · 37 个 skill · MIT</sub><br><sub>💡 28 个 skill 里也有广告、宣传片类</sub>

- **[narrative-to-screen-reader](https://github.com/zhlmi/narrative-to-screen-reader)** · ★ 125<br>把手上的故事翻译成影视开发语言：快速诊断、编剧改编读本、导演视听读本、演员读本、制片摘要<br><sub>阶段：选题 · 人物 · 改编</sub><br><sub>更新于 2026-10-01 · 中文</sub>

- **[fight-video-create-skill](https://github.com/qualsenWeb/fight-video-create-skill)** · ★ 98<br>AI 打戏设计：从打斗构思到剧情、动作、分镜，带招式校验和参考库<br><sub>阶段：正文</sub><br><sub>更新于 2026-09-29 · 多语言</sub>

- **[short-drama-skills](https://github.com/YvonneMovingon/short-drama-skills)** · ★ 95<br>LuxReal 生产验证的短剧提示词：叙事拆解、情绪刻画、动态描述、剧情拆分、视频提示词润色<br><sub>阶段：正文 · 审稿 · 改编</sub><br><sub>更新于 2026-07-01 · 📝 提示词 · 多语言 · MIT</sub><br><sub>💡 prompt.md 形式，不是标准 SKILL.md</sub>

- **[screenwriter-skill](https://github.com/Vi7QY/screenwriter-skill)** · ★ 88<br>短剧/漫剧剧本审稿：红果 Top100 操盘经验蒸馏的 37 条规则<br><sub>阶段：审稿</sub><br><sub>更新于 2026-04-12 💤 · 多语言 · MIT</sub>

- **[ai-short-drama](https://github.com/Hao0321/ai-short-drama)** · ★ 74<br>把「重生、逆袭、隐藏大佬」等题材编译成有爽点和追更钩子的连载：题材调研、故事架构、镜头时间线、连续性校验<br><sub>阶段：选题 · 大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-08-13 · 中文 · MIT</sub><br><sub>💡 README 为繁体中文</sub>

- **[ai-short-drama-skill](https://github.com/xixihhhh/ai-short-drama-skill)** · ★ 72<br>Dramake：文字转 AI 短剧，串起剧本、分镜、配音、剪辑与质检，适配抖音/红果和横竖屏，自带 evals<br><sub>阶段：正文 · 审稿 · 改编</sub><br><sub>更新于 2026-08-29 · 中文 · MIT</sub>

- **[novel-to-manju](https://github.com/senmanx/novel-to-manju)** · ★ 64<br>小说转漫剧全流程：爆款改文 → 剧本 → 人物/场景三视图 → 分镜 → 视频提示词<br><sub>阶段：人物 · 正文 · 改编</sub><br><sub>更新于 2026-08-17 · 中文</sub>

- **[acheng-director-skill](https://github.com/AharaOoO/acheng-director-skill)** · ★ 49<br>Acheng 导演引擎：剧本、分镜、文戏五轨表演、打戏因果链、特效与资产，编译成 MiniMax H3 / Seedance 提示词<br><sub>阶段：人物 · 正文 · 审稿</sub><br><sub>更新于 2026-10-01 · 中文 · 11 个 skill · Apache-2.0</sub><br><sub>💡 CC BY-NC-ND 4.0（禁商用、禁演绎）；附 132 段运镜白模视频，仓库体积较大</sub>

- **[qianqianwriting](https://github.com/catyiqian/qianqianwriting)** · ★ 49<br>短剧/漫剧编剧：救猫咪方法论 + 31 部爆款短剧分析<br><sub>阶段：大纲 · 正文</sub><br><sub>更新于 2026-03-05 💤 · 中文</sub>

- **[muse-video-skill](https://github.com/LuoJiangYong/muse-video-skill)** · ★ 46<br>虚拟剧组：导演/编剧/摄影/美术/特效/声音六角色协作，创意 → 剧本、分镜、美术、提示词，38 个案例技法库<br><sub>阶段：正文 · 审稿</sub><br><sub>更新于 2026-09-30 · 多语言 · MIT</sub>

- **[ai-short-drama](https://github.com/oiuv/ai-short-drama)** · ★ 43<br>雪风爽剧：一句话补全创作需求，按爽点模型写分集剧本并同步角色/场景/道具档案，再拆镜写 Seedance 2.0 提示词<br><sub>阶段：人物 · 大纲 · 正文</sub><br><sub>更新于 2026-08-22 · 中文 · 5 个 skill</sub><br><sub>💡 随「雪风AI短剧工坊」应用发布，README 未写 agent 安装步骤；仓库无许可证</sub>

- **[open-source-video-gen-skill](https://github.com/mini-yifan/open-source-video-gen-skill)** · ★ 39<br>Vibe Video：在 AutoDL 上跑开源 MiniMax H3 出片，短剧模板串起 Brief、分集概要、剧本台词、美术和视频，含 H3 提示词写法<br><sub>阶段：人物 · 大纲 · 正文</sub><br><sub>更新于 2026-09-11 · 多语言 · 9 个 skill</sub><br><sub>💡 依赖 AutoDL GPU 实例（按时计费）；短剧模板只管流程关卡，叙事部分较薄</sub>

- **[jingju-skills](https://github.com/jxshow/jingju-skills)** · ★ 38<br>鲸剧：AI 漫剧全流程，大纲、人设一致性、分集剧本、分镜、图/视频提示词、ComfyUI 批量出图<br><sub>阶段：人物 · 大纲 · 正文</sub><br><sub>更新于 2026-06-09 · 中文</sub>

- **[spark-video](https://github.com/JohnKeating1997/spark-video)** · ★ 34<br>一句梗概 → 剧本、分镜、角色/场景/道具一致性、渲染、逐镜 AI 质检到成片 mp4，每阶段设确认关卡<br><sub>阶段：人物 · 正文 · 审稿</sub><br><sub>更新于 2026-09-01 · 英文 · 7 个 skill</sub><br><sub>💡 依赖阿里云百炼等付费视频 API；默认短剧模式，也有广告和科普示例</sub>

- **[novel-to-ai-short-drama-skill](https://github.com/muxia0396/novel-to-ai-short-drama-skill)** · ★ 31<br>从导演视角把小说改编成 AI 短剧：分镜、运镜、表演调度与时长<br><sub>阶段：改编</sub><br><sub>更新于 2026-09-04 · 中文 · MIT</sub>

- **[5min-drama-contest](https://github.com/SoloEnt-AI/5min-drama-contest)** · ★ 27<br>五分钟短剧剧本：一步一问锁定赛道、立意、结构原型和前 30 秒开场，四幕卡点大纲 → 正式剧本 → 分镜脚本<br><sub>阶段：人物 · 大纲 · 正文</sub><br><sub>更新于 2026-08-29 · 中文</sub><br><sub>💡 灵蟹创作（SoloEnt）出品，面向其五分钟短剧大赛</sub>

- **[short-drama-director](https://github.com/UncleWang2088/short-drama-director)** · ★ 26<br>短剧导演专家包：剧本创作、平台标准审稿、镜头级分镜与表演指导，输出 Seedance 提示词<br><sub>阶段：正文 · 审稿</sub><br><sub>更新于 2026-10-13 · 中文 · 9 个 skill</sub>

- **[ManjuForge](https://github.com/mengxiujie/ManjuForge)** · ★ 24<br>漫剧/短剧连载引擎：一句话 → 剧本、分镜、配音、提示词，7 个记忆文件 + 22 项一致性检查防人设崩坏<br><sub>阶段：大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-10-13 · 中文 · MIT-0</sub>

- **[write-chinese-long-screenplay](https://github.com/mudden2380078550-creator/write-chinese-long-screenplay)** · ★ 23<br>中文电影与长剧集剧本写作<br><sub>阶段：大纲 · 正文</sub><br><sub>更新于 2026-09-12 · 中文 · 2 个 skill · GPL-3.0</sub>

- **[ShortVideoDirector](https://github.com/wddxh/ShortVideoDirector)** · ★ 21<br>4 个子代理协作，把故事创意转成视频分镜提示词和资产图像提示词<br><sub>阶段：人物 · 大纲</sub><br><sub>更新于 2026-09-16 · 中文 · 35 个 skill · MIT</sub>

- **[hardcore-director](https://github.com/jlam00-dev/hardcore-director)** · ★ 20<br>硬核导演：影视与 AI 视频总控，按阶段路由编剧/短剧、角色场景、分镜、Seedance 2.5/Wan 3.0/H3 提示词、声音与剪辑模块<br><sub>阶段：人物 · 大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-10-01 · 中文 · MIT</sub><br><sub>💡 整合包：大部分模块是第三方 skill 快照（已注明来源），也覆盖广告和宣传片</sub>

- **[ai-manga-drama](https://github.com/liuxiao20051106-prog/ai-manga-drama)** · ★ 18<br>AI 漫剧工坊：一句创意到成片的八步流程，任务卡剧本、角色参考图库、风格锚、分镜、图/视频提示词、配音字幕与合成终检<br><sub>阶段：人物 · 大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-09-17 · 多语言 · 2 个 skill · MIT</sub>

- **[Comfy-H3-Director](https://github.com/MIKA6941/Comfy-H3-Director)** · ★ 16<br>MiniMax H3 漫剧导演：网文改分镜、核心/龙套资产分级、文戏长镜与武戏快切、动作连续性锁定、尾帧接力，一次出整集提示词<br><sub>阶段：人物 · 改编</sub><br><sub>更新于 2026-08-30 · 多语言 · 10 个 skill</sub><br><sub>💡 另附 9 个 MiniMax 官方 H3 skill 的搬运/中译版；README 开头有要求 agent 直接执行流程的指令</sub>

- **[vision_art_creator](https://github.com/ilkaydemiralay/vision_art_creator)** · ★ 15<br>影视部门式 skill 包：编剧、导演、角色、美术、摄影、分镜、镜头表、提示词、声音、剪辑，由总监 skill 调度和质检<br><sub>阶段：人物 · 正文 · 审稿</sub><br><sub>更新于 2026-10-07 · 英文 · 11 个 skill · MIT</sub><br><sub>💡 偏电影，不专做短剧</sub>

- **[ai-comic-drama-director-skills](https://github.com/djyy1031/ai-comic-drama-director-skills)** · ★ 14<br>AI 漫剧导演：剧本 + 已有资产 → Seedance 2.0/2.5 分镜组提示词，含人物表演、导演摄影、场景资产、站位图、连续性与声音<br><sub>阶段：人物 · 审稿 · 改编</sub><br><sub>更新于 2026-10-11 · 中文 · 7 个 skill · MIT</sub>

- **[screenplay-review-checklist](https://github.com/zhlmi/screenplay-review-checklist)** · ★ 14<br>对抗式剧本踩雷诊断：拿 37 条判据只给你的故事找问题<br><sub>阶段：审稿</sub><br><sub>更新于 2026-08-15 · 中文</sub>

- **[chinese-epic-scene-director](https://github.com/zhouwei713/chinese-epic-scene-director)** · ★ 13<br>中国式宏大场景：把一句设定扩写成仙侠/神话短片故事，建连续性台账，按镜头成对输出图片和视频提示词<br><sub>阶段：人物 · 正文</sub><br><sub>更新于 2026-08-18 · 中文 · MIT</sub><br><sub>💡 分叙事运镜和视觉展览两种模式，后者偏氛围、景观展示</sub>

- **[claude-screenwriting](https://github.com/e06084/claude-screenwriting)** · ★ 9<br>编剧知识引擎：把 Vogler/McKee/救猫咪落成 Obsidian 故事 wiki，15-beat 节奏、三层角色卡、结构诊断<br><sub>阶段：人物 · 大纲 · 审稿</sub><br><sub>更新于 2026-10-08 · 中文 · 8 个 skill · MIT</sub>

- **[kunka-screenwriting-master](https://github.com/geslie1/kunka-screenwriting-master)** · ★ 7<br>昆卡编剧大师：中文优先的编剧 skill 组，覆盖构思、改稿、连续性检查与剧集开发<br><sub>阶段：大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-09-10 · 中文 · 13 个 skill · MIT</sub>

- **[gushi-skill](https://github.com/pipivv/gushi-skill)** · ★ 6<br>从麦基《故事》蒸馏的短剧编剧方法<br><sub>阶段：大纲 · 正文</sub><br><sub>更新于 2026-06-16 · 中文</sub>

- **[write-screenplay-skill](https://github.com/egguy886/write-screenplay-skill)** · ★ 6<br>小说/设定转商业剧本，国内短剧与出海微短剧双模式<br><sub>阶段：正文 · 改编</sub><br><sub>更新于 2026-10-25 · 中文 · MIT</sub>

- **[emma-screenwriting-skills](https://github.com/adoria111/emma-screenwriting-skills)** · ★ 3<br>艾玛短剧技能组：结构拆解、改编、选题迭代、期待设计、逐集钩子、集纲扩写、对白诊断、剧本删减<br><sub>阶段：选题 · 大纲 · 正文 · 审稿 · 改编</sub><br><sub>更新于 2026-10-13 · 中文 · 10 个 skill · MIT</sub>

- **[hongguo-shortdrama-screenwriting](https://github.com/zhu5859243-free/hongguo-shortdrama-screenwriting)** · ★ 0<br>红果/抖音爆款短剧编剧：短剧工厂引擎 + 《短剧编剧第一课》01–10 期方法论<br><sub>阶段：大纲 · 正文</sub><br><sub>更新于 2026-09-22 · 中文 · MIT</sub><br><sub>💡 方法论来源为作者自述，未核实</sub>


<details><summary>安装命令</summary>

```bash
# 默认命令基于 skills CLI，未逐个验证，以各仓库 README 为准
# shuohao-skills
npx skills add eternityspring/shuohao-skills
# drama-skills
npx skills add zenstory-ai/drama-skills
# Seedance2-Storyboard-Generator
npx skills add liangdabiao/Seedance2-Storyboard-Generator
# screenwriting-skills
/plugin marketplace add jtydhr88/screenwriting-skills
# manju-laoli-skill
npx skills add lixiaoxiao9888-create/manju-laoli-skill
# shanyin-screenwriting-master
# 下载仓库里的 .skill 文件，在 Claude App 的 Skills 中导入（另有通用 .md 版）
# seedance-2-5-video-director
npx skills add liyue-aigc/seedance-2-5-video-director
# screen-creative-skills
npx skills add VanGong1999/screen-creative-skills
# short-drama-factory
npx skills add lixiaoxiao9888-create/short-drama-factory
# OnlyShot
npx skills add A-cat-with-carrots/OnlyShot
# Micro-Drama-Skills
npx skills add zhaihao118/Micro-Drama-Skills
# smy-seedance-storyboard
npx skills add liangdabiao/smy-seedance-storyboard
# short-drama-production
npx skills add suihe1/short-drama-production
# qisi-video-remix
npx skills add wyuzhi/qisi-video-remix
# workrally
npx skills add Tencent/workrally
# film-studio-skills
npx skills add machina-exm/film-studio-skills
# infinite-creation
npx skills add SwotAtmk/infinite-creation
# narrative-to-screen-reader
npx skills add zhlmi/narrative-to-screen-reader
# fight-video-create-skill
npx skills add qualsenWeb/fight-video-create-skill
# screenwriter-skill
npx skills add Vi7QY/screenwriter-skill
# ai-short-drama
npx skills add Hao0321/ai-short-drama
# ai-short-drama-skill
npx skills add xixihhhh/ai-short-drama-skill
# novel-to-manju
npx skills add senmanx/novel-to-manju
# acheng-director-skill
npx skills add AharaOoO/acheng-director-skill
# qianqianwriting
npx skills add catyiqian/qianqianwriting
# muse-video-skill
npx skills add LuoJiangYong/muse-video-skill
# ai-short-drama
npx skills add oiuv/ai-short-drama
# open-source-video-gen-skill
npx skills add mini-yifan/open-source-video-gen-skill
# jingju-skills
npx skills add jxshow/jingju-skills
# spark-video
npx skills add JohnKeating1997/spark-video
# novel-to-ai-short-drama-skill
npx skills add muxia0396/novel-to-ai-short-drama-skill
# 5min-drama-contest
npx skills add SoloEnt-AI/5min-drama-contest
# short-drama-director
npx skills add UncleWang2088/short-drama-director
# ManjuForge
npx skills add mengxiujie/ManjuForge
# write-chinese-long-screenplay
npx skills add mudden2380078550-creator/write-chinese-long-screenplay
# ShortVideoDirector
npx skills add wddxh/ShortVideoDirector
# hardcore-director
npx skills add jlam00-dev/hardcore-director
# ai-manga-drama
npx skills add liuxiao20051106-prog/ai-manga-drama
# Comfy-H3-Director
npx skills add MIKA6941/Comfy-H3-Director
# vision_art_creator
npx skills add ilkaydemiralay/vision_art_creator
# ai-comic-drama-director-skills
npx skills add djyy1031/ai-comic-drama-director-skills
# screenplay-review-checklist
npx skills add zhlmi/screenplay-review-checklist
# chinese-epic-scene-director
npx skills add zhouwei713/chinese-epic-scene-director
# claude-screenwriting
npx skills add e06084/claude-screenwriting
# kunka-screenwriting-master
npx skills add geslie1/kunka-screenwriting-master
# gushi-skill
npx skills add pipivv/gushi-skill
# write-screenplay-skill
npx skills add egguy886/write-screenplay-skill
# emma-screenwriting-skills
npx skills add adoria111/emma-screenwriting-skills
# hongguo-shortdrama-screenwriting
npx skills add zhu5859243-free/hongguo-shortdrama-screenwriting
```

</details>

<a id="group-companion"></a>
### 去 AI 味 · 润色

让文字读起来不像 AI 写的。不限于小说，网文作者用得最多。

- 🌟 **[Humanizer-zh](https://github.com/op7418/Humanizer-zh)** · ★ 20.9k<br>blader/humanizer 的中文改编版：按 31 个检查点（含 6 项中文专项）清理空话和模板句，保留事实、确定程度与作者语气<br><sub>阶段：审稿</sub><br><sub>更新于 2026-09-23 · 中文 · MIT</sub><br><sub>💡 通用中文润色，不专门针对小说；规则源自 blader/humanizer，已按中文重写</sub>

- 🌟 **[lieflat-less-ai-tone](https://github.com/larashero3-dotcom/lieflat-less-ai-tone)** · ★ 4.1k<br>用 283 万字人机对照语料检验 26 项「AI 味」特征，只按通过检验的 11 项改写，附可复算的检测脚本<br><sub>阶段：审稿</sub><br><sub>更新于 2026-08-24 · 中文 · MIT</sub><br><sub>💡 通用中文，非小说专用</sub>

- 🌟 **[shuorenhua](https://github.com/MrGeDiao/shuorenhua)** · ★ 2.3k<br>中文优先的去套话改写：保留数字、条件、承诺和作者口气，可选自由/句内/原位三档改动范围，附 123 条评测集<br><sub>阶段：审稿</sub><br><sub>更新于 2026-10-25 · 中文 · MIT</sub><br><sub>💡 主要面向说明文、工作文本和个人文章，不专门针对小说</sub>

- **[humanizer](https://github.com/blader/humanizer)** · ★ 60.7k<br>按维基百科「Signs of AI writing」清单去除 AI 写作痕迹<br><sub>阶段：审稿</sub><br><sub>更新于 2026-10-16 · 英文 · MIT</sub>

- **[stop-slop](https://github.com/hardikpandya/stop-slop)** · ★ 18.3k<br>识别并删掉 AI 套话、模板句式和节奏问题<br><sub>阶段：审稿</sub><br><sub>更新于 2026-03-17 💤 · 英文 · MIT</sub>

- **[human-writing](https://github.com/KKKKhazix/human-writing)** · ★ 4.2k<br>活人感写作：让 AI 写的中文像具体的人在说话，适用小说、公众号、口播等<br><sub>阶段：审稿</sub><br><sub>更新于 2026-08-11 · 中文 · MIT</sub>

- **[sepia](https://github.com/Nanako0129/sepia)** · ★ 3.5k<br>面向小说的去 AI 味：修复叙事结构，按场合匹配文风规则，方法来自 StoryScope 论文<br><sub>阶段：审稿</sub><br><sub>更新于 2026-10-15 · 英文 · 6 个 skill · MIT</sub>

- **[speak-human-tw](https://github.com/Raymondhou0917/speak-human-tw)** · ★ 1.1k<br>繁体中文去 AI 味：抓 35+ 种 AI 写作痕迹，同时把大陆用语和半角标点改成台湾写法，附交稿前自评检核表<br><sub>阶段：审稿</sub><br><sub>更新于 2026-10-26 · 中文 · MIT</sub><br><sub>💡 面向文案、电子报和办公文字，会把大陆用语改成台湾用语，简体网文别用</sub>

- **[De-AI-Prompt-Enhancer-Writer-Booster-SKILL](https://github.com/OUBIGFA/De-AI-Prompt-Enhancer-Writer-Booster-SKILL)** · ★ 920<br>中文去 AI 味 + 作者文风复现两套 skill，小说文本会先过叙事层十项检查（主题被说破、情绪只靠身体反应等）<br><sub>阶段：审稿</sub><br><sub>更新于 2026-09-17 · 中文 · 7 个 skill</sub><br><sub>💡 README 自述在 op7418/Humanizer-zh 基础上升级，叙事层和文风模块是新增内容</sub>

- **[qu-ai-wei](https://github.com/LifelongLazyLearner/qu-ai-wei)** · ★ 695<br>简体中文去 AI 味：清理套话、翻译腔和机械排比，保留事实、正式程度和原文声口，没有问题的真人文字不改<br><sub>阶段：审稿</sub><br><sub>更新于 2026-09-10 · 中文 · MIT</sub><br><sub>💡 通用中文，不专门针对小说</sub>

- **[humanize-text-skill](https://github.com/lynote-ai/humanize-text-skill)** · ★ 242<br>中英双语去 AI 味：规则检测器识别 50 类问题并打分，改写时保护数字、命令和引文，再向口语/专业/技术语气靠拢<br><sub>阶段：审稿</sub><br><sub>更新于 2026-07-07 · 多语言 · 2 个 skill · MIT</sub><br><sub>💡 文档以英文为主；检测器是零依赖的 Node.js 脚本；场景偏 README、发布说明、状态更新等技术文本</sub>

- **[humanizer-zh-next](https://github.com/Hyacehila/humanizer-zh-next)** · ★ 214<br>中文润色去 AI 味：35 类模式各配中文示例和适用边界，按需加载商务营销、学术写作、基金申请三个专用分支<br><sub>阶段：审稿</sub><br><sub>更新于 2026-10-25 · 中文 · MIT</sub><br><sub>💡 基于 op7418/Humanizer-zh 与 blader/humanizer，另加商务/学术/基金三个分支、文件保护规则和结构检查脚本</sub>

- **[zh-humanizer-literary](https://github.com/mengke-wang/zh-humanizer-literary)** · ★ 90<br>中文去 AI 味与文采增强：删套话，把抽象判断换成具体的人、场景和动作，在准确前提下补命名、意象和节奏<br><sub>阶段：审稿</sub><br><sub>更新于 2026-08-07 · 中文 · MIT</sub><br><sub>💡 风格提炼自作者王梦珂（好事发生 App）的公开写作，示例多为公众号、小红书和产品文案</sub>

- **[qu-ai-wei](https://github.com/baibanbao/qu-ai-wei)** · ★ 73<br>中文去 AI 味：合并王佩写作系统、humanizer-zh、lieflat 三家规则并裁决七处冲突，分自家稿、白名单两种改稿模式<br><sub>阶段：审稿</sub><br><sub>更新于 2026-09-23 · 中文 · MIT</sub><br><sub>💡 面向一般中文稿件，不是专为小说写的</sub>

- **[de-ai-tone](https://github.com/allenloves/de-ai-tone)** · ★ 62<br>繁体中文写作与翻译的去 AI 味规范：18 条禁用/限用规则、欧化句式还原、台湾用语对照、生成后逐条自检<br><sub>阶段：审稿</sub><br><sub>更新于 2026-10-18 · 中文 · CC-BY-SA-4.0</sub><br><sub>💡 面向繁中（台湾）通用写作与翻译，不是专为小说写的；CC BY-SA 4.0</sub>

- **[novel-humanize](https://github.com/qi531416/novel-humanize)** · ★ 25<br>中文小说/网文去 AI 味：逐句细改打散骨架，对话改「」、清零破折号、调标点节奏，保剧情不 OOC，L1-L4 分层自检<br><sub>阶段：审稿</sub><br><sub>更新于 2026-08-06 · 中文</sub><br><sub>💡 融合 anti-zhuque、ultra-remove-ai、wechat-ai-detox 的规则，另引用 laoguo2025/huoren-write 与 KKKKhazix/human-writing 的细则（需到原仓库查阅）；目标之一是通过腾讯朱雀检测</sub>

- **[chinese-grammar-proofreader](https://github.com/orange4664/chinese-grammar-proofreader)** · ★ 19<br>中文病句检查：逐句查语序、搭配、成分残缺、指代不明、两面对一面等，只做最小修改，歧义句给两种改法<br><sub>阶段：审稿</sub><br><sub>更新于 2026-10-01 · 中文 · MIT</sub><br><sub>💡 只查语病、不做去 AI 味；例句以说明文/技术文为主</sub>

- **[zu-article-polisher-skill](https://github.com/wwenj/zu-article-polisher-skill)** · ★ 19<br>中文长文去 AI 味：识别模板开场、假问题、否定式排比、强行升华、宣传腔等，重写文章骨架，附 Markdown 风格检查脚本<br><sub>阶段：审稿</sub><br><sub>更新于 2026-06-23 · 中文</sub><br><sub>💡 面向技术文章、公众号和讲稿，非小说专用</sub>

- **[natural-writing-skill](https://github.com/yyx20202020/natural-writing-skill)** · ★ 18<br>中英文去 AI 味：按修改力度与结构范围两组参数改写，按写作样本校准文风，附脚本核对数字、日期、代码等事实是否丢失<br><sub>阶段：审稿</sub><br><sub>更新于 2026-07-16 · 多语言 · MIT</sub><br><sub>💡 适用场景以公众号、口播稿、技术文档等非虚构为主，非小说专用</sub>

- **[sloptrim-zh](https://github.com/ismilewolf-eng/sloptrim-zh)** · ★ 15<br>中文去 AI 味：85 条模式加本地检测脚本给 0-100 分，按分数分档改写，保留事实和限定词，另有歌词模式<br><sub>阶段：审稿</sub><br><sub>更新于 2026-10-18 · 中文 · Apache-2.0</sub><br><sub>💡 通用中文去 AI 味，非小说专用；基于英文 sloptrim 汉化</sub>

- **[fiction-humanizer-zh](https://github.com/deedeekong07-alt/fiction-humanizer-zh)** · ★ 12<br>中文小说去 AI 味：修复梗概感、情绪标签、对白汇报腔、冲突无代价，按铺垫-过程-余波重写，强化前 300 字和章末钩子<br><sub>阶段：审稿</sub><br><sub>更新于 2026-06-01 · 中文 · MIT</sub><br><sub>📚 番茄 · 七猫 · 起点</sub>

- **[de-ai-router](https://github.com/YuliangXiu/de-ai-router)** · ★ 11<br>去 AI 味路由：按文本类型和意图从 10 个去 AI 味 skill 中选首选与备选再执行，中文文本路由到 qu-ai-wei / humanizer-zh<br><sub>阶段：审稿</sub><br><sub>更新于 2026-09-25 · 多语言 · 11 个 skill · MIT</sub><br><sub>💡 仓库打包附带 10 个他人的去 AI 味 skill（其中 2 个上游无许可证），自身只新增路由层</sub>

- **[mohen](https://github.com/cxzxx783/mohen)** · ★ 9<br>中文自媒体人味写作 skill：写前调研、标题、成稿、12 项去 AI 味硬门槛、AI 味评分和平台适配，附质检脚本与网页版单文件<br><sub>阶段：审稿</sub><br><sub>更新于 2026-10-18 · 中文</sub><br><sub>💡 面向小红书、头条、百家号、公众号文章，不针对小说；CC BY-NC-SA 4.0，不可商用；网页版单文件实际文件名是 mohen-v5.1-*.txt</sub>

- **[huoren-write](https://github.com/laoguo2025/huoren-write)** · ★ 8<br>网文与短剧文本的去 AI 味打磨：清理模板腔、假精确、万能安抚腔和强行升华，保留剧情事实与人物声口，附检查脚本<br><sub>阶段：审稿</sub><br><sub>更新于 2026-06-25 · 中文</sub><br><sub>💡 同时覆盖短剧剧本</sub>

- **[writing-skills.TW](https://github.com/aeopress/writing-skills.TW)** · ★ 8<br>繁体中文（台湾）去 AI 味与节奏打磨：humanizer-tw 清 AI 腔和大陆用语，good-writing-tw 调句子节奏，附英文 humanizer<br><sub>阶段：审稿</sub><br><sub>更新于 2026-09-22 · 中文 · 6 个 skill · MIT</sub><br><sub>💡 通用写作，非小说专用；作者 yelban 已把原 humanizer.TW 并入此仓库</sub>

- **[human-tone-writing](https://github.com/betterwu7889/human-tone-writing)** · ★ 7<br>人味写作三层法：先按金字塔原则写对结构，再从立场、细节、节奏上去 AI 味，最后补说服力和个人风格<br><sub>阶段：审稿</sub><br><sub>更新于 2026-09-03 · 中文 · MIT</sub><br><sub>💡 示例偏汇报、方案、公众号等非虚构文本</sub>

- **[chinese-de-ai-writing](https://github.com/tangwenwen-md/chinese-de-ai-writing)** · ★ 6<br>按证据分级的中文去 AI 味审稿与改稿：只执行语料验证过的规则，不新增事实、不改断言强度，附扫描脚本和验证结果<br><sub>阶段：审稿</sub><br><sub>更新于 2026-09-29 · 中文 · MIT</sub><br><sub>💡 规则改编自 lieflat-less-ai-tone、Humanizer-zh 等 7 个项目（见 THIRD_PARTY_NOTICES.md），另加证据分级和 HC3 语料验证；语体专项覆盖小红书、口播、科普、公文、学术，不含小说</sub>

- **[xiaoci-skill](https://github.com/evoworkAI/xiaoci-skill)** · ★ 6<br>中文去 AI 味：23 条带密度门限的可改规则加 19 条禁改清单，按 9 种语体调门限，scan.py 计算 AI 味浓度并记改动台账<br><sub>阶段：审稿</sub><br><sub>更新于 2026-09-17 · 中文 · MIT</sub><br><sub>💡 基于 larashero3-dotcom/lieflat-less-ai-tone 的 283 万字语料数据，另加禁改清单、语体路由和扫描脚本；小说/散文语体默认最高保护，改动最少；附可粘贴进网页 AI 的 PROMPT.md</sub>

- **[humanize-chinese-writing](https://github.com/fy-agent/humanize-chinese-writing)** · ★ 5<br>中文去 AI 味与人性化改写：清理黑话、套话、模板腔，可按作者样本匹配风格，并检查 HTML 页面和分析稿的信息密度<br><sub>阶段：审稿</sub><br><sub>更新于 2026-08-11 · 中文</sub><br><sub>💡 面向文章、邮件、网页等非虚构文本；PolyForm Noncommercial 许可，不可商用</sub>

- **[novel-to-webnovel](https://github.com/aimerfeng/novel-to-webnovel)** · ★ 1<br>把日轻译稿、机翻稿的翻译腔改成中文网文口感：分三档程度，格式清理、风格定调、样例确认、分块并行改写、QA 脚本<br><sub>阶段：审稿</sub><br><sub>更新于 2026-07-03 · 中文 · MIT</sub><br><sub>💡 需要 perl。默认另存新文件；重度档会把人名和背景改成中国本土</sub>


<details><summary>安装命令</summary>

```bash
# 默认命令基于 skills CLI，未逐个验证，以各仓库 README 为准
# Humanizer-zh
npx skills add op7418/Humanizer-zh
# lieflat-less-ai-tone
npx skills add larashero3-dotcom/lieflat-less-ai-tone
# shuorenhua
npx skills add MrGeDiao/shuorenhua
# humanizer
npx skills add blader/humanizer
# stop-slop
npx skills add hardikpandya/stop-slop
# human-writing
npx skills add KKKKhazix/human-writing
# sepia
npx skills add Nanako0129/sepia
# speak-human-tw
npx skills add Raymondhou0917/speak-human-tw
# De-AI-Prompt-Enhancer-Writer-Booster-SKILL
npx skills add OUBIGFA/De-AI-Prompt-Enhancer-Writer-Booster-SKILL
# qu-ai-wei
npx skills add LifelongLazyLearner/qu-ai-wei
# humanize-text-skill
npx skills add lynote-ai/humanize-text-skill
# humanizer-zh-next
npx skills add Hyacehila/humanizer-zh-next
# zh-humanizer-literary
npx skills add mengke-wang/zh-humanizer-literary
# qu-ai-wei
npx skills add baibanbao/qu-ai-wei
# de-ai-tone
npx skills add allenloves/de-ai-tone
# novel-humanize
npx skills add qi531416/novel-humanize
# chinese-grammar-proofreader
npx skills add orange4664/chinese-grammar-proofreader
# zu-article-polisher-skill
npx skills add wwenj/zu-article-polisher-skill
# natural-writing-skill
npx skills add yyx20202020/natural-writing-skill
# sloptrim-zh
npx skills add ismilewolf-eng/sloptrim-zh
# fiction-humanizer-zh
npx skills add deedeekong07-alt/fiction-humanizer-zh
# de-ai-router
npx skills add YuliangXiu/de-ai-router
# mohen
npx skills add cxzxx783/mohen
# huoren-write
npx skills add laoguo2025/huoren-write
# writing-skills.TW
npx skills add aeopress/writing-skills.TW
# human-tone-writing
npx skills add betterwu7889/human-tone-writing
# chinese-de-ai-writing
npx skills add tangwenwen-md/chinese-de-ai-writing
# xiaoci-skill
npx skills add evoworkAI/xiaoci-skill
# humanize-chinese-writing
npx skills add fy-agent/humanize-chinese-writing
# novel-to-webnovel
npx skills add aimerfeng/novel-to-webnovel
```

</details>

<a id="group-craft"></a>
### 写作基本功

不限于网文的叙事理论和练习：结构、人物、对白、视角。

- **[creative-writing-skills](https://github.com/haowjy/creative-writing-skills)** · ★ 541<br>通用创意写作插件：写作/批评/修改/探索分工，含故事规划、故事记忆、读者模拟<br><sub>阶段：大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-10-25 · 英文 · 24 个 skill · Apache-2.0</sub>

- **[agent-skills](https://github.com/jwynia/agent-skills)** · ★ 176<br>叙事技能大全：故事教练、合写、大纲、人物弧光、对白、结局、反套路、闪小说，大量世界观构建体系<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-02-24 💤 · 英文 · 119 个 skill</sub><br><sub>💡 也含营销等非虚构 skill，按需挑选安装</sub>

- **[novel-writing](https://github.com/wgwtest/novel-writing)** · ★ 54<br>小说写作基本功 skill：场景/章/卷的因果规划、视角与知情边界、有后果的对话、保留作者声音的修订与审稿<br><sub>阶段：大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-09-26 · 英文 · MIT</sub><br><sub>💡 skill 正文为英文，示例有中英两版</sub>

- **[wangwen-writing-skill-kit](https://github.com/hyi1233/wangwen-writing-skill-kit)** · ★ 13<br>网文方法论技能包：一个调度 skill 按需加载开篇、金手指、简介、伏笔、爽感、人物、节奏、去AI化、拆书等 13 个模块<br><sub>阶段：选题 · 人物 · 大纲 · 正文 · 审稿 · 包装</sub><br><sub>更新于 2026-08-24 · 中文</sub><br><sub>💡 内容蒸馏自 B 站 UP 主「网文徐掌柜」的拆书视频，含其原话金句</sub>

- **[inkcraft-writing-skills](https://github.com/Fei2411/inkcraft-writing-skills)** · ★ 8<br>13 种网文体裁的写作方法库，每个体裁分结构、前三章、场景写法、成文规范、自检清单五份，带体裁自动分流 skill<br><sub>阶段：大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-09-12 · 中文 · 14 个 skill</sub><br><sub>💡 CC BY 4.0；由商业产品 InkCraft 的写作材料提炼，不含软件本身</sub>

- **[writing-skills](https://github.com/Calliope-Editor/writing-skills)** · ★ 7<br>13 个只评不写的英文小说 skill：结构/行文/校对/连贯性编辑、角色卡、试读读者团、经纪人首页审读，以及对话、场景、叙述距离练习<br><sub>阶段：人物 · 审稿</sub><br><sub>更新于 2026-07-16 · 英文 · 13 个 skill · MIT</sub><br><sub>💡 由写作应用 Calliope 发布，可选接其 MCP；skill 本身不需要账号</sub>

- **[AutoWriter](https://github.com/sinfiny/AutoWriter)** · ★ 5<br>34 个英文写作 skill：Sanderson 方法论套件、网连载谋略与悬念公平性、潜台词、叙述密度、因果世界观，外加自主写作循环<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-04-30 · 英文 · 34 个 skill</sub><br><sub>💡 主 README 只介绍未完成的 Elixir 循环，skill 说明见 skills/README.md；另含若干非虚构和营销类 skill</sub>


<details><summary>安装命令</summary>

```bash
# 默认命令基于 skills CLI，未逐个验证，以各仓库 README 为准
# creative-writing-skills
npx skills add haowjy/creative-writing-skills
# agent-skills
npx skills add jwynia/agent-skills
# novel-writing
npx skills add wgwtest/novel-writing
# wangwen-writing-skill-kit
npx skills add hyi1233/wangwen-writing-skill-kit
# inkcraft-writing-skills
npx skills add Fei2411/inkcraft-writing-skills
# writing-skills
npx skills add Calliope-Editor/writing-skills
# AutoWriter
npx skills add sinfiny/AutoWriter
```

</details>

<a id="group-beyond"></a>
### 延伸：互动小说 · 改编

把小说变成互动故事、游戏或漫画。改编成短剧剧本的见上面「剧本 · 短剧」。

- **[novel-to-game](https://github.com/zenstory-ai/novel-to-game)** · ★ 925<br>小说改编游戏：带原文出处的设计文档、网页游戏构建与基于证据的 QA，附三个可玩示例<br><sub>阶段：设定 · 改编</sub><br><sub>更新于 2026-10-20 · 多语言 · 7 个 skill · MIT</sub>

- **[novel_to_comic](https://github.com/aiskyhub/novel_to_comic)** · ★ 50<br>小说忠实改编漫画的 Codex 插件：剧本先行、多角色子代理审校、整页提示词逐页生成、导出手机竖屏漫画<br><sub>阶段：改编</sub><br><sub>更新于 2026-10-12 · 中文</sub><br><sub>💡 多子代理运行，token 消耗大；需要能出图的模型</sub>

- **[interactive-fiction-skill](https://github.com/Treasure-hub-agent/interactive-fiction-skill)** · ★ 38<br>选项驱动的互动小说：你选，它写，装进 AI 助手即可玩<br><sub>阶段：正文</sub><br><sub>更新于 2026-10-18 · 多语言 · MIT</sub>

- **[velvet-ascent-skill](https://github.com/ruijayfeng/velvet-ascent-skill)** · ★ 29<br>中文成人向后宫养成文字游戏 GM：角色分 6 阶段推进关系，NSFW 档位 0-4 可调，8 文件记忆世界、人物与伏笔，结束后可导出小说<br><sub>阶段：人物 · 正文 · 记忆</sub><br><sub>更新于 2026-07-13 · 中文 · MIT</sub><br><sub>💡 用 npx @ruizhefeng/velvet-ascent-skill 安装，默认装到 ~/.agents/skills/velvet-ascent，可用 --target 改路径；支持切换女性向剧情</sub>

- **[soul-killer](https://github.com/Xeonice/soul-killer)** · ★ 26<br>从任意人物的公开数字足迹提取身份、语言风格和行为模式，蒸馏成角色，再和世界观合成可游玩的 Galgame 剧本 skill<br><sub>阶段：人物 · 改编</sub><br><sub>更新于 2026-04-15 💤 · 🧩 应用 · 多语言 · GPL-3.0</sub><br><sub>💡 CLI 工具（TypeScript 源码在仓库），导出的 .skill 档案在 Claude Code / OpenClaw 里游玩；官方安装脚本从作者的 Cloudflare 下载二进制，也可以从源码构建</sub>

- **[codex-novel-to-comic-studio](https://github.com/lhfer/codex-novel-to-comic-studio)** · ★ 25<br>EPUB/TXT 小说改编漫画：版权声明关口、故事与视觉圣经、分页剧本和分镜、image2 整页生成、导出 PDF/CBZ<br><sub>阶段：改编</sub><br><sub>更新于 2026-05-19 · 英文 · 13 个 skill · MIT</sub><br><sub>💡 依赖 Codex image2 出图；README 另有中文、日文版</sub>

- **[fanfic-roleplay-design](https://github.com/unknowlei/fanfic-roleplay-design)** · ★ 17<br>同人角色扮演设计：联网整理原作资料，生成或合并 SillyTavern 世界书，分还原模式与人物模式，可按主线阶段配置 MVU 变量<br><sub>阶段：设定 · 人物 · 改编</sub><br><sub>更新于 2026-10-06 · 英文</sub><br><sub>💡 产物是 SillyTavern 世界书 JSON；MVU/EJS 功能需预装 Tavern Helper 与 MVU</sub>

- **[interactive-novel](https://github.com/din1919/interactive-novel)** · ★ 10<br>把小说片段变成可游玩的互动故事：提取世界状态和人物，用户扮演其中角色，系统接管 NPC 与世界反应，带分层记忆和存读档<br><sub>阶段：改编</sub><br><sub>更新于 2026-06-16 · 中文 · MIT</sub><br><sub>💡 skill 在 interactive-novel/ 子目录；附 state-helper.js（Node）做存读档和一致性检查；含 NSFW 协议</sub>

- **[codex-noval-2-manga](https://github.com/FA-T-T/codex-noval-2-manga)** · ★ 5<br>Codex 小说改漫画 skill 套件：把小说改成漫画页脚本、视觉设计和角色参考图，再写成 GPT Image 2 直出页面的提示词<br><sub>阶段：改编</sub><br><sub>更新于 2026-05-02 · 英文 · 4 个 skill · Apache-2.0</sub><br><sub>💡 渲染需另装 gpt-image-2-skill</sub>


<details><summary>安装命令</summary>

```bash
# 默认命令基于 skills CLI，未逐个验证，以各仓库 README 为准
# novel-to-game
npx skills add zenstory-ai/novel-to-game
# novel_to_comic
npx skills add aiskyhub/novel_to_comic
# interactive-fiction-skill
npx skills add Treasure-hub-agent/interactive-fiction-skill
# velvet-ascent-skill
npx skills add ruijayfeng/velvet-ascent-skill
# codex-novel-to-comic-studio
npx skills add lhfer/codex-novel-to-comic-studio
# fanfic-roleplay-design
npx skills add unknowlei/fanfic-roleplay-design
# interactive-novel
npx skills add din1919/interactive-novel
# codex-noval-2-manga
npx skills add FA-T-T/codex-noval-2-manga
```

</details>

<a id="group-translate"></a>
### 翻译 · 出海

外文小说译成中文、网文译成外文出海，以及轻小说、视觉小说的翻译。

- **[AiNiee](https://github.com/NEKOparapa/AiNiee)** · ★ 6.4k<br>AI 翻译桌面工具：EPUB/TXT 小说、RPG 与 Ren'Py 游戏文本、字幕、文档，支持术语表、禁翻表、AI 润色<br><sub>阶段：翻译</sub><br><sub>更新于 2026-10-25 · 🧩 应用 · 中文 · AGPL-3.0</sub><br><sub>💡 AGPL-3.0。Release 是打包版，源码在仓库里。游戏文本要先用 MTool、Translator++ 等工具提取</sub>

- **[GalTransl](https://github.com/GalTransl/GalTransl)** · ★ 2.4k<br>Galgame 自动翻译工具：桌面 GUI 加 Agent 模式，GPT 字典、译前译后字典、断点续翻，也能翻 EPUB 和字幕<br><sub>阶段：翻译</sub><br><sub>更新于 2026-10-26 · 🧩 应用 · 中文 · GPL-3.0</sub><br><sub>💡 GPL-3.0。Release 有各平台打包版，源码在仓库里。解包和注入要配合 GARbro 等外部工具。作者要求：没经过全文校对就发布的，标明是 AI 翻译补丁</sub>

- **[ainiee-translate-skill](https://github.com/xuanji86/ainiee-translate-skill)** · ★ 34<br>让 agent 当翻译引擎的整书翻译插件：锁定术语表、断点续翻、多 agent 并行、对抗式审校，读写 EPUB/TXT/RPY 等格式<br><sub>阶段：翻译</sub><br><sub>更新于 2026-10-22 · 中文 · AGPL-3.0</sub><br><sub>💡 不限语言对，README 与示例以外文译中文为主。解析/导出模块改写自 NEKOparapa/AiNiee（AGPL），能导入 AiNiee 工程和 profile。要自建 Python venv，并设 SKILL_DIR、AINIEE_PY 环境变量</sub>

- **[chuanban-jp-novel-translator](https://github.com/Anarcadia/chuanban-jp-novel-translator)** · ★ 8<br>日译中长篇小说 skill 组：主调度串行派单章 subagent，维护术语表和章节摘要，断点续翻，审改分离润色，合并后做 EPUB<br><sub>阶段：翻译</sub><br><sub>更新于 2026-10-15 · 中文 · 11 个 skill · MIT</sub><br><sub>💡 作者推荐 Claude Opus，或走官方源的 DeepSeek-V4-Pro，其他来源容易被审核拒译。scripts/ 要留在包里，skill 中的 {SCRIPTS_DIR} 换成绝对路径。同作者另有 Proma 平台版</sub>

- **[codex-visual-novel-translation](https://github.com/9029kazuki/codex-visual-novel-translation)** · ★ 4<br>Galgame 日译简中 skill：调研引擎与解包，建术语和人设 Bible，按整场景翻译、独立审校，回封、诊断字体、实机 QA<br><sub>阶段：翻译</sub><br><sub>更新于 2026-09-07 · 中文 · 2 个 skill · MIT</sub><br><sub>💡 另附可配置语言对的英文版 skill。解包工具（如 GARbro）要自备，具体引擎得按游戏版本调研</sub>

- **[glossary-review-skill](https://github.com/oodadoudou/glossary-review-skill)** · ★ 1<br>韩中/日中小说术语表 xlsx 审查：逐词联网搜索并对照上下文，统一人名和组织译名，确认提案后写回<br><sub>阶段：翻译</sub><br><sub>更新于 2026-04-26 💤 · 中文 · MIT</sub><br><sub>💡 要准备参考原文 output_detail.txt 和 background.txt。确认后直接覆盖原 xlsx。最后一次提交在 2026-04，接近 6 个月线</sub>

- **[novel-convert-agent](https://github.com/NguyenVi07/novel-convert-agent)** · ★ 1<br>中文网文批量译成越南语 convert 体的项目模板：每批 10 章，自动维护人物、设定、剧情摘要和断点<br><sub>阶段：翻译</sub><br><sub>更新于 2026-10-03 · 英文</sub><br><sub>💡 作者只在 Antigravity 上测过。skill 在 .agents/skills/ 下，须按模板目录（i/、o/、data/）使用。面向越南读者</sub>

- **[renpy-translate](https://github.com/loggg4823-create/renpy-translate)** · ★ 1<br>Ren'Py 视觉小说汉化 skill 加脚本：分析项目、提取对白，调 DeepSeek/OpenAI/Claude 翻译，生成 tl 文件，断点续传<br><sub>阶段：翻译</sub><br><sub>更新于 2026-06-20 · 中文 · MIT</sub><br><sub>💡 翻译由脚本直接调 API，要自备 Key。仓库只有一次提交</sub>

- **[web-novel-library](https://github.com/Cheng-cheng9669/web-novel-library)** · ★ 1<br>连载网文增量翻译资料库：章节 SHA-256 清单，检测缺章和源文变更，标记过期译文，生成翻译计划并记录状态<br><sub>阶段：翻译</sub><br><sub>更新于 2026-08-14 · 英文 · MIT</sub><br><sub>💡 只导入本地章节文件，不带抓取器。翻译规范里有日轻译简中的要点</sub>

- **[galgame-skill](https://github.com/waw1w1/galgame-skill)** · ★ 0<br>Galgame／视觉小说译成中文的 skill：统一术语与称呼，保持多路线连续，分批自审、整线纠错，脚本检查 ID/变量/标签<br><sub>阶段：翻译</sub><br><sub>更新于 2026-09-30 · 中文</sub><br><sub>💡 仓库没有开源许可证。只有用户明确授权时才启用子代理</sub>

- **[jp-ln-ocr-epub-skill](https://github.com/Katiros/jp-ln-ocr-epub-skill)** · ★ 0<br>日轻竖排扫图用 PaddleOCR 识别，再用 DeepSeek 日译中、出 Word 审阅稿：术语表、ruby 处理、低置信重试、质量闸门<br><sub>阶段：翻译</sub><br><sub>更新于 2026-07-12 · 英文</sub><br><sub>💡 安装脚本只有 Windows PowerShell 版。EPUB 自动制作还没实现。wiki 术语导入默认指向《魔法禁书目录》的灰机 wiki，可以改</sub>

- **[novel-localization](https://github.com/tinrin-kiri/novel-localization)** · ★ 0<br>长篇小说本地化 skill 加项目模板：分类术语表、未决专名记录、逐章原文对照草稿，导出 TXT/HTML/EPUB<br><sub>阶段：翻译</sub><br><sub>更新于 2026-07-02 · 英文 · MIT</sub><br><sub>💡 模板默认译成简体中文。附带的成为小说家吧（なろう）脚本只抓目录。仓库只有一次提交</sub>

- **[novel-translate](https://github.com/MarkfuGod/novel-translate)** · ★ 0<br>Cursor skill：抓取 AO3、FanFiction.net、Royal Road、Wattpad 等站章节，经 OpenAI 兼容接口译成中文，可续跑<br><sub>阶段：翻译</sub><br><sub>更新于 2026-06-25 · 英文 · MIT</sub><br><sub>📚 Royal Road</sub><br><sub>💡 默认译成简中，可改。FanFiction.net 用 cloudscraper 绕过 Cloudflare；需要登录或付费的章节不处理。仓库只有一次提交</sub>

- **[translate-novel](https://github.com/yqrsmion/translate-novel)** · ★ 0<br>整本小说 txt 翻译 skill：边界感知切块、串行逐块翻译、段落 1:1 对齐加 V1–V12 校验、崩溃可续、确定性合并<br><sub>阶段：翻译</sub><br><sub>更新于 2026-10-06 · 中文 · MIT</sub><br><sub>💡 语言对用环境变量设定，内置日译简中的标点规范。只输出纯文本 txt。配了 NOVEL_LLM_* 时脚本会直接调 API</sub>

- **[zh-vi-novel-translation](https://github.com/duongmkqn005-ai/zh-vi-novel-translation)** · ★ 0<br>中文小说译越南语 skill：人名用汉越音，按说话方向定称呼，术语表与作品记忆，查证网络梗，校改 convert 稿<br><sub>阶段：翻译</sub><br><sub>更新于 2026-10-05 · 多语言 · MIT</sub><br><sub>💡 skill 正文和 README 是越南语，面向越南译者。另写了 Antigravity、Hermes 的装法。账号和仓库同一天创建</sub>


<details><summary>安装命令</summary>

```bash
# 默认命令基于 skills CLI，未逐个验证，以各仓库 README 为准
# ainiee-translate-skill
npx skills add xuanji86/ainiee-translate-skill
# chuanban-jp-novel-translator
npx skills add Anarcadia/chuanban-jp-novel-translator
# codex-visual-novel-translation
npx skills add 9029kazuki/codex-visual-novel-translation
# glossary-review-skill
npx skills add oodadoudou/glossary-review-skill
# novel-convert-agent
npx skills add NguyenVi07/novel-convert-agent
# renpy-translate
npx skills add loggg4823-create/renpy-translate
# web-novel-library
npx skills add Cheng-cheng9669/web-novel-library
# galgame-skill
npx skills add waw1w1/galgame-skill
# jp-ln-ocr-epub-skill
npx skills add Katiros/jp-ln-ocr-epub-skill
# novel-localization
npx skills add tinrin-kiri/novel-localization
# novel-translate
npx skills add MarkfuGod/novel-translate
# translate-novel
npx skills add yqrsmion/translate-novel
# zh-vi-novel-translation
npx skills add duongmkqn005-ai/zh-vi-novel-translation
```

</details>

<a id="group-sources"></a>
### 素材：小说下载 · 书源

拆书要先有原文。这里收下载小说、生成书源、抓取正文的工具，CLI 工具 agent 可以直接调用。

- **[Yuedu](https://github.com/XIU2/Yuedu)** · ★ 12.6k<br>「阅读」APP 书源合集：作者自用的 22 个精选小说书源（起点、番茄、69书吧等），提供网络导入和二维码导入<br><sub>阶段：选题</sub><br><sub>更新于 2026-08-14 · 🧩 应用 · 中文 · GPL-3.0</sub><br><sub>📚 起点 · 番茄</sub><br><sub>💡 需要配合 gedoor/legado（阅读 APP）使用；书源少，作者自己说维护不积极。在 APP 里缓存全本后可以导出 TXT</sub>

- **[legado](https://github.com/aoaostar/legado)** · ★ 7k<br>「阅读」App 书源合集：全量约 3900 条书源，另有订阅源、净化规则、排版和朗读引擎配置，一键导入<br><sub>阶段：选题</sub><br><sub>更新于 2026-10-26 · 🧩 应用 · 中文</sub><br><sub>💡 书源由机器人定时同步更新；Git 仓库不支持一键导入，从 legado.aoaostar.com 导入</sub>

- **[work_crawler](https://github.com/kanasimi/work_crawler)** · ★ 4.3k<br>Node.js 小说漫画批量下载器：小说部分覆盖起点、笔趣阁系、成为小说家吧、カクヨム等站，输出 EPUB，有 Electron 界面<br><sub>阶段：选题</sub><br><sub>更新于 2026-10-12 · 🧩 应用 · 多语言</sub><br><sub>📚 起点</sub><br><sub>💡 约六成站点模块是漫画。Release 安装包还停在 2022 年的 v2.14，近两年的修复要从源码运行才能用上</sub>

- **[Tomato-Novel-Downloader](https://github.com/zhongbai2333/Tomato-Novel-Downloader)** · ★ 4.1k<br>番茄小说下载器（Rust）：TUI 与 Web UI 搜索下载，导出 TXT/EPUB/PDF，可附段评、生成 Edge TTS 有声书<br><sub>阶段：选题</sub><br><sub>更新于 2026-10-17 · 🧩 应用 · 中文 · MIT</sub><br><sub>📚 番茄</sub><br><sub>💡 由 Dlmily/Tomato-Novel-Downloader-Lite 的 Python 版改写成 Rust，另加 EPUB、断点续传、搜索、Web UI。默认构建依赖不公开的 Official-API crate，第三方正文接口地址和 token 也不开源；公开源码用 Cargo_no_official.toml 构建，此模式没有搜索和段评。命令行只能更新已下载的书，新书要用 TUI 或 Web UI</sub>

- **[lightnovel-crawler](https://github.com/lncrawl/lightnovel-crawler)** · ★ 2.7k<br>英文网文/轻小说爬虫：361 个站点（含 Royal Road、Webnovel），一条命令生成 EPUB/TXT 等，另有自建 Web 书库与翻译<br><sub>阶段：选题</sub><br><sub>更新于 2026-10-23 · 🧩 应用 · 英文 · 7 个 skill · GPL-3.0</sub><br><sub>📚 Royal Road</sub><br><sub>💡 pip install lightnovel-crawler 安装。原仓库 dipu-bd/lightnovel-crawler，现在转到 lncrawl 组织，旧地址会自动跳转</sub>

- **[fanqienovel-downloader](https://github.com/ying-ck/fanqienovel-downloader)** · ★ 2.4k<br>番茄小说 Python 下载器：命令行按 ID/链接下载、搜索、批量和更新已下书目，另有 Web 版队列与在线阅读，导出 TXT/EPUB<br><sub>阶段：选题</sub><br><sub>更新于 2026-08-16 · 🧩 应用 · 中文 · AGPL-3.0</sub><br><sub>📚 番茄</sub><br><sub>💡 Web 版可以用 Docker 跑；Release 里的 exe 是打包版，源码在 src/。2026-07 社区 PR 改用 curl_cffi 应对反爬</sub>

- **[novel-downloader](https://github.com/404-novel-project/novel-downloader)** · ★ 2k<br>通用小说下载油猴脚本：在目录页一键下载，覆盖起点、晋江、番茄、七猫、SF、ESJ、轻小说文库等百余站，输出 TXT+EPUB<br><sub>阶段：选题</sub><br><sub>更新于 2026-10-19 · 🧩 应用 · 中文 · 2 个 skill · AGPL-3.0</sub><br><sub>📚 起点 · 晋江 · 番茄 · 七猫</sub><br><sub>💡 对无登录墙的站点，经你同意后会把详情页/目录页存档到 archive.org，并上报 IP、UA 等信息。晋江、番茄可能要手动做字体匹配，晋江章节可填 App token。仓库里的 .claude/skills 是维护者开发用的，不是写作 skill</sub>

- **[Novel](https://github.com/tickmao/Novel)** · ★ 2k<br>书源合集：阅读（Legado）约 1000 个、香色闺阁 1274 个书源，附净化规则、TTS 配置、字体和主题，Actions 每天校验<br><sub>阶段：选题</sub><br><sub>更新于 2026-10-26 · 🧩 应用 · 中文</sub><br><sub>💡 书源要先过自动运行校验才会发布；爱阅书香的书源链接到第三方仓库</sub>

- **[bilinovel-download](https://github.com/ShqWW/bilinovel-download)** · ★ 364<br>哔哩轻小说（linovelib）与哔哩漫画下载器：Fluent 风格 GUI 加命令行，按卷打包 EPUB，插图自动排版<br><sub>阶段：选题</sub><br><sub>更新于 2026-07-27 · 🧩 应用 · 中文</sub><br><sub>💡 只支持 Windows 10 及以上，要装 Edge 浏览器；从源码运行先 pip install -r requirements.txt</sub>

- **[legado-source-generator](https://github.com/z1131392774/legado-source-generator)** · ★ 248<br>Chrome/Firefox 扩展：在小说网页上点选元素，生成「阅读」书源的搜索、发现、详情、目录、正文规则并导出 JSON<br><sub>阶段：选题</sub><br><sub>更新于 2026-09-21 · 🧩 应用 · 中文 · MIT</sub><br><sub>💡 README 写明整个项目由 AI 辅助生成（vibe coding），建议用前自己看一遍代码。同作者另有让 AI 编写调试书源的 legado-book-source-skill</sub>

- **[go-novel-dl](https://github.com/guohuiyuan/go-novel-dl)** · ★ 235<br>Go 多站小说下载器：CLI、Web UI 和桌面壳，跨站聚合搜索，覆盖 ESJ、SF、刺猬猫、起点、番茄等，导出 TXT/EPUB/HTML<br><sub>阶段：选题</sub><br><sub>更新于 2026-10-23 · 🧩 应用 · 中文 · AGPL-3.0</sub><br><sub>📚 起点 · 番茄</sub><br><sub>💡 docs/architecture.md 写明沿用 Python 版 novel-downloader 的结构（应为 saudadez21/novel-downloader），这里用 Go 重写，另加了 Web UI、聚合搜索、书架和阅读器</sub>

- **[book-source-creator-skill](https://github.com/Narylr350/book-source-creator-skill)** · ★ 196<br>输入小说网站地址，分析站点结构生成「阅读/Legado」书源 JSON 或 JS，并验证搜索、详情、目录、正文四条链路<br><sub>阶段：选题</sub><br><sub>更新于 2026-08-17 · 中文</sub><br><sub>💡 推荐从 Releases 下载 zip，解压后把 legado-book-source-generator 放进 ~/.claude/skills 或 $CODEX_HOME/skills；验证环节可能用到 Java、adb 或安卓设备</sub>

- **[lightnovel-pydownloader](https://github.com/ilusrdbb/lightnovel-pydownloader)** · ★ 164<br>日轻翻译站爬虫：支持 ESJ、轻之国度、真白萌、百合会，按白名单或收藏批量导出 EPUB/TXT，有 CLI 和 GUI<br><sub>阶段：选题</sub><br><sub>更新于 2026-09-11 · 🧩 应用 · 中文 · MIT</sub><br><sub>💡 真白萌、百合会要用本机 Chrome 过 Cloudflare/WAF；作者提示 3.5.x 版本可能回退</sub>

- **[wenku8-downloader](https://github.com/Messiahhh/wenku8-downloader)** · ★ 160<br>轻小说文库命令行下载器（Node.js）：搜索、榜单、按 ID 下载，章节与插图断点续传，输出经 EPUBCheck 校验的 EPUB 3<br><sub>阶段：选题</sub><br><sub>更新于 2026-06-18 · 🧩 应用 · 中文</sub><br><sub>💡 npm install -g wenku8 安装；首次要 wenku8 login 粘贴 Cookie。只出 EPUB。2026-06 整体用 AI 重写过</sub>

- **[FanqieNovelDownloader](https://github.com/rainyautumn1/FanqieNovelDownloader)** · ★ 105<br>番茄小说桌面下载器（PySide6）：内置浏览器登录，单本按章节范围或按榜单批量下载，导出 TXT/EPUB/Markdown<br><sub>阶段：选题</sub><br><sub>更新于 2026-05-13 · 🧩 应用 · 中文 · GPL-3.0</sub><br><sub>📚 番茄</sub><br><sub>💡 最近一次提交是 2026-05 的 macOS 适配；完整内容要在内置浏览器里登录账号才能拿到</sub>

- **[esj-novel-downloader](https://github.com/mikoto710/esj-novel-downloader)** · ★ 49<br>ESJZone 油猴脚本：详情页和论坛页全本或按章节范围下载，导出 TXT/EPUB/HTML，含插图、断点续传和密码章节处理<br><sub>阶段：选题</sub><br><sub>更新于 2026-10-25 · 🧩 应用 · 中文 · MIT</sub><br><sub>💡 README 注明抓取逻辑参考 ZALin/ESJ-novel-backup。仓库里的 .codex/skills 是开发维护用的</sub>

- **[Yamibo_Downloader](https://github.com/RRRRUDDDD/Yamibo_Downloader)** · ★ 41<br>百合会论坛油猴脚本：按一楼目录或楼主楼层抓取连载帖、标签合集，按章节筛选后导出 EPUB3/TXT，含插图<br><sub>阶段：选题</sub><br><sub>更新于 2026-07-10 · 🧩 应用 · 中文 · MIT</sub>

- **[jjwxc-downloader](https://github.com/tracywong117/jjwxc-downloader)** · ★ 28<br>晋江文学城免费章节下载脚本：用 Selenium 抓成 TXT，附 TXT 转 EPUB（带封面和目录）<br><sub>阶段：选题</sub><br><sub>更新于 2026-06-28 · 🧩 应用 · 中文 · MIT</sub><br><sub>📚 晋江</sub><br><sub>💡 只能下免费章节，需自备与 Chrome 同版本的 ChromeDriver。2024 年以后只有 2026-06 一次修复提交</sub>

- **[wenku8-downloader](https://github.com/fateking27/wenku8-downloader)** · ★ 15<br>轻小说文库命令行下载器（Bun）：按 ID/书名/作者搜索或看榜单，整本或分卷导出 EPUB/TXT，可只下插图、配代理池<br><sub>阶段：选题</sub><br><sub>更新于 2026-09-09 · 🧩 应用 · 中文 · MIT</sub><br><sub>💡 和 Messiahhh/wenku8-downloader 同名但代码独立；这个多了 TXT 输出和已下架小说下载。Release 是打包好的 exe，也可 bun install 后从源码跑</sub>

- **[novelDownloader](https://github.com/nanachi1212/novelDownloader)** · ★ 12<br>通用小说下载器（Python）：GUI 下载队列加 CLI，适配 69书吧、多个台湾小说站和番茄，过滤广告后导出 TXT/EPUB<br><sub>阶段：选题</sub><br><sub>更新于 2026-10-22 · 🧩 应用 · 中文</sub><br><sub>📚 番茄</sub><br><sub>💡 界面和文档是繁体中文。番茄只有预览的章节，交给内附的 zhongbai2333/Tomato-Novel-Downloader v2.4.15 exe 取全文（仓库里也提交了这个 12MB exe，大小和 NOTICE 里的 SHA256 与上游 Release 一致）。2026-07 新建</sub>

- **[FXdownloader](https://github.com/halei0v0/FXdownloader)** · ★ 10<br>多源小说下载：八个站点（含番茄）聚合搜索、跨源分工下载与三层重试、番茄字体解密、断点续传，自带排行榜和阅读器<br><sub>阶段：选题</sub><br><sub>更新于 2026-07-26 · 🧩 应用 · 中文</sub><br><sub>📚 番茄</sub><br><sub>💡 Python 源码在仓库，Web 界面，也可用 Docker 运行；仓库里附带了下载好的示例小说和书库数据</sub>

- **[fanqie-novel-downloader-skill](https://github.com/yunmegnze/fanqie-novel-downloader-skill)** · ★ 5<br>番茄小说下载 skill：给阅读链接，经 Chrome CDP 逐章抓取，解码字体加密，按章存 TXT 并汇总成 JSON<br><sub>阶段：选题</sub><br><sub>更新于 2026-05-10 · 中文</sub><br><sub>📚 番茄</sub><br><sub>💡 需 Node.js 22+ 和 web-access skill 提供的 CDP 代理；字体映射表来自 ying-ck/fanqienovel-downloader；锁定章节需登录有权限的账号；README 安装地址少了 -skill 后缀</sub>


<details><summary>安装命令</summary>

```bash
# 默认命令基于 skills CLI，未逐个验证，以各仓库 README 为准
# book-source-creator-skill
npx skills add Narylr350/book-source-creator-skill
# fanqie-novel-downloader-skill
npx skills add yunmegnze/fanqie-novel-downloader-skill
```

</details>

<a id="group-apps"></a>
### 相关开源应用（完整应用，非 skill）

可自行部署的 AI 写小说应用，不是 skill，供对照参考。

- **[AI_NovelGenerator](https://github.com/YILING0013/AI_NovelGenerator)** · ★ 6.3k<br>本地部署的长篇小说生成应用：用雪花法从核心创意逐级展开卷、弧、场景、章纲到正文，管理角色/势力/物品/伏笔状态，AI 流程可在画布上改<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 记忆</sub><br><sub>更新于 2026-10-16 · 🧩 应用 · 多语言 · AGPL-3.0</sub><br><sub>💡 main 分支已经重写（Next.js + FastAPI + MongoDB），旧版留在 old 分支，两版数据不兼容</sub>

- **[AI-Novel-Writing-Assistant](https://github.com/ExplosiveCoderflome/AI-Novel-Writing-Assistant)** · ★ 3.3k<br>长篇小说创作工作台：自动导演从灵感推进到开书、世界观、角色、章节规划、正文与检查，含拆书、写法引擎、反 AI 规则、RAG 知识库和短篇流程<br><sub>阶段：选题 · 设定 · 人物 · 大纲 · 正文 · 记忆 · 审稿 · 改编</sub><br><sub>更新于 2026-10-24 · 🧩 应用 · 中文 · 2 个 skill</sub><br><sub>💡 有 Windows 桌面版，也能从源码部署；能把已写章节延展成漫画分镜和短剧素材。作者另有 ani-book-skill（已收）</sub>

- **[ainovel-cli](https://github.com/voocel/ainovel-cli)** · ★ 2.2k<br>全自动长篇小说生成 CLI：确定性引擎调度 Architect/Writer/Editor 三个代理，卷弧滚动规划、七维评审、步骤级断点恢复，可随时插入修改意见<br><sub>阶段：大纲 · 正文 · 记忆 · 审稿</sub><br><sub>更新于 2026-10-25 · 🧩 应用 · 中文 · Apache-2.0</sub><br><sub>💡 主打一句话全自动成书；想逐章把关可开 /review on。可在 TUI 里看着写，也可 headless 跑在服务器上</sub>

- **[AI-Novel-Writer](https://github.com/EthanYoQ/AI-Novel-Writer)** · ★ 1.8k<br>桌面长篇写作软件：前提、角色、世界观、章节蓝图、草稿、审稿、修稿、定稿逐段推进，可按阶段绑定写作 Skill，支持本地与在线模型<br><sub>阶段：设定 · 人物 · 大纲 · 正文 · 审稿</sub><br><sub>更新于 2026-10-26 · 🧩 应用 · 多语言 · GPL-3.0</sub><br><sub>💡 提供 Windows/macOS 桌面版；仓库里另有 DeepSeek Harness 插件预览版，已冻结，作者说它的能力不到桌面版一成</sub>

- **[NovelForge](https://github.com/RhythmicWave/NovelForge)** · ★ 1.3k<br>卡片式长篇创作工具：按 JSON Schema 结构化生成设定、角色、大纲卡片，用 @DSL 注入上下文、知识图谱保一致，可编排代码式工作流（含拆书）<br><sub>阶段：选题 · 设定 · 人物 · 大纲 · 正文 · 记忆</sub><br><sub>更新于 2026-09-23 · 🧩 应用 · 中文 · AGPL-3.0</sub>

- **[OpenFic](https://github.com/syrizelink/OpenFic)** · ★ 1.2k<br>人机协同的小说写作工具：写作编辑器加可自定义的 Prompt/Agent/工作流，维护设定、角色与伏笔，向量检索百万字项目，支持 Docker/pip/桌面版<br><sub>阶段：设定 · 人物 · 正文 · 记忆</sub><br><sub>更新于 2026-10-25 · 🧩 应用 · 多语言 · Apache-2.0</sub><br><sub>💡 定位是协同写作，不做一键成书。README 里有 API 中转商的推广链接</sub>


<a id="by-stage"></a>
## 按创作阶段查找

卡在某一步时，从这里找能帮上忙的 skill。「专项」只覆盖 3 个以内的阶段，「综合」是全流程或多环节项目；各自按星数排序。

**选题 · 扫榜 · 拆书**（56）

- 专项（26）：[Yuedu](https://github.com/XIU2/Yuedu) · [legado](https://github.com/aoaostar/legado) · [work_crawler](https://github.com/kanasimi/work_crawler) · [Tomato-Novel-Downloader](https://github.com/zhongbai2333/Tomato-Novel-Downloader) · [lightnovel-crawler](https://github.com/lncrawl/lightnovel-crawler) · [fanqienovel-downloader](https://github.com/ying-ck/fanqienovel-downloader) · [novel-downloader](https://github.com/404-novel-project/novel-downloader) · [Novel](https://github.com/tickmao/Novel) · [bilinovel-download](https://github.com/ShqWW/bilinovel-download) · [legado-source-generator](https://github.com/z1131392774/legado-source-generator) · [go-novel-dl](https://github.com/guohuiyuan/go-novel-dl) · [book-source-creator-skill](https://github.com/Narylr350/book-source-creator-skill) · [lightnovel-pydownloader](https://github.com/ilusrdbb/lightnovel-pydownloader) · [wenku8-downloader](https://github.com/Messiahhh/wenku8-downloader) · [narrative-to-screen-reader](https://github.com/zhlmi/narrative-to-screen-reader) · [FanqieNovelDownloader](https://github.com/rainyautumn1/FanqieNovelDownloader) · [esj-novel-downloader](https://github.com/mikoto710/esj-novel-downloader) · [Yamibo_Downloader](https://github.com/RRRRUDDDD/Yamibo_Downloader) · [jjwxc-downloader](https://github.com/tracywong117/jjwxc-downloader) · [wenfeng-skill](https://github.com/XTmingyue/wenfeng-skill) · [analyze-hit-novel](https://github.com/ciel-oliver/analyze-hit-novel) · [wenku8-downloader](https://github.com/fateking27/wenku8-downloader) · [fanqie-radar](https://github.com/WindXRan/fanqie-radar) · [novelDownloader](https://github.com/nanachi1212/novelDownloader) · [FXdownloader](https://github.com/halei0v0/FXdownloader) · [fanqie-novel-downloader-skill](https://github.com/yunmegnze/fanqie-novel-downloader-skill)
- 综合（30）：[inkos](https://github.com/Narcooo/inkos) · [oh-story-claudecode](https://github.com/zenstory-ai/oh-story-claudecode) · [webnovel-writer](https://github.com/lingfengQAQ/webnovel-writer) · [Chinese-WebNovel-Skill](https://github.com/Tomsawyerhu/Chinese-WebNovel-Skill) · [oh-story-dsh](https://github.com/zenstory-ai/oh-story-dsh) · [screen-creative-skills](https://github.com/VanGong1999/screen-creative-skills) · [Lorn.NovelWriteSkills](https://github.com/lornshrimp/Lorn.NovelWriteSkills) · [sumeru](https://github.com/xindoo/sumeru) · [bookflow-skill](https://github.com/LanyXiaosheng/bookflow-skill) · [Distilled-Novel-Toolbox](https://github.com/dama-cyber/Distilled-Novel-Toolbox) · [chinese-webnovel-skills](https://github.com/tance-mang/chinese-webnovel-skills) · [DaisyWriter](https://github.com/ricky-theseus/DaisyWriter) · [chinese-longnovel-skill](https://github.com/xiaofeng-928/chinese-longnovel-skill) · [ai-short-drama](https://github.com/Hao0321/ai-short-drama) · [oh-story-claudecode](https://github.com/qin1473692580-ux/oh-story-claudecode) · [ai-fiction-writer](https://github.com/Wooooooooood/ai-fiction-writer) · [xt-webnovel-writing](https://github.com/xiaotiewinner/xt-webnovel-writing) · [webfiction-write](https://github.com/qingyabailu-git/webfiction-write) · [fanqie-short-story.skill](https://github.com/aby-aby111/fanqie-short-story.skill) · [wangwen-writing-skill-kit](https://github.com/hyi1233/wangwen-writing-skill-kit) · [novel-assistant-skill](https://github.com/duiniwukenaihe/novel-assistant-skill) · [human-novel-writer](https://github.com/huahuakandaima/human-novel-writer) · [wangwenwrite-skill](https://github.com/Thatgfsj-easyRep/wangwenwrite-skill) · [novel-writer-skill](https://github.com/liuxiao20051106-prog/novel-writer-skill) · [general-novel-skill](https://github.com/xiaoyuCR7/general-novel-skill) · [open-novel-fanqie](https://github.com/kongxcer555/open-novel-fanqie) · [web-novel-master](https://github.com/tinylion1024/web-novel-master) · [novel-craft](https://github.com/dongyanyuxuana/novel-craft) · [novel-engine](https://github.com/jiangying3222880/novel-engine) · [emma-screenwriting-skills](https://github.com/adoria111/emma-screenwriting-skills)

**设定 · 世界观**（45）

- 专项（3）：[novel-to-game](https://github.com/zenstory-ai/novel-to-game) · [Fanfic-background-assistant](https://github.com/Elowwwen/Fanfic-background-assistant) · [fanfic-roleplay-design](https://github.com/unknowlei/fanfic-roleplay-design)
- 综合（42）：[webnovel-writer](https://github.com/lingfengQAQ/webnovel-writer) · [awesome-novel-agent](https://github.com/modoojunko/awesome-novel-agent) · [oh-story-dsh](https://github.com/zenstory-ai/oh-story-dsh) · [story-skills](https://github.com/danjdewhurst/story-skills) · [Lorn.NovelWriteSkills](https://github.com/lornshrimp/Lorn.NovelWriteSkills) · [webnovel-writer-opencode](https://github.com/lujih/webnovel-writer-opencode) · [sumeru](https://github.com/xindoo/sumeru) · [Distilled-Novel-Toolbox](https://github.com/dama-cyber/Distilled-Novel-Toolbox) · [agent-skills](https://github.com/jwynia/agent-skills) · [awesome-novel-studio](https://github.com/MJbae/awesome-novel-studio) · [tianming-skill](https://github.com/zy-zmc/tianming-skill) · [novel-harness](https://github.com/manhai934/novel-harness) · [long-novel-writer](https://github.com/jiaw-Zh/long-novel-writer) · [chinese-webnovel-skills](https://github.com/tance-mang/chinese-webnovel-skills) · [DaisyWriter](https://github.com/ricky-theseus/DaisyWriter) · [chinese-longnovel-skill](https://github.com/xiaofeng-928/chinese-longnovel-skill) · [dreampowers](https://github.com/skyfiredao/dreampowers) · [ai-fiction-writer](https://github.com/Wooooooooood/ai-fiction-writer) · [ultimate-novel-creation-skill](https://github.com/Fly143/ultimate-novel-creation-skill) · [novel-master](https://github.com/bbroot/novel-master) · [vibe-noveling](https://github.com/TulanCN/vibe-noveling) · [book-writer-skill](https://github.com/kshanxs/book-writer-skill) · [webfiction-write](https://github.com/qingyabailu-git/webfiction-write) · [novel-flow-one-by-one](https://github.com/ZhangDongyang800/novel-flow-one-by-one) · [long-novelist-skill](https://github.com/tianshiemo7/long-novelist-skill) · [silver-novel-skills](https://github.com/jialanhu0915/silver-novel-skills) · [plotrail](https://github.com/waylean/plotrail) · [novel-assistant-skill](https://github.com/duiniwukenaihe/novel-assistant-skill) · [human-novel-writer](https://github.com/huahuakandaima/human-novel-writer) · [wangwenwrite-skill](https://github.com/Thatgfsj-easyRep/wangwenwrite-skill) · [general-novel-skill](https://github.com/xiaoyuCR7/general-novel-skill) · [novel-webfiction](https://github.com/zlbigger/novel-webfiction) · [open-novel-fanqie](https://github.com/kongxcer555/open-novel-fanqie) · [web-novel-master](https://github.com/tinylion1024/web-novel-master) · [chinese-novelist-skill](https://github.com/lvyu-cmd/chinese-novelist-skill) · [web-novel-writing-skill](https://github.com/XINGANLIU/web-novel-writing-skill) · [novelist-skill](https://github.com/chanceline-max/novelist-skill) · [novel-craft](https://github.com/dongyanyuxuana/novel-craft) · [fanqie-xiaoshuo-skill](https://github.com/soultt/fanqie-xiaoshuo-skill) · [novel-engine](https://github.com/jiangying3222880/novel-engine) · [Creative-writing-skill](https://github.com/xbraindance/Creative-writing-skill) · [AutoWriter](https://github.com/sinfiny/AutoWriter)

**人物 · 关系**（72）

- 专项（21）：[shanyin-screenwriting-master](https://github.com/Shanyin-ai/shanyin-screenwriting-master) · [XiaoLuo-AI-Drama-Skill](https://github.com/zhurui0523/XiaoLuo-AI-Drama-Skill) · [narrative-to-screen-reader](https://github.com/zhlmi/narrative-to-screen-reader) · [novel-to-manju](https://github.com/senmanx/novel-to-manju) · [acheng-director-skill](https://github.com/AharaOoO/acheng-director-skill) · [ai-short-drama](https://github.com/oiuv/ai-short-drama) · [open-source-video-gen-skill](https://github.com/mini-yifan/open-source-video-gen-skill) · [jingju-skills](https://github.com/jxshow/jingju-skills) · [spark-video](https://github.com/JohnKeating1997/spark-video) · [velvet-ascent-skill](https://github.com/ruijayfeng/velvet-ascent-skill) · [5min-drama-contest](https://github.com/SoloEnt-AI/5min-drama-contest) · [soul-killer](https://github.com/Xeonice/soul-killer) · [ShortVideoDirector](https://github.com/wddxh/ShortVideoDirector) · [fanfic-roleplay-design](https://github.com/unknowlei/fanfic-roleplay-design) · [Comfy-H3-Director](https://github.com/MIKA6941/Comfy-H3-Director) · [vision_art_creator](https://github.com/ilkaydemiralay/vision_art_creator) · [ai-comic-drama-director-skills](https://github.com/djyy1031/ai-comic-drama-director-skills) · [chinese-epic-scene-director](https://github.com/zhouwei713/chinese-epic-scene-director) · [claude-screenwriting](https://github.com/e06084/claude-screenwriting) · [writing-skills](https://github.com/Calliope-Editor/writing-skills) · [character-card-fiction-workflow-skill](https://github.com/shigehaomingzi1/character-card-fiction-workflow-skill)
- 综合（51）：[webnovel-writer](https://github.com/lingfengQAQ/webnovel-writer) · [shuohao-skills](https://github.com/eternityspring/shuohao-skills) · [drama-skills](https://github.com/zenstory-ai/drama-skills) · [screenwriting-skills](https://github.com/jtydhr88/screenwriting-skills) · [Chinese-WebNovel-Skill](https://github.com/Tomsawyerhu/Chinese-WebNovel-Skill) · [awesome-novel-agent](https://github.com/modoojunko/awesome-novel-agent) · [oh-story-dsh](https://github.com/zenstory-ai/oh-story-dsh) · [screen-creative-skills](https://github.com/VanGong1999/screen-creative-skills) · [story-skills](https://github.com/danjdewhurst/story-skills) · [Lorn.NovelWriteSkills](https://github.com/lornshrimp/Lorn.NovelWriteSkills) · [webnovel-writer-opencode](https://github.com/lujih/webnovel-writer-opencode) · [sumeru](https://github.com/xindoo/sumeru) · [bookflow-skill](https://github.com/LanyXiaosheng/bookflow-skill) · [Distilled-Novel-Toolbox](https://github.com/dama-cyber/Distilled-Novel-Toolbox) · [agent-skills](https://github.com/jwynia/agent-skills) · [awesome-novel-studio](https://github.com/MJbae/awesome-novel-studio) · [tianming-skill](https://github.com/zy-zmc/tianming-skill) · [novel-harness](https://github.com/manhai934/novel-harness) · [long-novel-writer](https://github.com/jiaw-Zh/long-novel-writer) · [chinese-webnovel-skills](https://github.com/tance-mang/chinese-webnovel-skills) · [DaisyWriter](https://github.com/ricky-theseus/DaisyWriter) · [dreampowers](https://github.com/skyfiredao/dreampowers) · [ai-fiction-writer](https://github.com/Wooooooooood/ai-fiction-writer) · [ultimate-novel-creation-skill](https://github.com/Fly143/ultimate-novel-creation-skill) · [novel-master](https://github.com/bbroot/novel-master) · [vibe-noveling](https://github.com/TulanCN/vibe-noveling) · [book-writer-skill](https://github.com/kshanxs/book-writer-skill) · [xt-webnovel-writing](https://github.com/xiaotiewinner/xt-webnovel-writing) · [webfiction-write](https://github.com/qingyabailu-git/webfiction-write) · [hardcore-director](https://github.com/jlam00-dev/hardcore-director) · [novel-flow-one-by-one](https://github.com/ZhangDongyang800/novel-flow-one-by-one) · [ai-manga-drama](https://github.com/liuxiao20051106-prog/ai-manga-drama) · [long-novelist-skill](https://github.com/tianshiemo7/long-novelist-skill) · [silver-novel-skills](https://github.com/jialanhu0915/silver-novel-skills) · [wangwen-writing-skill-kit](https://github.com/hyi1233/wangwen-writing-skill-kit) · [plotrail](https://github.com/waylean/plotrail) · [novel-assistant-skill](https://github.com/duiniwukenaihe/novel-assistant-skill) · [human-novel-writer](https://github.com/huahuakandaima/human-novel-writer) · [novel-writer-skill](https://github.com/liuxiao20051106-prog/novel-writer-skill) · [general-novel-skill](https://github.com/xiaoyuCR7/general-novel-skill) · [open-novel-fanqie](https://github.com/kongxcer555/open-novel-fanqie) · [web-novel-master](https://github.com/tinylion1024/web-novel-master) · [chinese-novelist-skill](https://github.com/lvyu-cmd/chinese-novelist-skill) · [web-novel-writing-skill](https://github.com/XINGANLIU/web-novel-writing-skill) · [novelist-skill](https://github.com/chanceline-max/novelist-skill) · [novel-craft](https://github.com/dongyanyuxuana/novel-craft) · [fanqie-xiaoshuo-skill](https://github.com/soultt/fanqie-xiaoshuo-skill) · [novel-engine](https://github.com/jiangying3222880/novel-engine) · [Creative-writing-skill](https://github.com/xbraindance/Creative-writing-skill) · [AutoWriter](https://github.com/sinfiny/AutoWriter) · [novel-craft](https://github.com/chaserr/novel-craft)

**大纲 · 章纲 · 伏笔**（86）

- 专项（19）：[shanyin-screenwriting-master](https://github.com/Shanyin-ai/shanyin-screenwriting-master) · [novel-writing-framework](https://github.com/LAY-lgtm/novel-writing-framework) · [short-drama-production](https://github.com/suihe1/short-drama-production) · [chinese-erotic-fiction-writing](https://github.com/xWebt/chinese-erotic-fiction-writing) · [novel-writing](https://github.com/wgwtest/novel-writing) · [qianqianwriting](https://github.com/catyiqian/qianqianwriting) · [ai-short-drama](https://github.com/oiuv/ai-short-drama) · [open-source-video-gen-skill](https://github.com/mini-yifan/open-source-video-gen-skill) · [jingju-skills](https://github.com/jxshow/jingju-skills) · [5min-drama-contest](https://github.com/SoloEnt-AI/5min-drama-contest) · [sun-yuchen-writing](https://github.com/AAAAAAAJ/sun-yuchen-writing) · [ManjuForge](https://github.com/mengxiujie/ManjuForge) · [write-chinese-long-screenplay](https://github.com/mudden2380078550-creator/write-chinese-long-screenplay) · [ShortVideoDirector](https://github.com/wddxh/ShortVideoDirector) · [claude-screenwriting](https://github.com/e06084/claude-screenwriting) · [inkcraft-writing-skills](https://github.com/Fei2411/inkcraft-writing-skills) · [kunka-screenwriting-master](https://github.com/geslie1/kunka-screenwriting-master) · [gushi-skill](https://github.com/pipivv/gushi-skill) · [hongguo-shortdrama-screenwriting](https://github.com/zhu5859243-free/hongguo-shortdrama-screenwriting)
- 综合（67）：[inkos](https://github.com/Narcooo/inkos) · [oh-story-claudecode](https://github.com/zenstory-ai/oh-story-claudecode) · [webnovel-writer](https://github.com/lingfengQAQ/webnovel-writer) · [shuohao-skills](https://github.com/eternityspring/shuohao-skills) · [chinese-novelist-skill](https://github.com/PenglongHuang/chinese-novelist-skill) · [screenwriting-skills](https://github.com/jtydhr88/screenwriting-skills) · [Chinese-WebNovel-Skill](https://github.com/Tomsawyerhu/Chinese-WebNovel-Skill) · [awesome-novel-agent](https://github.com/modoojunko/awesome-novel-agent) · [oh-story-dsh](https://github.com/zenstory-ai/oh-story-dsh) · [creative-writing-skills](https://github.com/haowjy/creative-writing-skills) · [screen-creative-skills](https://github.com/VanGong1999/screen-creative-skills) · [short-drama-factory](https://github.com/lixiaoxiao9888-create/short-drama-factory) · [story-skills](https://github.com/danjdewhurst/story-skills) · [Lorn.NovelWriteSkills](https://github.com/lornshrimp/Lorn.NovelWriteSkills) · [webnovel-writer-opencode](https://github.com/lujih/webnovel-writer-opencode) · [sumeru](https://github.com/xindoo/sumeru) · [bookflow-skill](https://github.com/LanyXiaosheng/bookflow-skill) · [Distilled-Novel-Toolbox](https://github.com/dama-cyber/Distilled-Novel-Toolbox) · [agent-skills](https://github.com/jwynia/agent-skills) · [awesome-novel-studio](https://github.com/MJbae/awesome-novel-studio) · [tianming-skill](https://github.com/zy-zmc/tianming-skill) · [novel-harness](https://github.com/manhai934/novel-harness) · [ani-book-skill](https://github.com/ExplosiveCoderflome/ani-book-skill) · [long-novel-writer](https://github.com/jiaw-Zh/long-novel-writer) · [chinese-webnovel-skills](https://github.com/tance-mang/chinese-webnovel-skills) · [fanqie-novel-skill](https://github.com/304769384-png/fanqie-novel-skill) · [DaisyWriter](https://github.com/ricky-theseus/DaisyWriter) · [chinese-longnovel-skill](https://github.com/xiaofeng-928/chinese-longnovel-skill) · [dreampowers](https://github.com/skyfiredao/dreampowers) · [ai-short-drama](https://github.com/Hao0321/ai-short-drama) · [oh-story-claudecode](https://github.com/qin1473692580-ux/oh-story-claudecode) · [ai-fiction-writer](https://github.com/Wooooooooood/ai-fiction-writer) · [ultimate-novel-creation-skill](https://github.com/Fly143/ultimate-novel-creation-skill) · [novelops-skill](https://github.com/qiyan233/novelops-skill) · [novel-master](https://github.com/bbroot/novel-master) · [vibe-noveling](https://github.com/TulanCN/vibe-noveling) · [book-writer-skill](https://github.com/kshanxs/book-writer-skill) · [xt-webnovel-writing](https://github.com/xiaotiewinner/xt-webnovel-writing) · [webfiction-write](https://github.com/qingyabailu-git/webfiction-write) · [hardcore-director](https://github.com/jlam00-dev/hardcore-director) · [novel-flow-one-by-one](https://github.com/ZhangDongyang800/novel-flow-one-by-one) · [fanqie-short-story.skill](https://github.com/aby-aby111/fanqie-short-story.skill) · [ai-manga-drama](https://github.com/liuxiao20051106-prog/ai-manga-drama) · [long-novelist-skill](https://github.com/tianshiemo7/long-novelist-skill) · [silver-novel-skills](https://github.com/jialanhu0915/silver-novel-skills) · [opencreator-novel](https://github.com/xwcai999/opencreator-novel) · [wangwen-writing-skill-kit](https://github.com/hyi1233/wangwen-writing-skill-kit) · [plotrail](https://github.com/waylean/plotrail) · [novel-assistant-skill](https://github.com/duiniwukenaihe/novel-assistant-skill) · [human-novel-writer](https://github.com/huahuakandaima/human-novel-writer) · [wangwenwrite-skill](https://github.com/Thatgfsj-easyRep/wangwenwrite-skill) · [novel-writing-skill](https://github.com/cnskycn/novel-writing-skill) · [novel-writer-skill](https://github.com/liuxiao20051106-prog/novel-writer-skill) · [general-novel-skill](https://github.com/xiaoyuCR7/general-novel-skill) · [novel-webfiction](https://github.com/zlbigger/novel-webfiction) · [open-novel-fanqie](https://github.com/kongxcer555/open-novel-fanqie) · [web-novel-master](https://github.com/tinylion1024/web-novel-master) · [chinese-novelist-skill](https://github.com/lvyu-cmd/chinese-novelist-skill) · [web-novel-writing-skill](https://github.com/XINGANLIU/web-novel-writing-skill) · [novelist-skill](https://github.com/chanceline-max/novelist-skill) · [novel-craft](https://github.com/dongyanyuxuana/novel-craft) · [fanqie-xiaoshuo-skill](https://github.com/soultt/fanqie-xiaoshuo-skill) · [novel-engine](https://github.com/jiangying3222880/novel-engine) · [Creative-writing-skill](https://github.com/xbraindance/Creative-writing-skill) · [AutoWriter](https://github.com/sinfiny/AutoWriter) · [novel-craft](https://github.com/chaserr/novel-craft) · [emma-screenwriting-skills](https://github.com/adoria111/emma-screenwriting-skills)

**正文 · 续写**（114）

- 专项（47）：[Seedance2-Storyboard-Generator](https://github.com/liangdabiao/Seedance2-Storyboard-Generator) · [manju-laoli-skill](https://github.com/lixiaoxiao9888-create/manju-laoli-skill) · [shanyin-screenwriting-master](https://github.com/Shanyin-ai/shanyin-screenwriting-master) · [seedance-2-5-video-director](https://github.com/liyue-aigc/seedance-2-5-video-director) · [XiaoLuo-AI-Drama-Skill](https://github.com/zhurui0523/XiaoLuo-AI-Drama-Skill) · [OnlyShot](https://github.com/A-cat-with-carrots/OnlyShot) · [Micro-Drama-Skills](https://github.com/zhaihao118/Micro-Drama-Skills) · [novel-writing-framework](https://github.com/LAY-lgtm/novel-writing-framework) · [smy-seedance-storyboard](https://github.com/liangdabiao/smy-seedance-storyboard) · [short-drama-production](https://github.com/suihe1/short-drama-production) · [qisi-video-remix](https://github.com/wyuzhi/qisi-video-remix) · [workrally](https://github.com/Tencent/workrally) · [film-studio-skills](https://github.com/machina-exm/film-studio-skills) · [fight-video-create-skill](https://github.com/qualsenWeb/fight-video-create-skill) · [short-drama-skills](https://github.com/YvonneMovingon/short-drama-skills) · [ai-short-drama-skill](https://github.com/xixihhhh/ai-short-drama-skill) · [novel-to-manju](https://github.com/senmanx/novel-to-manju) · [chinese-erotic-fiction-writing](https://github.com/xWebt/chinese-erotic-fiction-writing) · [novel-writing](https://github.com/wgwtest/novel-writing) · [qianqianwriting](https://github.com/catyiqian/qianqianwriting) · [acheng-director-skill](https://github.com/AharaOoO/acheng-director-skill) · [muse-video-skill](https://github.com/LuoJiangYong/muse-video-skill) · [lengdu](https://github.com/asass-11/lengdu) · [ai-short-drama](https://github.com/oiuv/ai-short-drama) · [open-source-video-gen-skill](https://github.com/mini-yifan/open-source-video-gen-skill) · [jingju-skills](https://github.com/jxshow/jingju-skills) · [interactive-fiction-skill](https://github.com/Treasure-hub-agent/interactive-fiction-skill) · [spark-video](https://github.com/JohnKeating1997/spark-video) · [xin-skills](https://github.com/oscar-wang-xin/xin-skills) · [velvet-ascent-skill](https://github.com/ruijayfeng/velvet-ascent-skill) · [5min-drama-contest](https://github.com/SoloEnt-AI/5min-drama-contest) · [short-drama-director](https://github.com/UncleWang2088/short-drama-director) · [sun-yuchen-writing](https://github.com/AAAAAAAJ/sun-yuchen-writing) · [ManjuForge](https://github.com/mengxiujie/ManjuForge) · [write-chinese-long-screenplay](https://github.com/mudden2380078550-creator/write-chinese-long-screenplay) · [wenfeng-skill](https://github.com/XTmingyue/wenfeng-skill) · [vision_art_creator](https://github.com/ilkaydemiralay/vision_art_creator) · [chinese-epic-scene-director](https://github.com/zhouwei713/chinese-epic-scene-director) · [fictional-erotica](https://github.com/rs-skills-lab/fictional-erotica) · [horror-weird-fiction-skill](https://github.com/EnderRomantice/horror-weird-fiction-skill) · [inkcraft-writing-skills](https://github.com/Fei2411/inkcraft-writing-skills) · [kunka-screenwriting-master](https://github.com/geslie1/kunka-screenwriting-master) · [gushi-skill](https://github.com/pipivv/gushi-skill) · [write-screenplay-skill](https://github.com/egguy886/write-screenplay-skill) · [character-card-fiction-workflow-skill](https://github.com/shigehaomingzi1/character-card-fiction-workflow-skill) · [jiamama-bedtime-story-skill](https://github.com/leonluo2008-ops/jiamama-bedtime-story-skill) · [hongguo-shortdrama-screenwriting](https://github.com/zhu5859243-free/hongguo-shortdrama-screenwriting)
- 综合（67）：[inkos](https://github.com/Narcooo/inkos) · [oh-story-claudecode](https://github.com/zenstory-ai/oh-story-claudecode) · [webnovel-writer](https://github.com/lingfengQAQ/webnovel-writer) · [shuohao-skills](https://github.com/eternityspring/shuohao-skills) · [chinese-novelist-skill](https://github.com/PenglongHuang/chinese-novelist-skill) · [drama-skills](https://github.com/zenstory-ai/drama-skills) · [screenwriting-skills](https://github.com/jtydhr88/screenwriting-skills) · [Chinese-WebNovel-Skill](https://github.com/Tomsawyerhu/Chinese-WebNovel-Skill) · [awesome-novel-agent](https://github.com/modoojunko/awesome-novel-agent) · [oh-story-dsh](https://github.com/zenstory-ai/oh-story-dsh) · [creative-writing-skills](https://github.com/haowjy/creative-writing-skills) · [short-drama-factory](https://github.com/lixiaoxiao9888-create/short-drama-factory) · [story-skills](https://github.com/danjdewhurst/story-skills) · [Lorn.NovelWriteSkills](https://github.com/lornshrimp/Lorn.NovelWriteSkills) · [webnovel-writer-opencode](https://github.com/lujih/webnovel-writer-opencode) · [sumeru](https://github.com/xindoo/sumeru) · [bookflow-skill](https://github.com/LanyXiaosheng/bookflow-skill) · [Distilled-Novel-Toolbox](https://github.com/dama-cyber/Distilled-Novel-Toolbox) · [agent-skills](https://github.com/jwynia/agent-skills) · [awesome-novel-studio](https://github.com/MJbae/awesome-novel-studio) · [tianming-skill](https://github.com/zy-zmc/tianming-skill) · [novel-harness](https://github.com/manhai934/novel-harness) · [ani-book-skill](https://github.com/ExplosiveCoderflome/ani-book-skill) · [long-novel-writer](https://github.com/jiaw-Zh/long-novel-writer) · [chinese-webnovel-skills](https://github.com/tance-mang/chinese-webnovel-skills) · [fanqie-novel-skill](https://github.com/304769384-png/fanqie-novel-skill) · [DaisyWriter](https://github.com/ricky-theseus/DaisyWriter) · [chinese-longnovel-skill](https://github.com/xiaofeng-928/chinese-longnovel-skill) · [dreampowers](https://github.com/skyfiredao/dreampowers) · [ai-short-drama](https://github.com/Hao0321/ai-short-drama) · [oh-story-claudecode](https://github.com/qin1473692580-ux/oh-story-claudecode) · [ai-fiction-writer](https://github.com/Wooooooooood/ai-fiction-writer) · [ultimate-novel-creation-skill](https://github.com/Fly143/ultimate-novel-creation-skill) · [novelops-skill](https://github.com/qiyan233/novelops-skill) · [novel-master](https://github.com/bbroot/novel-master) · [vibe-noveling](https://github.com/TulanCN/vibe-noveling) · [book-writer-skill](https://github.com/kshanxs/book-writer-skill) · [xt-webnovel-writing](https://github.com/xiaotiewinner/xt-webnovel-writing) · [webfiction-write](https://github.com/qingyabailu-git/webfiction-write) · [hardcore-director](https://github.com/jlam00-dev/hardcore-director) · [novel-flow-one-by-one](https://github.com/ZhangDongyang800/novel-flow-one-by-one) · [fanqie-short-story.skill](https://github.com/aby-aby111/fanqie-short-story.skill) · [ai-manga-drama](https://github.com/liuxiao20051106-prog/ai-manga-drama) · [long-novelist-skill](https://github.com/tianshiemo7/long-novelist-skill) · [silver-novel-skills](https://github.com/jialanhu0915/silver-novel-skills) · [opencreator-novel](https://github.com/xwcai999/opencreator-novel) · [wangwen-writing-skill-kit](https://github.com/hyi1233/wangwen-writing-skill-kit) · [plotrail](https://github.com/waylean/plotrail) · [novel-assistant-skill](https://github.com/duiniwukenaihe/novel-assistant-skill) · [human-novel-writer](https://github.com/huahuakandaima/human-novel-writer) · [wangwenwrite-skill](https://github.com/Thatgfsj-easyRep/wangwenwrite-skill) · [novel-writing-skill](https://github.com/cnskycn/novel-writing-skill) · [novel-writer-skill](https://github.com/liuxiao20051106-prog/novel-writer-skill) · [general-novel-skill](https://github.com/xiaoyuCR7/general-novel-skill) · [novel-webfiction](https://github.com/zlbigger/novel-webfiction) · [open-novel-fanqie](https://github.com/kongxcer555/open-novel-fanqie) · [web-novel-master](https://github.com/tinylion1024/web-novel-master) · [chinese-novelist-skill](https://github.com/lvyu-cmd/chinese-novelist-skill) · [web-novel-writing-skill](https://github.com/XINGANLIU/web-novel-writing-skill) · [novelist-skill](https://github.com/chanceline-max/novelist-skill) · [novel-craft](https://github.com/dongyanyuxuana/novel-craft) · [fanqie-xiaoshuo-skill](https://github.com/soultt/fanqie-xiaoshuo-skill) · [novel-engine](https://github.com/jiangying3222880/novel-engine) · [Creative-writing-skill](https://github.com/xbraindance/Creative-writing-skill) · [AutoWriter](https://github.com/sinfiny/AutoWriter) · [novel-craft](https://github.com/chaserr/novel-craft) · [emma-screenwriting-skills](https://github.com/adoria111/emma-screenwriting-skills)

**长篇记忆 · 一致性（防吃书、防 OOC）**（46）

- 专项（2）：[velvet-ascent-skill](https://github.com/ruijayfeng/velvet-ascent-skill) · [novel-project-strategy](https://github.com/wgwtest/novel-project-strategy)
- 综合（44）：[inkos](https://github.com/Narcooo/inkos) · [webnovel-writer](https://github.com/lingfengQAQ/webnovel-writer) · [chinese-novelist-skill](https://github.com/PenglongHuang/chinese-novelist-skill) · [Chinese-WebNovel-Skill](https://github.com/Tomsawyerhu/Chinese-WebNovel-Skill) · [creative-writing-skills](https://github.com/haowjy/creative-writing-skills) · [story-skills](https://github.com/danjdewhurst/story-skills) · [webnovel-writer-opencode](https://github.com/lujih/webnovel-writer-opencode) · [sumeru](https://github.com/xindoo/sumeru) · [tianming-skill](https://github.com/zy-zmc/tianming-skill) · [novel-harness](https://github.com/manhai934/novel-harness) · [ani-book-skill](https://github.com/ExplosiveCoderflome/ani-book-skill) · [long-novel-writer](https://github.com/jiaw-Zh/long-novel-writer) · [chinese-webnovel-skills](https://github.com/tance-mang/chinese-webnovel-skills) · [fanqie-novel-skill](https://github.com/304769384-png/fanqie-novel-skill) · [DaisyWriter](https://github.com/ricky-theseus/DaisyWriter) · [chinese-longnovel-skill](https://github.com/xiaofeng-928/chinese-longnovel-skill) · [dreampowers](https://github.com/skyfiredao/dreampowers) · [oh-story-claudecode](https://github.com/qin1473692580-ux/oh-story-claudecode) · [ai-fiction-writer](https://github.com/Wooooooooood/ai-fiction-writer) · [ultimate-novel-creation-skill](https://github.com/Fly143/ultimate-novel-creation-skill) · [novelops-skill](https://github.com/qiyan233/novelops-skill) · [novel-master](https://github.com/bbroot/novel-master) · [vibe-noveling](https://github.com/TulanCN/vibe-noveling) · [book-writer-skill](https://github.com/kshanxs/book-writer-skill) · [xt-webnovel-writing](https://github.com/xiaotiewinner/xt-webnovel-writing) · [webfiction-write](https://github.com/qingyabailu-git/webfiction-write) · [novel-flow-one-by-one](https://github.com/ZhangDongyang800/novel-flow-one-by-one) · [long-novelist-skill](https://github.com/tianshiemo7/long-novelist-skill) · [opencreator-novel](https://github.com/xwcai999/opencreator-novel) · [plotrail](https://github.com/waylean/plotrail) · [novel-assistant-skill](https://github.com/duiniwukenaihe/novel-assistant-skill) · [human-novel-writer](https://github.com/huahuakandaima/human-novel-writer) · [novel-writing-skill](https://github.com/cnskycn/novel-writing-skill) · [novel-writer-skill](https://github.com/liuxiao20051106-prog/novel-writer-skill) · [general-novel-skill](https://github.com/xiaoyuCR7/general-novel-skill) · [novel-webfiction](https://github.com/zlbigger/novel-webfiction) · [open-novel-fanqie](https://github.com/kongxcer555/open-novel-fanqie) · [web-novel-master](https://github.com/tinylion1024/web-novel-master) · [chinese-novelist-skill](https://github.com/lvyu-cmd/chinese-novelist-skill) · [web-novel-writing-skill](https://github.com/XINGANLIU/web-novel-writing-skill) · [novelist-skill](https://github.com/chanceline-max/novelist-skill) · [novel-craft](https://github.com/dongyanyuxuana/novel-craft) · [novel-engine](https://github.com/jiangying3222880/novel-engine) · [novel-craft](https://github.com/chaserr/novel-craft)

**审稿 · 润色 · 去 AI 味**（113）

- 专项（53）：[humanizer](https://github.com/blader/humanizer) · [Humanizer-zh](https://github.com/op7418/Humanizer-zh) · [stop-slop](https://github.com/hardikpandya/stop-slop) · [human-writing](https://github.com/KKKKhazix/human-writing) · [lieflat-less-ai-tone](https://github.com/larashero3-dotcom/lieflat-less-ai-tone) · [sepia](https://github.com/Nanako0129/sepia) · [shuorenhua](https://github.com/MrGeDiao/shuorenhua) · [manju-laoli-skill](https://github.com/lixiaoxiao9888-create/manju-laoli-skill) · [speak-human-tw](https://github.com/Raymondhou0917/speak-human-tw) · [De-AI-Prompt-Enhancer-Writer-Booster-SKILL](https://github.com/OUBIGFA/De-AI-Prompt-Enhancer-Writer-Booster-SKILL) · [seedance-2-5-video-director](https://github.com/liyue-aigc/seedance-2-5-video-director) · [qu-ai-wei](https://github.com/LifelongLazyLearner/qu-ai-wei) · [novel-writing-framework](https://github.com/LAY-lgtm/novel-writing-framework) · [humanize-text-skill](https://github.com/lynote-ai/humanize-text-skill) · [humanizer-zh-next](https://github.com/Hyacehila/humanizer-zh-next) · [short-drama-skills](https://github.com/YvonneMovingon/short-drama-skills) · [zh-humanizer-literary](https://github.com/mengke-wang/zh-humanizer-literary) · [screenwriter-skill](https://github.com/Vi7QY/screenwriter-skill) · [qu-ai-wei](https://github.com/baibanbao/qu-ai-wei) · [ai-short-drama-skill](https://github.com/xixihhhh/ai-short-drama-skill) · [de-ai-tone](https://github.com/allenloves/de-ai-tone) · [chinese-erotic-fiction-writing](https://github.com/xWebt/chinese-erotic-fiction-writing) · [novel-writing](https://github.com/wgwtest/novel-writing) · [acheng-director-skill](https://github.com/AharaOoO/acheng-director-skill) · [muse-video-skill](https://github.com/LuoJiangYong/muse-video-skill) · [lengdu](https://github.com/asass-11/lengdu) · [spark-video](https://github.com/JohnKeating1997/spark-video) · [short-drama-director](https://github.com/UncleWang2088/short-drama-director) · [novel-humanize](https://github.com/qi531416/novel-humanize) · [sun-yuchen-writing](https://github.com/AAAAAAAJ/sun-yuchen-writing) · [ManjuForge](https://github.com/mengxiujie/ManjuForge) · [zu-article-polisher-skill](https://github.com/wwenj/zu-article-polisher-skill) · [chinese-grammar-proofreader](https://github.com/orange4664/chinese-grammar-proofreader) · [natural-writing-skill](https://github.com/yyx20202020/natural-writing-skill) · [vision_art_creator](https://github.com/ilkaydemiralay/vision_art_creator) · [sloptrim-zh](https://github.com/ismilewolf-eng/sloptrim-zh) · [screenplay-review-checklist](https://github.com/zhlmi/screenplay-review-checklist) · [ai-comic-drama-director-skills](https://github.com/djyy1031/ai-comic-drama-director-skills) · [fiction-humanizer-zh](https://github.com/deedeekong07-alt/fiction-humanizer-zh) · [de-ai-router](https://github.com/YuliangXiu/de-ai-router) · [fictional-erotica](https://github.com/rs-skills-lab/fictional-erotica) · [claude-screenwriting](https://github.com/e06084/claude-screenwriting) · [mohen](https://github.com/cxzxx783/mohen) · [huoren-write](https://github.com/laoguo2025/huoren-write) · [writing-skills.TW](https://github.com/aeopress/writing-skills.TW) · [inkcraft-writing-skills](https://github.com/Fei2411/inkcraft-writing-skills) · [kunka-screenwriting-master](https://github.com/geslie1/kunka-screenwriting-master) · [human-tone-writing](https://github.com/betterwu7889/human-tone-writing) · [writing-skills](https://github.com/Calliope-Editor/writing-skills) · [xiaoci-skill](https://github.com/evoworkAI/xiaoci-skill) · [chinese-de-ai-writing](https://github.com/tangwenwen-md/chinese-de-ai-writing) · [humanize-chinese-writing](https://github.com/fy-agent/humanize-chinese-writing) · [novel-to-webnovel](https://github.com/aimerfeng/novel-to-webnovel)
- 综合（60）：[inkos](https://github.com/Narcooo/inkos) · [oh-story-claudecode](https://github.com/zenstory-ai/oh-story-claudecode) · [webnovel-writer](https://github.com/lingfengQAQ/webnovel-writer) · [chinese-novelist-skill](https://github.com/PenglongHuang/chinese-novelist-skill) · [drama-skills](https://github.com/zenstory-ai/drama-skills) · [screenwriting-skills](https://github.com/jtydhr88/screenwriting-skills) · [Chinese-WebNovel-Skill](https://github.com/Tomsawyerhu/Chinese-WebNovel-Skill) · [oh-story-dsh](https://github.com/zenstory-ai/oh-story-dsh) · [creative-writing-skills](https://github.com/haowjy/creative-writing-skills) · [short-drama-factory](https://github.com/lixiaoxiao9888-create/short-drama-factory) · [story-skills](https://github.com/danjdewhurst/story-skills) · [Lorn.NovelWriteSkills](https://github.com/lornshrimp/Lorn.NovelWriteSkills) · [webnovel-writer-opencode](https://github.com/lujih/webnovel-writer-opencode) · [sumeru](https://github.com/xindoo/sumeru) · [bookflow-skill](https://github.com/LanyXiaosheng/bookflow-skill) · [Distilled-Novel-Toolbox](https://github.com/dama-cyber/Distilled-Novel-Toolbox) · [agent-skills](https://github.com/jwynia/agent-skills) · [awesome-novel-studio](https://github.com/MJbae/awesome-novel-studio) · [novel-harness](https://github.com/manhai934/novel-harness) · [ani-book-skill](https://github.com/ExplosiveCoderflome/ani-book-skill) · [chinese-webnovel-skills](https://github.com/tance-mang/chinese-webnovel-skills) · [fanqie-novel-skill](https://github.com/304769384-png/fanqie-novel-skill) · [DaisyWriter](https://github.com/ricky-theseus/DaisyWriter) · [chinese-longnovel-skill](https://github.com/xiaofeng-928/chinese-longnovel-skill) · [dreampowers](https://github.com/skyfiredao/dreampowers) · [ai-short-drama](https://github.com/Hao0321/ai-short-drama) · [oh-story-claudecode](https://github.com/qin1473692580-ux/oh-story-claudecode) · [ai-fiction-writer](https://github.com/Wooooooooood/ai-fiction-writer) · [ultimate-novel-creation-skill](https://github.com/Fly143/ultimate-novel-creation-skill) · [novelops-skill](https://github.com/qiyan233/novelops-skill) · [novel-master](https://github.com/bbroot/novel-master) · [vibe-noveling](https://github.com/TulanCN/vibe-noveling) · [book-writer-skill](https://github.com/kshanxs/book-writer-skill) · [xt-webnovel-writing](https://github.com/xiaotiewinner/xt-webnovel-writing) · [webfiction-write](https://github.com/qingyabailu-git/webfiction-write) · [hardcore-director](https://github.com/jlam00-dev/hardcore-director) · [novel-flow-one-by-one](https://github.com/ZhangDongyang800/novel-flow-one-by-one) · [ai-manga-drama](https://github.com/liuxiao20051106-prog/ai-manga-drama) · [silver-novel-skills](https://github.com/jialanhu0915/silver-novel-skills) · [opencreator-novel](https://github.com/xwcai999/opencreator-novel) · [wangwen-writing-skill-kit](https://github.com/hyi1233/wangwen-writing-skill-kit) · [plotrail](https://github.com/waylean/plotrail) · [novel-assistant-skill](https://github.com/duiniwukenaihe/novel-assistant-skill) · [human-novel-writer](https://github.com/huahuakandaima/human-novel-writer) · [wangwenwrite-skill](https://github.com/Thatgfsj-easyRep/wangwenwrite-skill) · [novel-writing-skill](https://github.com/cnskycn/novel-writing-skill) · [novel-writer-skill](https://github.com/liuxiao20051106-prog/novel-writer-skill) · [general-novel-skill](https://github.com/xiaoyuCR7/general-novel-skill) · [open-novel-fanqie](https://github.com/kongxcer555/open-novel-fanqie) · [web-novel-master](https://github.com/tinylion1024/web-novel-master) · [chinese-novelist-skill](https://github.com/lvyu-cmd/chinese-novelist-skill) · [web-novel-writing-skill](https://github.com/XINGANLIU/web-novel-writing-skill) · [novelist-skill](https://github.com/chanceline-max/novelist-skill) · [novel-craft](https://github.com/dongyanyuxuana/novel-craft) · [fanqie-xiaoshuo-skill](https://github.com/soultt/fanqie-xiaoshuo-skill) · [novel-engine](https://github.com/jiangying3222880/novel-engine) · [Creative-writing-skill](https://github.com/xbraindance/Creative-writing-skill) · [AutoWriter](https://github.com/sinfiny/AutoWriter) · [novel-craft](https://github.com/chaserr/novel-craft) · [emma-screenwriting-skills](https://github.com/adoria111/emma-screenwriting-skills)

**书名 · 简介 · 封面**（17）

- 综合（17）：[oh-story-claudecode](https://github.com/zenstory-ai/oh-story-claudecode) · [oh-story-dsh](https://github.com/zenstory-ai/oh-story-dsh) · [Lorn.NovelWriteSkills](https://github.com/lornshrimp/Lorn.NovelWriteSkills) · [chinese-webnovel-skills](https://github.com/tance-mang/chinese-webnovel-skills) · [DaisyWriter](https://github.com/ricky-theseus/DaisyWriter) · [oh-story-claudecode](https://github.com/qin1473692580-ux/oh-story-claudecode) · [ultimate-novel-creation-skill](https://github.com/Fly143/ultimate-novel-creation-skill) · [book-writer-skill](https://github.com/kshanxs/book-writer-skill) · [xt-webnovel-writing](https://github.com/xiaotiewinner/xt-webnovel-writing) · [fanqie-short-story.skill](https://github.com/aby-aby111/fanqie-short-story.skill) · [opencreator-novel](https://github.com/xwcai999/opencreator-novel) · [wangwen-writing-skill-kit](https://github.com/hyi1233/wangwen-writing-skill-kit) · [human-novel-writer](https://github.com/huahuakandaima/human-novel-writer) · [wangwenwrite-skill](https://github.com/Thatgfsj-easyRep/wangwenwrite-skill) · [general-novel-skill](https://github.com/xiaoyuCR7/general-novel-skill) · [open-novel-fanqie](https://github.com/kongxcer555/open-novel-fanqie) · [web-novel-master](https://github.com/tinylion1024/web-novel-master)

**发布 · 多平台分发**（6）

- 专项（2）：[fanqie-publisher-skill](https://github.com/amm10090/fanqie-publisher-skill) · [auto-fanqie](https://github.com/Kirby980/auto-fanqie)
- 综合（4）：[Lorn.NovelWriteSkills](https://github.com/lornshrimp/Lorn.NovelWriteSkills) · [webnovel-writer-opencode](https://github.com/lujih/webnovel-writer-opencode) · [DaisyWriter](https://github.com/ricky-theseus/DaisyWriter) · [oh-story-claudecode](https://github.com/qin1473692580-ux/oh-story-claudecode)

**翻译 · 本地化**（15）

- 专项（15）：[AiNiee](https://github.com/NEKOparapa/AiNiee) · [GalTransl](https://github.com/GalTransl/GalTransl) · [ainiee-translate-skill](https://github.com/xuanji86/ainiee-translate-skill) · [chuanban-jp-novel-translator](https://github.com/Anarcadia/chuanban-jp-novel-translator) · [codex-visual-novel-translation](https://github.com/9029kazuki/codex-visual-novel-translation) · [glossary-review-skill](https://github.com/oodadoudou/glossary-review-skill) · [web-novel-library](https://github.com/Cheng-cheng9669/web-novel-library) · [renpy-translate](https://github.com/loggg4823-create/renpy-translate) · [novel-convert-agent](https://github.com/NguyenVi07/novel-convert-agent) · [galgame-skill](https://github.com/waw1w1/galgame-skill) · [translate-novel](https://github.com/yqrsmion/translate-novel) · [novel-localization](https://github.com/tinrin-kiri/novel-localization) · [zh-vi-novel-translation](https://github.com/duongmkqn005-ai/zh-vi-novel-translation) · [jp-ln-ocr-epub-skill](https://github.com/Katiros/jp-ln-ocr-epub-skill) · [novel-translate](https://github.com/MarkfuGod/novel-translate)

**改编（小说 → 剧本 / 漫画 / 游戏 / 互动）**（29）

- 专项（21）：[Seedance2-Storyboard-Generator](https://github.com/liangdabiao/Seedance2-Storyboard-Generator) · [novel-to-game](https://github.com/zenstory-ai/novel-to-game) · [XiaoLuo-AI-Drama-Skill](https://github.com/zhurui0523/XiaoLuo-AI-Drama-Skill) · [smy-seedance-storyboard](https://github.com/liangdabiao/smy-seedance-storyboard) · [short-drama-production](https://github.com/suihe1/short-drama-production) · [qisi-video-remix](https://github.com/wyuzhi/qisi-video-remix) · [infinite-creation](https://github.com/SwotAtmk/infinite-creation) · [narrative-to-screen-reader](https://github.com/zhlmi/narrative-to-screen-reader) · [short-drama-skills](https://github.com/YvonneMovingon/short-drama-skills) · [ai-short-drama-skill](https://github.com/xixihhhh/ai-short-drama-skill) · [novel-to-manju](https://github.com/senmanx/novel-to-manju) · [novel_to_comic](https://github.com/aiskyhub/novel_to_comic) · [novel-to-ai-short-drama-skill](https://github.com/muxia0396/novel-to-ai-short-drama-skill) · [soul-killer](https://github.com/Xeonice/soul-killer) · [codex-novel-to-comic-studio](https://github.com/lhfer/codex-novel-to-comic-studio) · [fanfic-roleplay-design](https://github.com/unknowlei/fanfic-roleplay-design) · [Comfy-H3-Director](https://github.com/MIKA6941/Comfy-H3-Director) · [ai-comic-drama-director-skills](https://github.com/djyy1031/ai-comic-drama-director-skills) · [interactive-novel](https://github.com/din1919/interactive-novel) · [write-screenplay-skill](https://github.com/egguy886/write-screenplay-skill) · [codex-noval-2-manga](https://github.com/FA-T-T/codex-noval-2-manga)
- 综合（8）：[inkos](https://github.com/Narcooo/inkos) · [shuohao-skills](https://github.com/eternityspring/shuohao-skills) · [drama-skills](https://github.com/zenstory-ai/drama-skills) · [screenwriting-skills](https://github.com/jtydhr88/screenwriting-skills) · [oh-story-dsh](https://github.com/zenstory-ai/oh-story-dsh) · [screen-creative-skills](https://github.com/VanGong1999/screen-creative-skills) · [short-drama-factory](https://github.com/lixiaoxiao9888-create/short-drama-factory) · [emma-screenwriting-skills](https://github.com/adoria111/emma-screenwriting-skills)

<a id="by-sites"></a>
## 按投稿平台查找

仓库说明里明确提到针对的平台（按星数排序）。

**起点**（16）：[Yuedu](https://github.com/XIU2/Yuedu) · [oh-story-claudecode](https://github.com/zenstory-ai/oh-story-claudecode) · [work_crawler](https://github.com/kanasimi/work_crawler) · [novel-downloader](https://github.com/404-novel-project/novel-downloader) · [novel-writing-framework](https://github.com/LAY-lgtm/novel-writing-framework) · [Lorn.NovelWriteSkills](https://github.com/lornshrimp/Lorn.NovelWriteSkills) · [go-novel-dl](https://github.com/guohuiyuan/go-novel-dl) · [sumeru](https://github.com/xindoo/sumeru) · [Distilled-Novel-Toolbox](https://github.com/dama-cyber/Distilled-Novel-Toolbox) · [chinese-webnovel-skills](https://github.com/tance-mang/chinese-webnovel-skills) · [DaisyWriter](https://github.com/ricky-theseus/DaisyWriter) · [webfiction-write](https://github.com/qingyabailu-git/webfiction-write) · [fiction-humanizer-zh](https://github.com/deedeekong07-alt/fiction-humanizer-zh) · [wangwenwrite-skill](https://github.com/Thatgfsj-easyRep/wangwenwrite-skill) · [general-novel-skill](https://github.com/xiaoyuCR7/general-novel-skill) · [web-novel-master](https://github.com/tinylion1024/web-novel-master)

**番茄**（32）：[Yuedu](https://github.com/XIU2/Yuedu) · [oh-story-claudecode](https://github.com/zenstory-ai/oh-story-claudecode) · [Tomato-Novel-Downloader](https://github.com/zhongbai2333/Tomato-Novel-Downloader) · [fanqienovel-downloader](https://github.com/ying-ck/fanqienovel-downloader) · [novel-downloader](https://github.com/404-novel-project/novel-downloader) · [novel-writing-framework](https://github.com/LAY-lgtm/novel-writing-framework) · [Lorn.NovelWriteSkills](https://github.com/lornshrimp/Lorn.NovelWriteSkills) · [go-novel-dl](https://github.com/guohuiyuan/go-novel-dl) · [webnovel-writer-opencode](https://github.com/lujih/webnovel-writer-opencode) · [sumeru](https://github.com/xindoo/sumeru) · [bookflow-skill](https://github.com/LanyXiaosheng/bookflow-skill) · [Distilled-Novel-Toolbox](https://github.com/dama-cyber/Distilled-Novel-Toolbox) · [FanqieNovelDownloader](https://github.com/rainyautumn1/FanqieNovelDownloader) · [chinese-webnovel-skills](https://github.com/tance-mang/chinese-webnovel-skills) · [fanqie-novel-skill](https://github.com/304769384-png/fanqie-novel-skill) · [DaisyWriter](https://github.com/ricky-theseus/DaisyWriter) · [oh-story-claudecode](https://github.com/qin1473692580-ux/oh-story-claudecode) · [webfiction-write](https://github.com/qingyabailu-git/webfiction-write) · [fanqie-publisher-skill](https://github.com/amm10090/fanqie-publisher-skill) · [fanqie-short-story.skill](https://github.com/aby-aby111/fanqie-short-story.skill) · [fanqie-radar](https://github.com/WindXRan/fanqie-radar) · [human-novel-writer](https://github.com/huahuakandaima/human-novel-writer) · [fiction-humanizer-zh](https://github.com/deedeekong07-alt/fiction-humanizer-zh) · [novelDownloader](https://github.com/nanachi1212/novelDownloader) · [wangwenwrite-skill](https://github.com/Thatgfsj-easyRep/wangwenwrite-skill) · [FXdownloader](https://github.com/halei0v0/FXdownloader) · [auto-fanqie](https://github.com/Kirby980/auto-fanqie) · [general-novel-skill](https://github.com/xiaoyuCR7/general-novel-skill) · [open-novel-fanqie](https://github.com/kongxcer555/open-novel-fanqie) · [web-novel-master](https://github.com/tinylion1024/web-novel-master) · [fanqie-xiaoshuo-skill](https://github.com/soultt/fanqie-xiaoshuo-skill) · [fanqie-novel-downloader-skill](https://github.com/yunmegnze/fanqie-novel-downloader-skill)

**晋江**（9）：[oh-story-claudecode](https://github.com/zenstory-ai/oh-story-claudecode) · [novel-downloader](https://github.com/404-novel-project/novel-downloader) · [sumeru](https://github.com/xindoo/sumeru) · [Distilled-Novel-Toolbox](https://github.com/dama-cyber/Distilled-Novel-Toolbox) · [chinese-webnovel-skills](https://github.com/tance-mang/chinese-webnovel-skills) · [DaisyWriter](https://github.com/ricky-theseus/DaisyWriter) · [jjwxc-downloader](https://github.com/tracywong117/jjwxc-downloader) · [general-novel-skill](https://github.com/xiaoyuCR7/general-novel-skill) · [web-novel-master](https://github.com/tinylion1024/web-novel-master)

**知乎盐言**（6）：[oh-story-claudecode](https://github.com/zenstory-ai/oh-story-claudecode) · [Lorn.NovelWriteSkills](https://github.com/lornshrimp/Lorn.NovelWriteSkills) · [Distilled-Novel-Toolbox](https://github.com/dama-cyber/Distilled-Novel-Toolbox) · [chinese-webnovel-skills](https://github.com/tance-mang/chinese-webnovel-skills) · [DaisyWriter](https://github.com/ricky-theseus/DaisyWriter) · [general-novel-skill](https://github.com/xiaoyuCR7/general-novel-skill)

**七猫**（7）：[novel-downloader](https://github.com/404-novel-project/novel-downloader) · [Lorn.NovelWriteSkills](https://github.com/lornshrimp/Lorn.NovelWriteSkills) · [webnovel-writer-opencode](https://github.com/lujih/webnovel-writer-opencode) · [DaisyWriter](https://github.com/ricky-theseus/DaisyWriter) · [webfiction-write](https://github.com/qingyabailu-git/webfiction-write) · [fiction-humanizer-zh](https://github.com/deedeekong07-alt/fiction-humanizer-zh) · [general-novel-skill](https://github.com/xiaoyuCR7/general-novel-skill)

**Royal Road**（3）：[lightnovel-crawler](https://github.com/lncrawl/lightnovel-crawler) · [chinese-webnovel-skills](https://github.com/tance-mang/chinese-webnovel-skills) · [novel-translate](https://github.com/MarkfuGod/novel-translate)

<a id="resources"></a>
## 相关资源

- [awesome-story-skills](https://github.com/UnderleveledBuilder/awesome-story-skills)：让大模型讲好故事的方法合集，按规划、长篇记忆、多 agent 审稿、去 AI 味等 12 种方法索引，附方法指南；不限网文，也收剧本、跑团和非虚构叙事
- [awesome-short-drama-skills](https://github.com/UnderleveledBuilder/awesome-short-drama-skills)：AI 短剧 · 漫剧 skill 精选，小说改编短剧从这里接着看
- [awesome-social-media-skills](https://github.com/UnderleveledBuilder/awesome-social-media-skills)：自媒体运营 skill 精选，在小红书、公众号、抖音推书和运营作者号看这里
- [anthropics/skills](https://github.com/anthropics/skills)：官方 Agent Skills 仓库，含规范和示例，想自己写 skill 可以从这里看起
- [vercel-labs/skills](https://github.com/vercel-labs/skills)：`npx skills` 安装工具，配套目录 [skills.sh](https://skills.sh)
- [VoltAgent/awesome-agent-skills](https://github.com/VoltAgent/awesome-agent-skills)：通用 skill 聚合列表

## 参与贡献

推荐项目可以[提交 issue](../../issues/new?template=submit-skill.yml)，也可以直接改 `data/skills.toml` 发 PR，详见 [CONTRIBUTING.md](CONTRIBUTING.md)。自己写的小说 skill 也欢迎自荐。

<a id="badge"></a>
## 收录徽章

项目已被收录的作者，可以在自己的 README 里加上这个徽章：

[![收录于 Awesome Novel Skills](https://img.shields.io/badge/%E6%94%B6%E5%BD%95%E4%BA%8E-Awesome_Novel_Skills-6f42c1)](https://github.com/UnderleveledBuilder/awesome-novel-skills)

```markdown
[![收录于 Awesome Novel Skills](https://img.shields.io/badge/%E6%94%B6%E5%BD%95%E4%BA%8E-Awesome_Novel_Skills-6f42c1)](https://github.com/UnderleveledBuilder/awesome-novel-skills)
```

## 许可

[CC0 1.0](LICENSE)

---

维护者：X [@UnderleveledDev](https://x.com/UnderleveledDev)
