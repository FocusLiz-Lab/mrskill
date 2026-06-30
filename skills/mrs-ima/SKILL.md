---
name: mrs-ima
description: |
  Compatibility entry for IMA retrieval with Mel Robbins podcast workflows. Use when the user explicitly invokes $mrs-ima or asks to search, read, cite, verify, or summarize Mel Robbins podcast interviews, books, tweets, or notes from IMA. This skill uses the default IMA knowledge base named "Mel Robbins 知识库 | 播客访谈".
---

# mrs-ima

Use this skill as a thin compatibility entry for users who explicitly ask for IMA retrieval.

Default IMA knowledge base:

```text
Mel Robbins 知识库 | 播客访谈
```

For the actual workflow, follow `$mrs`:

```text
IMA search/read -> evidence summary -> workflow selection -> final answer
```

Required dependency:

- `ima-skill/SKILL.md`
- `ima-skill/knowledge-base/SKILL.md`

Read `references/query-map.md` when selecting search terms.

Rules:

- Use the default knowledge base unless the user explicitly names another IMA knowledge base.
- Do not expose internal `knowledge_base_id`, `media_id`, or `folder_id`.
- Do not claim to have read IMA content unless retrieval actually happened.
- Use IMA as the retrieval source. Do not add non-IMA fallback instructions to this skill.
- If IMA credentials are missing, explain setup and do not silently use unverified materials.

Output a compact template:

```markdown
## IMA 检索摘要
- 知识库：
- 检索词：
- 命中的材料：
- 可用证据：
- 不确定/缺失：

## 处理结果

## 下一步
```
