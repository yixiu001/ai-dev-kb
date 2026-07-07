# 新项目知识包模板

复制本目录并改名为项目名称。它是 AI 理解项目的最小事实集合。

## 文件作用

| 文件 | 记录内容 |
|---|---|
| `PROJECT_BRIEF.md` | 项目为什么做、为谁做、V1 范围 |
| `REQUIREMENTS.md` | 功能、限制和验收标准 |
| `ARCHITECTURE.md` | 技术栈、模块、数据、接口和部署 |
| `TASKS.md` | 已完成、进行中和待办任务 |
| `DECISIONS.md` | 已批准的重要选择及原因 |
| `CURRENT_CONTEXT.md` | 当前版本、阶段、阻塞和本次任务 |

## AI 读取顺序

```text
PROJECT_BRIEF.md
→ REQUIREMENTS.md
→ ARCHITECTURE.md
→ DECISIONS.md
→ CURRENT_CONTEXT.md
→ TASKS.md
```

## 使用规则

- 不确定的信息写“待确认”，不要编造。
- 已批准结论与候选建议分开。
- 每个重要文件写更新时间。
- 当前状态只放在 `CURRENT_CONTEXT.md` 和 `TASKS.md`。
- 历史决定不要删除，使用“已替代”标记。
- 项目发生重要变化时同步更新相关文件。
