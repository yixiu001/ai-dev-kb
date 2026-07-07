# Issues、Projects 与协作

> 面向：需要管理需求、任务、缺陷和进度的用户

## Issues 用来做什么

Issue 可以表示新功能、Bug、技术债、调研、文档、发布准备或用户反馈。

一个合格 Issue 应包含：

```markdown
## 背景
## 用户结果
## 范围
## 明确不做
## 验收标准
- [ ]
## 风险与依赖
## 证据
```

## Labels

推荐使用少量统一标签：

```text
type:feature
type:bug
type:security
priority:high
status:blocked
area:billing
area:auth
```

## Milestones

Milestone 用于把 Issue 和 PR 归入版本或目标，例如：

- V1.0 首次上线；
- V1.1 订阅系统；
- 稳定性改进阶段。

## 父任务和子任务

复杂功能应拆分：

```text
团队订阅
├─ 创建组织
├─ 邀请成员
├─ 组织套餐
├─ 成员数量限制
└─ 数据隔离测试
```

每个子任务仍然需要独立验收标准。

## GitHub Projects

Projects 可以用 Table、Board 和 Roadmap 管理 Issue、PR 和草稿任务。

一人开发建议只保留：

```text
Backlog
→ Ready
→ In progress
→ In review
→ Verified
→ Released
```

常用字段包括 Priority、Area、Iteration、Estimate、Start date 和 Target date。

## Issue 与 PR 关联

PR 描述可以引用 Issue 编号。使用自动关闭关键词时，PR 合并后可关闭对应 Issue；只想建立关联时，可以写普通引用。

## Discussions

Discussions 适合开放式讨论、问答、公告和功能想法。已经明确可执行的工作应转成 Issue。

## AI 怎样使用 Issues

AI 可以帮助我：

- 把模糊需求整理成 Issue；
- 拆分父子任务；
- 生成验收标准；
- 从错误日志生成 Bug；
- 汇总里程碑进度。

AI 不得在没有批准时把建议自动变成正式范围。

## 推荐规则

- 一个 Issue 对应一个主要结果；
- 一个 PR 尽量对应一个 Issue；
- Issue 记录目标，PR 记录实际修改；
- 验证结果回写 Issue；
- 被阻塞时记录依赖和解除条件；
- 取消任务时保留历史和原因。

## 完成检查

- [ ] Issue 有背景、范围和验收标准；
- [ ] Labels 命名统一；
- [ ] 复杂功能已经拆分；
- [ ] Project 状态简单且真实；
- [ ] PR 与任务有关联；
- [ ] 发布目标使用 Milestone 管理。
