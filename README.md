# Skills 集合项目

这是一个技能（Skill）集合项目，包含多个可复用的 AI Skill 模块，用于扩展 Agent 的功能。

## 项目概述

本项目致力于构建高质量、可复用的 AI Skill 模块，每个 Skill 都经过精心设计，包含完整的工作流、评审机制和资源文件，确保输出质量。

## 项目结构

```
skills/
├── LICENSE                    # 许可证文件
├── README.md                  # 项目说明文档
├── my-first-resume/           # 简历辅助技能
│   ├── SKILL.md              # 技能入口文件
│   ├── README.md             # 技能详细文档
│   ├── methods/              # 方法论指南
│   ├── templates/            # 简历模板
│   ├── review/               # 评审规则
│   ├── simulation/           # 模拟投递
│   └── examples/             # 示例文件
└── annoying-paper/           # 课程论文生成技能
    ├── SKILL.md              # 技能入口文件
    ├── README.md             # 技能详细文档
    ├── methods/              # 方法论与知识库
    ├── templates/            # 论文模板
    ├── review/               # 评审体系
    ├── search/               # 文献查询
    └── examples/             # 示例文件
```

## 技能列表

### 1. my-first-resume

**描述**：面向应届生/实习生的简历辅助 Skill，通过渐进式引导、STAR 润色、多角色批判、模拟投递等环节，帮助首次写简历的用户生成高质量简历。

**触发词**："帮我写简历"、"我第一次写简历"、"我是应届生，需要写简历"、"帮我优化简历"、"我要找工作，需要简历"

**核心特色**：渐进式引导、STAR 原则润色、5角色批判评审、模拟投递反馈、输出 HTML/PDF

**详细文档**：[my-first-resume/README.md](my-first-resume/README.md)

---

### 2. annoying-paper

**描述**：大学生通识课/选修课快捷论文生成器，通过多角色决策团队评审、量化评分、多轮校验修改，一次性输出高质量课程论文。支持 docx/md/tex 三种格式导出。

**触发词**："帮我写论文"、"写课程论文"、"通识课作业"、"选修课论文"、"课程作业"、"期末论文"、"小论文"、"annoying-paper"

**核心特色**：一次性输出、三板块文献查询、5角色量化评审、自动修复循环、降AI痕迹策略、三格式导出

**详细文档**：[annoying-paper/README.md](annoying-paper/README.md)

---

## 技能对比

| 维度 | my-first-resume | annoying-paper |
|------|----------------|----------------|
| 目标用户 | 应届生/实习生 | 大学生 |
| 交互模式 | 渐进式引导（8步） | 一次性输出（7步） |
| 评审机制 | 5角色批判 + 模拟投递 | 5角色评审 + 量化评分 |
| 修复机制 | 手动迭代 | 自动修复循环 |
| 输出格式 | HTML/PDF | docx/md/tex |
| 核心特色 | STAR润色、模拟投递 | 三板块文献、降AI痕迹 |

## 安装方法

将技能文件夹复制到 Agent 的 skills 目录：

```bash
# macOS/Linux
cp -r my-first-resume ~/.claude/skills/
cp -r annoying-paper ~/.claude/skills/

# Windows
Copy-Item -Path "my-first-resume" -Destination "$env:USERPROFILE\.claude\skills\" -Recurse
Copy-Item -Path "annoying-paper" -Destination "$env:USERPROFILE\.claude\skills\" -Recurse
```

## 使用方式

当用户说出特定触发词时，Agent 会自动激活对应的技能。

### my-first-resume
- "帮我写简历"
- "我第一次写简历"
- "我是应届生，需要写简历"
- "帮我优化简历"
- "我要找工作，需要简历"

### annoying-paper
- "帮我写论文"
- "写课程论文"
- "通识课作业"
- "选修课论文"
- "课程作业"
- "期末论文"
- "小论文"
- "annoying-paper"

## 技能开发规范

### 文件结构

```
skill-name/
├── SKILL.md                  # 必须：技能入口文件（元数据 + 工作流指令）
├── README.md                 # 建议：技能详细说明文档
├── methods/                  # 方法论与知识库
├── templates/                # 模板文件
├── review/                   # 评审体系（评分标准、修复规则）
├── search/                   # （可选）文献查询指令
├── simulation/               # （可选）模拟/测试模块
└── examples/                 # 示例文件
```

### SKILL.md 格式

```markdown
---
name: skill-name
description: 技能描述
---

# 技能名称

## 适用场景
...

## 核心工作流
...

## 约束规则
...

## 资源文件索引
...
```

## 许可证

本项目采用 MIT 许可证，详见 [LICENSE](LICENSE) 文件。

## 贡献

欢迎提交新的技能模块或改进现有技能！请遵循项目结构规范。

## 更新日志

### v2.0 (2026-07-23)
- 新增 `annoying-paper` 课程论文生成技能
- 更新项目结构和技能列表
- 添加技能对比表格
- 完善技能开发规范
