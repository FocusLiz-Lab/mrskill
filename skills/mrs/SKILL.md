---
name: mrs
description: |
  Mel Robbins 自我改变 Skill 工具箱主入口。用于 5 秒法则、Let Them 理论、High 5 Habit、行动力、拖延、自信、焦虑、情绪疗愈、关系、习惯、人生重启计划、学习路径、行动练习、教练式复盘、内容选题、资料检索和 Mel Robbins 风格行动诊断。默认使用 IMA 知识库「MelRobbins 知识库 | 自我改变」，并可在 IMA 不可用时读取本地原子库。触发词包括 $mrs、/mrs、Mel Robbins、梅尔罗宾斯、5秒法则、Let Them、行动力、拖延、自信、情绪疗愈、关系、学习地图和播客访谈。
---

# mrs Mel Robbins 自我改变工具箱

这是 Mel Robbins 自我改变工具箱的主入口。先判断用户意图，再路由到最相关的 workflow skill；如果上下文足够，直接在同一回答中完成对应工作流。

## 默认 IMA 知识库

所有 workflow skills 默认读取：

```text
MelRobbins 知识库 | 自我改变
```

用户不需要每次输入这个知识库名称。如果用户明确指定其他 IMA 知识库，则优先使用用户指定的知识库。

## 必要依赖

所有需要资料依据的 workflow 都使用 `ima-skill` 做检索：

- `ima-skill/SKILL.md`
- `ima-skill/knowledge-base/SKILL.md`

不要臆造 IMA API。不要向用户暴露内部 `knowledge_base_id`、`media_id` 或 `folder_id`。

如果没有安装 `ima-skill` 或凭证缺失，先提示用户安装并配置 IMA：

```text
请安装 ima 技能
下载地址：https://app-dl.ima.qq.com/skills/ima-skills-1.1.7.zip
API Key 获取：https://ima.qq.com/agent-interface
```

## 路由表

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
