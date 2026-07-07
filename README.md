# AI Dev KB

一个面向普通用户和 AI 的 **ChatGPT 网页端项目开发知识库**。

本知识库帮助用户使用 ChatGPT GPT-5.5，从一个模糊想法开始，逐步完成需求、产品设计、技术方案、开发、测试和上线。

## V1 目标

1. 说明 ChatGPT 网页端开发项目的能力与边界。
2. 建立 AI 必须遵守的开发规则。
3. 给普通用户一条从想法到上线的清晰路径。
4. 统一新项目的上下文结构，让 AI 快速理解项目。
5. 提供模型、工具、外部服务和关键阶段的选择标准。
6. 通过检查清单降低“代码看起来完成、实际不能运行”的风险。

## 目录

```text
ai-dev-kb/
├─ README.md
├─ AI_START.md
├─ 01-capabilities/
├─ 02-development-rules/
├─ 03-development-workflow/
├─ 04-tools-and-models/
├─ 05-project-template/
└─ 06-checklists/
```

| 目录 | 作用 |
|---|---|
| `01-capabilities` | ChatGPT 能做什么、不能做什么 |
| `02-development-rules` | AI 开发时必须遵守的规则 |
| `03-development-workflow` | 普通用户从想法到上线的流程 |
| `04-tools-and-models` | 模型、ChatGPT 工具和外部工具的选择方法 |
| `05-project-template` | 新项目标准知识包 |
| `06-checklists` | 需求、开发、测试和上线验收 |

## 普通用户如何开始

1. 在 ChatGPT 中建立一个新 Project。
2. 阅读 `01-capabilities/`，了解能力边界。
3. 复制 `05-project-template/`，建立自己的项目知识包。
4. 先填写 `PROJECT_BRIEF.md`，不清楚的部分让 ChatGPT 协助整理。
5. 按照 `03-development-workflow/` 逐阶段推进。
6. 每个阶段结束后使用 `06-checklists/` 验收。
7. 每次新对话开始时，让 AI 先读取 `AI_START.md` 和项目知识包。

## AI 如何开始

AI 必须先阅读 [`AI_START.md`](./AI_START.md)，再按其中顺序读取规则和项目文档。

## V1 范围

V1 只建立最小可用知识库，不包含：

- 大量编程语言教程
- 提示词大全
- 复杂多 Agent 系统
- 自动同步 GitHub
- 自动部署平台
- 所有第三方工具的完整说明

## 基本原则

- 用户负责目标、范围、审批、账号权限和真实验收。
- AI 负责分析、设计、实施建议、代码、测试方法和文档。
- AI 不得把“生成代码”描述成“已经运行成功”。
- 任何完成结论都必须有可验证证据。
- 项目事实写入项目文档，不依赖聊天记忆。

## 版本

当前版本：`V1.0.0`

更新日期：`2026-07-07`

## 官方参考

- https://help.openai.com/en/articles/11909943-gpt-53-and-gpt-55-in-chatgpt
- https://help.openai.com/en/articles/10169521-using-projects-in-chatgpt
- https://help.openai.com/en/articles/10500283-deep-research-in-chatgpt
- https://help.openai.com/en/articles/8437071-data-analysis-with-chatgpt
