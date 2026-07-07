# AI 文档索引与解释规则

> 面向：AI

## 1. 文档分类

本仓库包含三类文档，AI 必须区分其权威性。

### A. 用户教育文档

位置：

- `README.md`
- `USER_START.md`
- `00-user-guide/`

用途：帮助用户理解怎样与 AI 合作。可以包含故事、比喻、案例和简化表达。

权威性：**非正式说明**。其中的案例、示例名称、示例功能和示例数据不得被当作当前项目需求。

### B. AI 工程规范

位置：

- `AI_START.md`
- `01-ai-collaboration/`
- `02-product-definition/`
- `03-system-design/`
- `04-delivery/`
- `06-platforms/`

用途：约束 AI 的分析、设计、实施、验证、工具使用和交接行为。

权威性：**通用规范**。当具体项目有更严格的已批准规则时，以具体项目规则为准；不得降低安全、质量和证据要求。

### C. 项目事实文档

位置：从 `05-project-template/` 复制到具体项目后的文件。

用途：记录当前项目的目标、需求、架构、状态、决定、风险、证据和发布信息。

权威性：**项目正式事实**。AI 不得用用户教育案例或历史聊天覆盖这些文件中的已批准内容。

## 2. 读取策略

```text
AI_START.md
→ 当前平台适配器
→ 当前项目状态
→ 当前任务关联的正式文档
→ 当前代码、测试、工具结果
→ 必要时查阅通用工程规范
```

不要默认读取全部用户文章。只有在需要解释给用户、提供教学示例或确认用户操作方式时，才读取 `00-user-guide/`。

## 3. 规范地图

| 问题 | 读取文档 |
|---|---|
| 如何确定工作模式、权限和状态 | `AI_START.md` |
| 如何管理上下文和交接 | `01-ai-collaboration/CONTEXT_AND_STATE.md` |
| 如何定义任务、控制修改和使用多 Agent | `01-ai-collaboration/TASK_CHANGE_MULTI_AGENT.md` |
| 如何划分人和 AI 的职责 | `01-ai-collaboration/OPERATING_MODEL.md` |
| 如何做产品发现与 PRD | `02-product-definition/PRODUCT_AND_PRD.md` |
| 如何建模领域并追踪需求 | `02-product-definition/TRACEABILITY_AND_DOMAIN.md` |
| 如何设计生产级架构 | `03-system-design/ARCHITECTURE.md` |
| 如何处理安全与隐私 | `03-system-design/SECURITY_PRIVACY.md` |
| 如何处理规模、可靠性和成本 | `03-system-design/SCALE_RELIABILITY_COST.md` |
| 如何实施和通过质量门禁 | `04-delivery/IMPLEMENTATION_AND_QUALITY.md` |
| 如何发布和处理生产运行 | `04-delivery/RELEASE_OPERATIONS.md` |
| 当前平台有什么能力和限制 | `06-platforms/<platform>/README.md` |

## 4. 输出纪律

AI 的正式产出必须：

- 使用项目文件中的 ID、术语和状态；
- 区分事实、假设、建议和已批准决定；
- 明确输入、输出、依赖和完成条件；
- 对修改范围和非修改范围作出声明；
- 为完成状态提供真实证据；
- 不把用户文章中的例子复制进项目文件，除非用户明确选择该方案；
- 不用营销式语言掩盖风险和未完成内容。

## 5. 面向用户解释时

当用户不理解专业概念时，可以：

- 使用第一人称场景；
- 使用具体案例；
- 使用 Mermaid 流程图、表格和前后对比；
- 先解释“这会影响我什么”，再解释术语；
- 给用户一个需要确认的最小选择，而不是一次展示全部工程细节。

但解释结束后，必须把正式结论写入相应项目文件，并恢复严格术语。

## 6. 冲突处理

如果用户文章、AI 规范和项目文件互相冲突：

1. 展示冲突；
2. 判断是否属于示例误用、规范更新或项目决定变化；
3. 不自动覆盖；
4. 需要改变项目事实时，创建正式决定并获得用户批准；
5. 更新所有受影响的追踪关系。
