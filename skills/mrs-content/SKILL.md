---
name: mrs-content
description: |
  Create content assets from Mel Robbins podcast themes with default IMA knowledge-base grounding. Use when the user invokes $mrs-content or asks for short video ideas, hooks, scripts, newsletters, carousels, summaries, episode takeaways, quote-safe paraphrases, topic clusters, or content calendars based on Mel Robbins podcast interviews and self-change themes. By default, use the IMA knowledge base named "Mel Robbins 知识库 | 播客访谈".
---

# mrs-content

Turn Mel Robbins podcast themes into publishable content ideas without copying original material.

## Workflow

1. Clarify platform and audience if missing.
2. Retrieve relevant IMA materials when the user asks for episode-grounded content, summaries, or claims.
3. Extract the reusable idea, emotional tension, audience situation, and action takeaway.
4. Create content assets in the requested format.
5. Mark any source-dependent claims that need IMA verification.

## Output Format

```markdown
## 内容角度

## 选题列表
| 标题/Hook | 受众痛点 | 核心观点 | 行动提示 | 需核对来源 |
|---|---|---|---|---|

## 示例脚本

## 发布注意
```

## Quality Bar

- Do not reproduce transcripts, long quotes, or book passages.
- Keep direct quotes short and only when retrieved and necessary.
- Prefer paraphrase, commentary, and original framing.
- Do not fabricate episode details, guest credentials, or research claims.
- Make the content useful outside the fandom: focus on user problems and actions.
