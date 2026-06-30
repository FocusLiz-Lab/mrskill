# mrskill

Mel Robbins 风格播客访谈与自我改变 Skill 工具箱。

`mrskill` 是一组面向 Agent 的 workflow skills，用来基于 IMA 知识库学习 Mel Robbins 播客访谈资料，并完成学习路径、行动练习、教练式复盘、内容创作和资料检索。

适用于 Codex、Claude Code、Cursor、Trae Solo 等支持 skill / system prompt 工作流的 Agent。

---

## 安装

发布后，可以用下面的命令安装整套 skills：

```bash
npx -y skills add FocusLiz-Lab/mrskill -g --all
```

安装后可以直接使用：

```text
$mrs 我总是拖延，按 Mel Robbins 的行动框架帮我拆一下。
```

也可以手动复制或导入 `skills/` 目录下的 skill 文件夹：

```text
skills/
├── mrs/
├── mrs-learning-map/
├── mrs-practice/
├── mrs-coach/
├── mrs-content/
└── mrs-ima/
```

每个文件夹都是一个独立 skill，根目录都有 `SKILL.md`。

---

## IMA 配置

整套 workflow skills 默认读取这个 IMA 知识库：

```text
MelRobbins 知识库 | 自我改变
```

用户不需要在每次提问时输入知识库名称。如果想使用其他 IMA 知识库，在问题里直接写知识库名称即可。

### 加入 / 访问知识库

扫描下面的二维码，加入或访问对应知识库：

![知识库二维码](docs/knowledge-base-qrcode.png)

### 安装 IMA Skill

```text
请安装 ima 技能
下载地址：https://app-dl.ima.qq.com/skills/ima-skills-1.1.7.zip
API Key 获取：https://ima.qq.com/agent-interface
```

使用前需要满足：

- 已安装官方 `ima-skill`
- 已配置 IMA `Client ID` 和 `API Key`
- 当前 IMA 账号有权限访问目标知识库

本仓库不包含、也不会保存任何 IMA API Key。

---

## 工具箱

| Skill | 用途 |
|---|---|
| `$mrs` | 主入口。根据用户问题自动路由到合适的 Mel Robbins workflow。 |
| `$mrs-learning-map` | 学习地图：播客主题顺序、学习路径、输出任务。 |
| `$mrs-practice` | 行动练习：把观点转成 7/14/30 天小行动和复盘。 |
| `$mrs-coach` | 教练式复盘：诊断卡点、提出问题、选择下一步动作。 |
| `$mrs-content` | 内容系统：选题、hook、脚本、newsletter 和摘要改写。 |
| `$mrs-ima` | IMA 检索入口：搜索、阅读、引用或排查 IMA。 |

---

## 常见路径

### 从学习到行动

```text
mrs-learning-map
    ↓
mrs-practice
    ↓
mrs-coach
```

### 从卡点到下一步

```text
mrs-coach
    ↓
mrs-practice
```

### 从播客到内容

```text
mrs-ima
    ↓
mrs-content
```

---

## 使用示例

```text
$mrs-learning-map 系统学习这个知识库，先看哪些主题？
```

```text
$mrs-practice 把 5 秒法则设计成一个 7 天练习。
```

```text
$mrs-coach 我总是想很多但不开始，帮我做一次复盘。
```

```text
$mrs-content 围绕拖延、行动力和自信生成 20 个短视频选题。
```

---

## 知识库 / 原子库

本仓库包含一个发布安全的抽象原子库：

```text
知识库/原子库/atoms.jsonl
```

它用于保存 Mel Robbins 风格 workflow 的方法论单元，不包含书籍、视频文稿、播客转录稿、社交媒体原文或付费材料。涉及具体原文、出处、嘉宾、案例细节时，仍应优先使用 IMA 知识库检索。

---

## 资料边界

本仓库只包含 skill instructions 和 workflow 抽象。

本仓库不包含 Mel Robbins 的原书、PDF、付费材料、YouTube 转录稿、X/Twitter 归档、私有资料文件夹或任何受版权保护的原始资料库。

这些 skills 会在运行时从用户自己的 IMA 知识库检索资料。用户需要自行确保有权上传和使用自己的资料。

请不要提交：

- IMA API Key
- 私有资料文件
- 原始 PDF、转录稿、视频或归档
- 个人环境配置
- 任何未经授权的第三方内容

---

## 许可证

本项目默认采用 CC BY-NC 4.0 许可证，除非后续另行添加其他许可证。

许可证只覆盖本仓库原创的 skill instructions 和 workflow 抽象，不授权任何第三方原始资料。
