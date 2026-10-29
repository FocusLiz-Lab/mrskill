---
name: mrs-content
description: |
  Create content assets from Mel Robbins podcast themes with default IMA knowledge-base grounding. Use when the user invokes $mrs-content or asks for short video ideas, hooks, scripts, newsletters, carousels, summaries, episode takeaways, quote-safe paraphrases, topic clusters, or content calendars based on Mel Robbins podcast interviews and self-change themes. By default, use the IMA knowledge base named "MelRobbins 知识库 | 自我改变".
---

## 手动更新路由

用户明确要求“更新 skill / 检查更新 / 同步最新原子库”时，先执行此路由。使用当前 SKILL.md 所在目录解析脚本绝对路径：

```text
python "{skillDir}/tools/update_skill.py"
```

只检查时加 `--check`。脚本从 GitHub main 的固定提交同步本仓库整套 skill 和原子资料，覆盖前备份，写入失败回滚；不需要 Git 或 GitHub 登录。根据脚本实际结果报告当前提交、更新状态与失败原因。普通业务问题不自动更新。更新后重新读取相关 SKILL.md。


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
