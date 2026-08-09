# Siro's Skills

个人 OpenCode 技能集合仓库。每个技能是一个独立目录，包含 `SKILL.md` 与可选的 `evals/` 测试用例。

## 技能列表

| 技能 | 说明 | 触发场景 |
| --- | --- | --- |
| [wudu-novel-writing](./wudu-novel-writing/) | 二次元轻小说正文写作（雾都文风蒸馏版） | 写小说正文、续写章节、模仿文风、检查正文是否符合文风、把大纲扩写为正文 |

### wudu-novel-writing

从 21 万字符中文小说样本（转生史莱姆同人·二次元轻小说文风）中蒸馏出的完整写作技能。

- **文气指纹**：短段分镜 × 吐槽旁白 × 二次元设定不解释 × 反差萌 × 甜宠微动作 × 月光意象
- **内置**：文风快照卡片、符号/语气词系统、五种场景标准动作（战斗三拍法/对话三件套/日常锚点/心理三句式/景物两笔勾景）、叙事纪律（视角/节奏/信息投放/情绪渲染）、错别字勘误清单、快速/标准/精修三档输出模式
- **测试**：`evals/evals.json` 含 3 个用例（续写/战斗/改写），实测带技能 100% 通过率 vs 基线 61%

## 安装

### 全局安装（所有项目可用，推荐）

将技能目录复制到 OpenCode 全局技能目录：

```powershell
Copy-Item -Recurse .\wudu-novel-writing "$env:USERPROFILE\.config\opencode\skills\"
```

### 项目级安装（仅当前项目可用）

```powershell
Copy-Item -Recurse .\wudu-novel-writing ".\opencode\skills\"
```

目录名必须与 `SKILL.md` frontmatter 中的 `name` 一致。

## 目录结构

```
skills/
├── .gitignore              # 排除样本素材/测试工作区/临时文件
├── README.md
└── <skill-name>/
    ├── SKILL.md            # 技能主体（frontmatter + 指令）
    └── evals/
        └── evals.json      # 测试用例（可选）
```

## 开发约定

- `SKILL.md` 的 `description` 承担技能触发职责：写明"何时触发/做什么"，并包含触发词
- 版权/私有样本（`.docx`、`.txt` 等）不入库，由 `.gitignore` 排除
- 测试工作区（`*-workspace/`、`iteration-*/`）不入库
