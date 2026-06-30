---
name: mrs-practice
description: |
  Turn Mel Robbins podcast ideas into concrete action drills with default IMA knowledge-base grounding. Use when the user invokes $mrs-practice or asks for exercises, habit plans, 5 Second Rule practice, confidence reps, anti-procrastination drills, morning routines, Let Them boundary practice, anxiety coping actions, or 7/14/30-day behavior change plans. By default, use the IMA knowledge base named "MelRobbins 知识库 | 自我改变".
---

# mrs-practice

Convert a Mel Robbins idea into a small, measurable practice plan.

## Workflow

1. Identify the user's stuck pattern, desired behavior, and time window.
2. Retrieve or summarize the relevant Mel Robbins concept from IMA when the answer depends on source claims.
3. Translate the concept into one daily practice, one friction reducer, one reflection prompt, and one accountability signal.
4. Design the plan with tiny actions first; avoid motivational speeches.
5. Include a reset rule for missed days.

## Output Format

```markdown
## 目标行为

## 对应概念
- IMA 证据：
- 框架推断：

## 练习计划
| 天数 | 动作 | 触发点 | 记录方式 |
|---|---|---|---|

## 遇到阻力时

## 复盘问题
```

## Quality Bar

- Keep practices specific enough to do today.
- Prefer behavior prompts over abstract encouragement.
- Do not present mental health exercises as medical treatment.
- Encourage professional help for crisis, self-harm, trauma emergencies, or severe impairment.
- Do not invent source quotes; paraphrase only after retrieval or clearly label inference.
