# IMA Query Map

Default knowledge base:

```text
MelRobbins 知识库 | 自我改变
```

## Query Patterns

| User asks for | Suggested IMA queries |
|---|---|
| Starting point | Mel Robbins start here, podcast first episode, 5 Second Rule, confidence, procrastination |
| 5 Second Rule | 5 Second Rule, countdown, activation energy, hesitation, courage |
| Let Them Theory | Let Them, control, boundaries, relationships, letting go |
| High 5 Habit | High 5 Habit, mirror, self encouragement, confidence, self-worth |
| Procrastination | procrastination, avoidance, motivation mistake, resistance, action |
| Anxiety or overwhelm | anxiety, stress, nervous system, fear, calm, pause |
| Relationship issues | boundaries, people pleasing, family, partner, friendship, let them |
| Content extraction | key takeaways, episode summary, quote, guest, framework, steps |

## Retrieval Rules

- Search broad first, then narrow by named concept, episode, or guest.
- Prefer Chinese and English terms when the first pass is thin.
- Report what was found and what was not found.
- Do not convert local filenames or internal IMA identifiers into public citations.
- Do not claim direct quotes unless the retrieved text supports them.

## Output Evidence Labels

Use these labels in answers:

- `IMA 证据`: retrieved material from the default or user-specified IMA knowledge base.
- `框架推断`: reasoning based on the retrieved material and the skill workflow.
- `待核对`: source-dependent point that still needs retrieval or confirmation.
