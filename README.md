# AI Dev KB

> 帮助普通用户使用 AI，从一个想法开始，开发并上线能够服务真实用户的复杂软件产品。

## 我是第一次使用

我不需要先读完整个知识库。

直接打开：

[`USER_START.md`](./USER_START.md)

然后按新手实战路线逐步完成：

```text
准备开发环境
→ 创建第一个项目会话
→ 明确产品和需求
→ 设计可上线架构
→ 开发第一个可用功能
→ 测试和修复
→ 部署到线上
→ 处理卡点并持续迭代
```

每一步都会告诉我：

- 在哪里操作；
- 需要准备什么；
- 可以复制给 AI 的提示词；
- AI 应该返回什么；
- 我怎样检查；
- 怎样才算完成；
- 卡住时怎么办。

## 这个知识库为什么存在

AI 很容易生成代码和页面，但复杂项目经常失败在：

- AI 没有真正理解项目；
- 需求在聊天中不断变化；
- 修改范围失控；
- 登录存在但权限错误；
- 本地能运行，生产环境失败；
- AI 说“完成”，但没有真实测试；
- 项目换聊天或换 AI 后重新从零开始；
- 上线后没有日志、监控、回退和成本控制。

这个知识库把大型项目开发转换成可以被用户理解、被 AI 执行、被真实证据验证的连续流程。

## 文档分成三类

### 1. 用户实战课程

入口：[`00-user-guide/`](./00-user-guide/)

用户文章采用第一人称、步骤、案例、流程图、工作表和可复制提示词。

### 2. AI 工程规范

入口：

- [`AI_START.md`](./AI_START.md)
- [`AI_DOCS.md`](./AI_DOCS.md)
- [`01-ai-collaboration/`](./01-ai-collaboration/)
- [`02-product-definition/`](./02-product-definition/)
- [`03-system-design/`](./03-system-design/)
- [`04-delivery/`](./04-delivery/)
- [`06-platforms/`](./06-platforms/)

AI 文档保持结构化、严谨和可执行，约束上下文、任务、修改、测试、发布和证据。

### 3. 我和 AI 共同维护的项目文件

从 [`05-project-template/`](./05-project-template/) 复制：

```text
PROJECT.md
PRD.md
ARCHITECTURE.md
PLAN_AND_STATE.md
DECISIONS_RISKS_EVIDENCE.md
RELEASE.md
```

用户教程用于帮助我理解，正式项目文件才代表当前项目事实。

## 新手主线

| 阶段 | 实战文章 | 实际产物 |
|---|---|---|
| 起点 | `00-新手实战总路线.md` | 完整路线图 |
| 准备 | `01-30分钟准备开发环境.md` | AI 工作空间、GitHub、运行环境 |
| 立项 | `02-我创建第一个项目会话.md` | `PROJECT.md` |
| 需求 | `03-我把想法变成可开发需求.md` | `PRD.md` |
| 架构 | `04-我让AI设计可上线的系统.md` | `ARCHITECTURE.md` |
| 开发 | `05-我开发第一个可用功能.md` | Task、代码、Commit |
| 验证 | `06-我测试并修复功能.md` | 测试与证据 |
| 发布 | `07-我把项目部署到线上.md` | 线上版本和 Runbook |
| 恢复 | `08-我卡住时怎样让AI自救.md` | 诊断与恢复流程 |

## 两个直接可用的工具

- [`新手项目工作表`](./00-user-guide/workbook/新手项目工作表.md)
- [`新手提示词包`](./00-user-guide/prompts/新手提示词包.md)

## 支持的 AI 平台

通用核心不绑定单一 AI。

当前首个完整适配器是：

- [`ChatGPT 网页端`](./06-platforms/chatgpt-web/README.md)

后续可以增加 Claude Code、Cursor、Gemini CLI、GitHub Copilot 等平台适配器，而不重写项目核心文档。

## 最重要的状态规则

```text
GENERATED  已生成，未真实运行
EXECUTED   已运行，未完整验收
VERIFIED   需求和检查通过
RELEASED   已发布到生产环境
OBSERVED   已经过真实用户和生产观察
```

没有真实证据时，AI 不得提升状态。

## 版本

当前版本：`V1.3 Novice Hands-on`  
更新日期：`2026-07-07`

调研和参考来源见：

- [`00-research/FINDINGS.md`](./00-research/FINDINGS.md)
- [`00-research/REFERENCES.md`](./00-research/REFERENCES.md)
