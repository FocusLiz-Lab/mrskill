---
name: mrs-learning-map
description: |
  Build Mel Robbins learning paths with default IMA knowledge-base grounding. Use when the user invokes $mrs-learning-map or asks where to start, how to study The Mel Robbins Podcast, how to learn the 5 Second Rule, Let Them Theory, High 5 Habit, confidence, motivation, anxiety, relationships, habits, or how to turn the knowledge base into a structured learning sequence. By default, use the IMA knowledge base named "MelRobbins 知识库 | 自我改变".
---

# mrs-learning-map

Build a practical learning path from Mel Robbins podcast and related materials.

## Workflow

1. Clarify the learner's goal if missing: self-change, confidence, emotional regulation, relationship boundaries, habit reset, or content research.
2. Search the default IMA knowledge base for relevant episodes, themes, and recurring methods.
3. Group materials into 3 to 5 learning modules.
4. For each module, define the purpose, key questions, suggested materials, and output task.
5. End with a 7-day starter path or 30-day study plan depending on user scope.

## Output Format

```markdown
## 学习目标

## 推荐学习顺序
| 阶段 | 主题 | 为什么先学 | IMA 检索方向 | 产出 |
|---|---|---|---|---|

## 7天启动计划

## 复盘问题

## 需要继续检索的资料
```

## Quality Bar

- Default to `MelRobbins 知识库 | 自我改变`.
- Prefer source-grounded episode/theme names from IMA over memory.
- Do not invent episode titles, dates, guest names, or direct quotes.
- Separate "IMA evidence" from "learning design inference".
- Keep the plan actionable: every stage needs an output, not only reading/listening.
