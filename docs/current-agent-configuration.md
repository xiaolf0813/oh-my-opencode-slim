# 当前 Agent 配置

## 配置来源

- 用户配置：`~/.config/opencode/oh-my-opencode-slim.json`
- 当前 preset：`mycompany`
- 项目覆盖：`.opencode/oh-my-opencode-slim.jsonc`

项目配置会覆盖用户 preset 中同一 agent 的字段。

## 职位名称

| 内部名称 | 显示名称 | 职责 |
| --- | --- | --- |
| `orchestrator` | `EngineeringLead` | 任务拆解、协调与验收 |
| `explorer` | `CodebaseAnalyst` | 代码库检索与分析 |
| `librarian` | `TechnicalResearcher` | 文档与外部资料研究 |
| `oracle` | `ChiefArchitect` | 架构决策与复杂问题审查 |
| `designer` | `ProductDesigner` | 产品体验、界面与交互设计 |
| `fixer` | `SoftwareEngineer` | 明确范围内的代码实现 |
| `observer` | `QualityEngineer` | 测试与质量验证 |
| `council` | `ArchitectureCouncil` | 多模型技术评审 |
| `councillor` | `CouncilReviewer` | 单位技术评审委员 |

显示名称必须使用 ASCII 标识符（字母开头，可包含数字、`_` 和 `-`）。

## 项目级模型覆盖

| Agent | 模型 | 思考级别 |
| --- | --- | --- |
| `orchestrator` | `openai/gpt-5.6-terra` | `high` |
| `explorer` | `zhipuai-coding-plan/glm-5.3-flash` | `max` |
| `librarian` | `zhipuai-coding-plan/glm-5.3-flash` | `medium` |
| `oracle` | `openai/gpt-5.6-sol` | `high` |
| `designer` | `openai/gpt-5.6-luna` | `medium` |
| `fixer` | `zhipuai-coding-plan/glm-5.3` | `max` |
| `observer` | 继承会话或全局模型 | — |
| `council` / `councillor` | 继承会话或全局模型 | — |

## Council 评审组

默认评审 preset 为 `three-model-review`，包含三位独立委员：

| 委员 | 模型 | 思考级别 |
| --- | --- | --- |
| `glm53` | `zhipuai-coding-plan/glm-5.3` | `max` |
| `gpt56sol` | `openai/gpt-5.6-sol` | `high` |
| `deepseekV4Pro` | `deepseek/deepseek-v4-pro` | 模型默认值 |
