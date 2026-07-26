# investment-advisory-workflow — neat-freak 知识收尾报告

**收尾时间**：2026-07-25
**收闭路径**：轻量路径（Skill 包 + Anthropic Skills 格式 v1.3.0，已有 recent neat-freak 风格 commit `66dea7b` README 重写 + 免责声明，HEAD 干净）
**收尾者**：neat-freak（v3.0.0）

---

## 一、影响（用户视角）

- **本次整体良好**：命名一致、SKILL.md 与 clawhub.yaml 版本**一致**（都是 1.3.0）—— 与 idx 24 context-manager（v1.1.0 vs v2.0.0 错位）和 idx 25 investment-workflow（v1.1.0 vs v1.2.0 错位）形成对比，**本项目是版本对齐的正面案例**。
- **唯一遗留**：evolve-test/ 目录未 gitignore，与 idx 24 context-manager 同款。
- **5 个核心场景 + 四专家思维** vs idx 25 investment-workflow 的 6 场景 + 6 阶段 —— 结构类似但定位不同（投研 vs 投顾）。

## 二、现役事实矩阵

| 事实面 | 状态 | 证据 |
|--------|------|------|
| 代码 | `not-applicable` | 无运行时代码；纯 Markdown + YAML Skill 定义 |
| 运行态 | `verified-current` | HEAD `66dea7b` README 重写 + 免责声明；v1.3.0 提示词优化基于 DAIR-AI 方法论（commit `eef6c9d`） |
| 文档 | `verified-current` | SKILL.md 8.9KB（Anthropic Skills 格式）+ README.md 5KB + references/ 3 文件（four-experts + shared-skills + six-stages）+ templates/ 1 文件（report-template） |
| 规则 | `not-applicable` | 无 CLAUDE.md / AGENTS.md |
| 记忆 | `not-applicable` | 无 |
| 工作区 | `verified-current` | 新建 `.neat-freak/`；HEAD 干净，无未提交改动 |

## 三、关键发现

### 3.1 命名 + 版本一致 ✅

| 文件 | version |
|------|---------|
| SKILL.md frontmatter | 1.3.0 |
| clawhub.yaml | 1.3.0 |

→ 两版本对齐（**正面案例**）。建议本项目管理方式作为其他项目的 reference。

### 3.2 命名一致 ✅

| 维度 | 名字 |
|------|------|
| 本地目录 | `investment-advisory-workflow` |
| GitHub remote | `lj22503/investment-advisory-workflow` |
| SKILL.md name | `investment-advisory-workflow` |
| clawhub.yaml name | `investment-advisory-workflow` |

→ 四层一致。

### 3.3 5 个核心场景（投顾）

| 场景 | 触发词 | 输出 |
|------|--------|------|
| 市场解读 | "最近XX怎么看？" | Markdown + 可视化卡片 |
| 事件分析 | "央行降准有什么用？" | 影响分析 + 操作建议框架 |
| 持仓诊断 | "帮我看看持仓" | 诊断报告 + 调仓建议 |
| 资产配置 | "100万怎么配置？" | 配置方案 + IPS |
| 行为纠偏 | "大跌了怎么办？" | 纠偏方案 + 话术 |

### 3.4 四专家思维

| 专家 | 专长 | 引用 |
|------|------|------|
| 林奇 (Peter Lynch) | 洞察 / 散户视角 | 一线调研、生活选股 |
| 卡尼曼 (Daniel Kahneman) | 行为 / 心理偏差 | 行为金融、认知偏差 |
| 芒格 (Charlie Munger) | 逆向 / 检查清单 | 思维模型、逆向思考 |
| 马利克 (Fritjof Malik) | 系统 / 复杂系统 | 系统论、6 账户 |

→ 与 idx 19 finops-Toolkit 的 7 角色分工模式对比——本项目用"四专家"而非"多角色"，是另一种分工模式。

### 3.5 SKILL.md §不适用的边界

> NOT for: 个股深度研究、量化策略开发、自营投资决策。

→ 项目**明确边界**：不做个股深度研究（指给 idx 25 investment-workflow）、不做量化（指给专业量化项目）、不做自营（保持顾问客观）。

### 3.6 references/ 3 文件

| 文件 | 作用（推测） |
|------|------------|
| four-experts.md | 四专家思维详细 |
| shared-skills.md | 共享 Skill 模块（推测 15 个） |
| six-stages.md | 6 阶段流程 |

### 3.7 SKILL.md 第 10 行 related_skills

`related_skills: [investment-workflow, fund-analyzer-pro, holding-diagnoser, fund-allocator, decision-checklist, companion-script, expression-layer]`

→ 与 idx 25 investment-workflow 形成 Skill 互引（互相 call）。

### 3.8 5 commit 历史

```
66dea7b docs: 重写 README，场景前置，新增 FAQ + 触发词映射 + 免责声明
eef6c9d feat: 提示词优化 v1.3.0 - 基于DAIR-AI方法论
0c71047 feat: 更新 clawhub.yaml 描述 - 投资顾问工作流 v1.3.0
ee455e2 chore: 更新 clawhub.yaml repository 指向独立仓库
5908621 chore: 合并远程仓库内容
```

→ 5 个 commit，从 one-person-ceo-skills 拆分 → v1.3.0 提示词优化（DAIR-AI） → README 重写。

### 3.9 与 idx 25 投资工作流对比

| 维度 | investment-workflow（idx 25） | investment-advisory-workflow（idx 26） |
|------|-----------------------------|-------------------------------------|
| 定位 | 投研（buy-side） | 投顾（advisory） |
| 场景数 | 6 个 | 5 个 |
| 思维模型 | 4 种共享 Skill | 4 专家（林奇/卡尼曼/芒格/马利克） |
| 阶段流程 | 6 阶段执行 | 6 阶段（推测同） |
| 版本 | 1.1.0/1.2.0 错位 ❌ | 1.3.0 一致 ✅ |
| 边界 | 默认 | 明确 NOT for |

→ 两项目**互补**：投研 + 投顾。

## 四、改动 / 新建

| 文件 | 动作 | 原因 |
|------|------|------|
| `.neat-freak/reports/investment-advisory-workflow-2026-07-24.md` | 新建 | 本次 audit trail |

## 五、待你确认（未确认前不动作）

1. **evolve-test/**：建议 .gitignore 规则（与 idx 24/25 同款）
2. **CLAUDE.md 是否创建**：项目无 agent 规则文件
3. **是否把"两版本对齐"做法推广**：本项目 SKILL.md 与 clawhub.yaml 版本一致的方法论（先 yaml 后 SKILL.md？）值得形成 recipe

## 六、遗留

- references/four-experts.md + shared-skills.md + six-stages.md 全文未读
- templates/report-template.md 模板未读
- evolve-test/ 实际内容未看
- SKILL.md 完整 6 阶段流程未读全文
- README.md 免责声明全文未读

---

*收尾完成度：5 事实面已标注（记忆 not-applicable，规则 not-applicable 缺文件）。报告基于 commit `66dea7b`（HEAD，分支 main）。本项目版本对齐（SKILL.md + clawhub.yaml 同 v1.3.0）是 idx 24/25 错位案例的反面参考。如需重新跑请清空 `.neat-freak/reports/` 后重跑。*