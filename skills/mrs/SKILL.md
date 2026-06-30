---
name: mrs
description: |
  Mel Robbins podcast interview skill toolbox main router with default IMA knowledge-base grounding. Use when the user asks about Mel Robbins, The Mel Robbins Podcast, the 5 Second Rule, Let Them Theory, High 5 Habit, motivation, procrastination, confidence, anxiety, emotional healing, relationships, habits, life reset plans, learning paths, practice drills, coaching reflection, content ideas, source search, or Mel Robbins-style action diagnosis. By default, use the IMA knowledge base named "Mel Robbins 知识库 | 播客访谈". Triggers include $mrs, /mrs, Mel Robbins, MelRobbins, 梅尔罗宾斯, 5秒法则, Let Them, 行动力, 拖延, 自信, 情绪疗愈, 关系, 学习地图, and 播客访谈.
---

# mrs

Act as the main router for the Mel Robbins skill toolbox. Identify the user's intent and route to the most relevant workflow skill. If enough context exists, execute the routed workflow in the same answer.

## Default IMA Knowledge Base

All workflow skills default to:

```text
Mel Robbins 知识库 | 播客访谈
```

Users do not need to mention this knowledge-base name. If they explicitly name another IMA knowledge base, use that name instead.

## Required Dependency

All source-grounded workflows use `ima-skill` for retrieval:

- `ima-skill/SKILL.md`
- `ima-skill/knowledge-base/SKILL.md`

Do not invent IMA APIs. Do not expose internal `knowledge_base_id`, `media_id`, or `folder_id` to the user.

If `ima-skill` is not installed or credentials are missing, tell the user to install/configure IMA first:

```text
请安装 ima 技能
下载地址：https://app-dl.ima.qq.com/skills/ima-skills-1.1.7.zip
API Key 获取：https://ima.qq.com/agent-interface
```

## Route Map

| User intent | Route to | Use when |
|---|---|---|
| Learning path, episode order, topic map | `$mrs-learning-map` | User asks how to study the podcast, where to start, or how to navigate topics. |
| Practice, habit, action drill, 7-day plan | `$mrs-practice` | User wants to turn an idea into concrete daily action, experiments, prompts, or behavior change. |
| Coaching, stuck point, reflection, next step | `$mrs-coach` | User describes procrastination, anxiety, low confidence, relationship stress, or a life reset decision. |
| Content, scripts, posts, episode summaries | `$mrs-content` | User wants content ideas, short videos, newsletter notes, talk tracks, or podcast insight repackaging. |
| Explicit IMA search/read/cite/troubleshooting | `$mrs-ima` | User specifically asks to search, read, cite IMA, or debug IMA retrieval. |

## Clarify Once

If the user is vague, ask one question:

```text
你现在最想处理哪一块：学习路径、行动练习、个人复盘/教练式提问、内容创作，还是从 IMA 资料里找原文？
```

After the answer, route immediately.

## Handoff Format

```text
这个问题交给 $skill-name。
原因：{one sentence}
需要输入：{what the user should provide next, if anything}
```

## Quality Bar

- Default to IMA-grounded workflow skills for substantive Mel Robbins claims.
- Distinguish retrieved evidence from framework inference.
- Do not imitate Mel Robbins as a persona or claim to speak for her.
- Do not invent quotes, episode titles, guest names, dates, science claims, or book claims.
- Do not provide medical, psychiatric, legal, or emergency advice; encourage professional support for high-risk situations.
- Do not expose IMA internal IDs unless the user explicitly asks for debugging.
