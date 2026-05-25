# 简历辅助 Skill 构建文档

## 概述

本文档是 `my-first-resume` Skill 的完整构建文档，包含文件结构、工作流设计、使用说明等内容。

---

## 一、文件结构

```
my-first-resume/
├── SKILL.md                    # 入口：元数据 + 工作流指令
├── methods/
│   ├── good-resume-elements.md # 好简历要素教学
│   ├── star-guide.md           # STAR 原则详解 + 示例
│   ├── quantification.md       # 如何量化成果
│   └── section-guide.md        # 各模块写作指南
├── templates/
│   └── student.md              # 应届生/实习生简历模板
├── review/
│   ├── multi-role-critique.md  # 多角色批判指令
│   ├── checklist.md            # 质量检查清单
│   └── scoring.md              # 打分标准
├── simulation/
│   ├── company-types.md        # 企业类型特征定义
│   └── jd-match.md             # JD 匹配分析指令
└── examples/
    ├── good-resume.md          # 优秀简历示例
    └── bad-vs-good.md          # 对比示例
```

---

## 二、核心工作流

```
Step 0: 破冰教育 → 介绍好简历要素，了解用户背景和求职方向
Step 1: 构建大纲 → 根据基本信息生成简历框架
Step 2: 渐进收集 → 对话式引导用户补充各模块内容（每次1个模块）
Step 3: STAR 润色 → 按方法论优化表达，强调量化成果
Step 4: 多角色批判 → Subagent 扮演 5 个角色独立评估
Step 5: 问题修复 → 根据批判意见修改，整合检查清单打分
Step 6: 模拟投递 → AI 角色模拟 + 可选 JD 匹配，评估不同企业类型反馈
Step 7: 迭代优化 → 用户确认后循环修改
Step 8: 最终导出 → 输出 HTML/PDF
```

---

## 三、多角色批判团队

| 角色 | 评估维度 | 权重 |
|-----|---------|------|
| 目标岗位资深员工 | 专业能力匹配度、技术深度 | 30% |
| 项目经理 | 项目经历合理性、成果可信度 | 25% |
| HR 经理 | 人岗匹配、第一印象、表达质量 | 25% |
| ATS 系统 | 机器可读性、关键词覆盖率、格式规范 | 15% |
| 学长/学姐（可选） | 学生气程度、同龄人视角、真实感 | 5% |

---

## 四、模拟投递企业类型

### 技术类岗位
- 互联网大厂（技术深度/项目亮点/成长潜力）
- 创业公司（自驱力/多面手/快速学习）
- 外企技术岗（英语/国际化/专业度）
- 外包公司（执行力/交付能力）

### 金融类岗位
- 银行（学历/证书/稳重）
- 证券/基金（专业资质/数据分析）
- 金融科技公司（技术+金融复合）

### 通用类岗位
- 外企（英语/国际化/专业度）
- 互联网大厂（综合能力/成长潜力）
- 中型企业（稳定性/性价比）
- 国企（学历/证书/稳重）

---

## 五、约束规则

1. **禁止编造**：AI 不得捏造用户未提及的经历或数据
2. **真实性提醒**：所有量化数据需提示用户核实
3. **隐私保护**：不收集身份证号、家庭住址等敏感信息
4. **渐进披露**：按需读取资源文件，节省 Token
5. **质量把关**：终稿必须通过检查清单（≥80分）

---

## 六、使用方式

### 安装

将 `my-first-resume` 文件夹复制到 Claude Code 的 skills 目录：

```bash
# macOS/Linux
cp -r my-first-resume ~/.claude/skills/

# Windows
Copy-Item -Path "my-first-resume" -Destination "$env:USERPROFILE\.claude\skills\" -Recurse
```

### 激活

当用户说以下内容时，Claude 会自动激活此 Skill：
- "帮我写简历"
- "我第一次写简历"
- "我是应届生，需要写简历"
- "帮我优化简历"

### 验证

```
用户：我有哪些可用的 Skills？

Claude：你应该能看到 resume-first-timer 在列表中
```

---

## 七、文件清单

| 文件 | 用途 | 行数 |
|-----|------|------|
| SKILL.md | 入口文件，定义工作流 | ~200 |
| methods/good-resume-elements.md | 好简历要素教学 | ~80 |
| methods/star-guide.md | STAR 原则详解 | ~150 |
| methods/quantification.md | 量化成果指南 | ~100 |
| methods/section-guide.md | 各模块写作指南 | ~200 |
| templates/student.md | 应届生简历模板 | ~100 |
| review/multi-role-critique.md | 多角色批判指令 | ~200 |
| review/checklist.md | 质量检查清单 | ~150 |
| review/scoring.md | 打分标准 | ~100 |
| simulation/company-types.md | 企业类型特征 | ~250 |
| simulation/jd-match.md | JD 匹配指令 | ~150 |
| examples/good-resume.md | 优秀简历示例 | ~100 |
| examples/bad-vs-good.md | 对比示例 | ~200 |

**总计**：约 2000 行

---

## 八、后续迭代建议

1. **增加行业模板**：针对不同行业（互联网、金融、制造业）增加简历模板
2. **增加岗位模板**：针对不同岗位（前端、后端、产品、运营）增加模板
3. **增加面试准备**：根据简历内容生成面试预测问题
4. **增加投递追踪**：记录投递历史和反馈
5. **多语言支持**：支持英文简历生成
