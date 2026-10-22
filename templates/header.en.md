# Awesome Novel Skills

[中文](README.md) · **English**

> A curated list of agent skills for writing novels and web fiction with AI: market research, outlining, drafting, long-form continuity, de-AI revision, short-drama scripts, translation and publishing. Install them into Claude Code or Codex and start writing.

This list collects novel and web-fiction skills for agents such as Claude Code, Codex and OpenClaw. They cover ranking-chart analysis and book teardowns, setting and characters, outlines and chapter outlines, drafting and continuation, keeping a long serial consistent and in character, review and de-AI revision, titles, blurbs and covers, translation for overseas readers, and publishing. The list also includes skills for plotting short-drama scripts, and the downloaders and book-source tools that book teardowns depend on. Every project has been checked by hand and sorted by type, writing stage and target platform.

Most projects come from the Chinese web-novel scene (Qidian, Fanqie Novel, Jinjiang and others), and many are documented in Chinese; the descriptions below are translated. For story-writing methods beyond web novels, with an English method guide, see [Awesome Story Skills](https://github.com/UnderleveledBuilder/awesome-story-skills/blob/main/README.en.md).

{{count}} skills and tools + {{apps}} related open-source apps · metadata updated {{updated}}

## Which skill to install for premises

Round 2 (2026-10-20): 10 skills from this list that can come up with a premise from scratch, 0xsline/short-drama from the short drama list, and a control with no skill installed each chose a premise 3 times for the same kind of revenge-fantasy story, one that could become a web novel or a vertical short drama. Every entry was compared blind with every other and ranked by points. The reviewers ask whether viewers would keep watching once AI makes it. Both AI reviewers (Opus and GPT) put the same three skills on top; all three beat the control in all 3 runs, and all three are in this list:

| Skill | Place (Opus / GPT) | Good for | Watch out for |
|---|---|---|---|
| [Tomsawyerhu/Chinese-WebNovel-Skill](https://github.com/Tomsawyerhu/Chinese-WebNovel-Skill) | 1 / 2 | Rare legal jobs and reversals of status; pitches you get in one line; payoffs that land on the opponent's face | One run is the familiar hidden-expert formula; limited fuel for a long serial |
| [lingfengQAQ/webnovel-writer](https://github.com/lingfengQAQ/webnovel-writer) | 2 / 3 | Powers with rules that cost something; the hero's flaw tied to the power | All 3 runs let the hero see numbers over people's heads; repetitive in the middle |
| [Hao0321/ai-short-drama](https://github.com/Hao0321/ai-short-drama) | 3 / 1 | The freshest premises; powers with rules; hooks with strong images | The rules leave the hero too passive, so payoffs come slowly |

Limits of this round:
- Both reviewers placed the no-skill control 9th, with 3 skills below it.
- oh-story and chinese-longnovel-skill start by checking the charts, but there was no network, so they had no chart data and placed near the bottom; how they do with the network, this round cannot say.
- The two reviewers disagreed on 63 of 198 pair results, mostly in the middle of the table.
- Only one model was tested, claude-opus-5-5, and only premises were compared, not the writing.

The full record and per-skill reviews (in Chinese): [Round 2](https://shortdramaskills.com/evals/round-2/).

**Legend**: 🌟 featured · 📝 prompt files (not a standard skill) · 🧩 full app · 📚 target platform · 💤 not updated for 180+ days · 📦 archived · ⚠️ repo unavailable

> [!NOTE]
> "Checked by hand" means the README, directory structure and classification were reviewed; it does not mean the output was tested. Side-by-side tests live in [evals/](evals/). A skill may ship scripts, so read its SKILL.md before installing it.
