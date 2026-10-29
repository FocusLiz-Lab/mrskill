---
name: mrs-learning-map
description: |
  Build Mel Robbins learning paths with default IMA knowledge-base grounding. Use when the user invokes $mrs-learning-map or asks where to start, how to study The Mel Robbins Podcast, how to learn the 5 Second Rule, Let Them Theory, High 5 Habit, confidence, motivation, anxiety, relationships, habits, or how to turn the knowledge base into a structured learning sequence. By default, use the IMA knowledge base named "MelRobbins 知识库 | 自我改变".
---

## 手动更新路由

用户明确要求“更新 skill / 检查更新 / 同步最新原子库”时，先执行此路由。使用当前 SKILL.md 所在目录解析脚本绝对路径：

```text
python "{skillDir}/tools/update_skill.py"
```

只检查时加 `--check`。脚本从 GitHub main 的固定提交同步本仓库整套 skill 和原子资料，覆盖前备份，写入失败回滚；不需要 Git 或 GitHub 登录。根据脚本实际结果报告当前提交、更新状态与失败原因。普通业务问题不自动更新。更新后重新读取相关 SKILL.md。


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
