# investment-advisory-workflow: 投资顾问工作流

> 场景驱动的投顾全流程。融合林奇/卡尼曼/芒格/马利克 四位专家思想，覆盖 5 个核心场景。

---

## 解决什么问题？

| 现状 | 用投顾工作流 |
|------|------------|
| 客户问"最近怎么看"，不知道怎么分析 | 市场扫描 + 行业降秩 + 大白话 |
| 客户持仓亏了不知道怎么安抚 | 持仓诊断 + 行为纠偏 + 安抚话术 |
| 不知道客户风险偏好就推产品 | decision-checklist + IPS 模板 |
| 大跌客户恐慌，想给建议又怕合规风险 | 行为纠偏框架 + 合规话术，不给具体买卖建议 |
| 想给客户做配置但不会沟通 | 芒格逆向检查 + 马利克六账户系统 |

---

## 5 个核心场景

| 场景 | 触发词 | 输出 |
|------|--------|------|
| 市场解读 | "最近XX怎么看？" | Markdown + 可视化卡片 |
| 事件分析 | "央行降准有什么用？" | 影响分析 + 操作建议框架 |
| 持仓诊断 | "帮我看看持仓" | 诊断报告 + 调仓建议 |
| 资产配置 | "100万怎么配置？" | 配置方案 + IPS |
| 行为纠偏 | "大跌了怎么办？" | 纠偏方案 + 话术 |

---

## 快速开始

```
/投资顾问 最近消费怎么看？
/投资顾问 帮我看看持仓
/投资顾问 100万怎么配置？
/投资顾问 大跌了怎么办？
```

---

## 场景 vs 投顾流程对照

**场景 1：客户问市场**
```
用户：最近消费怎么看？
→ market-scan → industry-rank → plain-explain → ljg-card
→ 输出：Markdown + PNG卡片
```

**场景 2：客户问事件**
```
用户：央行降准有什么用？
→ market-scan → industry-rank → multi-view → plain-explain → decision-integrate
→ 输出：影响分析 + 操作建议框架
```

**场景 3：持仓诊断**
```
用户：帮我看看持仓
→ data-query → holding-diagnoser → decision-checklist → fund-allocator → report-generator
→ 输出：诊断报告 + 调仓建议
```

**场景 4：资产配置**
```
用户：100万怎么配置？
→ decision-checklist → fund-allocator → ljg-roundtable → IPS → report-generator
→ 输出：配置方案 + 投资政策说明书
```

**场景 5：行为纠偏（大跌恐慌）**
```
用户：大跌了怎么办？
→ market-scan → companion-script → ljg-relationship → problem-mapper → plain-explain
→ 输出：纠偏方案 + 安抚话术（不给具体买卖建议）
```

---

## 四专家思维

| 专家 | 视角 | 投顾应用 |
|------|------|---------|
| 林奇 | 洞察发掘 | 生活化触达，故事驱动 |
| 卡尼曼 | 行为纠偏 | 认知偏误识别，选择架构 |
| 芒格 | 逆向检查 | 安全边际，失败预演 |
| 马利克 | 系统管理 | 六大账户，定期检视 |

---

## 触发词映射（Agent 调用索引）

| 用户说 | 调用 |
|--------|------|
| "最近怎么看"、"帮我分析市场" | `market-scan` + `industry-rank` |
| "央行降准"、"这个事件" | `market-scan` + `multi-view` |
| "帮我看看持仓"、"诊断持仓" | `data-query` + `holding-diagnoser` |
| "100万怎么配"、"资产配置" | `fund-allocator` + decision-checklist |
| "大跌了怎么办"、"客户恐慌" | `companion-script` + `ljg-relationship` |
| "要不要加仓"、"要不要卖" | `decision-checklist` + 风险揭示（不给具体建议） |
| "合规吗" | `content-compliance` |
| "生成报告" | `report-generator` |

---

## 共享 Skill（15个）

| Skill | 核心用途 |
|-------|---------|
| `market-scan` | 市场快照 |
| `industry-rank` | 行业降秩 |
| `holding-diagnoser` | 持仓5层诊断 |
| `fund-analyzer-pro` | 基金深度分析 |
| `fund-allocator` | 资产配置 |
| `decision-checklist` | 决策检查清单 |
| `companion-script` | 安抚话术 |
| `ljg-relationship` | 行为关系 |
| `problem-mapper` | 问题树 |
| `report-generator` | 报告生成 |
| `content-compliance` | 合规审查 |

---

## 数据层

- **data_layer v2.2.0**：akshare + fund_eastmoney
- **mcp-aktools**：零 API Key，AKShare 数据源
- **qieman-mcp**：且慢 MCP，持仓穿透/业绩归因

---

## FAQ

**Q：能直接推荐客户买什么吗？**

A：不能给具体标的投资建议。工作流输出分析框架、配置比例、风险揭示，最终决策由持牌投顾和客户共同完成。

**Q：和投教工作流（investor-education-workflow）有什么区别？**

A：投顾工作流专注"1对1客户场景"（持仓诊断、资产配置、行为纠偏），投教工作流专注"批量内容生产"（写文章、做卡片、发朋友圈）。

**Q：需要什么数据源？**

A：持仓数据需要客户提供，market-scan 依赖 akshare 免费数据源。

---

## ⚠️ 免责声明

本工作流仅供辅助参考，不构成投资建议。所有建议需经持牌投顾审核确认。

---

*版本：v1.0.0 | 2026-04-24*
