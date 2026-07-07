# GitHub 与 Git 代码管理实战手册

> 面向：需要用 GitHub 管理真实项目代码的普通用户

这个目录单独解决一件事：

> 我怎样安全地保存代码、管理版本、让 AI 修改代码、审查变更、恢复错误，并与其他人协作。

GitHub 不只是“上传代码的网站”。当项目变复杂后，它还负责：

- 保存代码和历史版本；
- 使用分支隔离不同任务；
- 使用 Pull Request 审查和合并修改；
- 使用 Issues 和 Projects 管理需求、缺陷和进度；
- 使用 Actions 自动构建、测试和部署；
- 使用权限、规则和安全扫描保护仓库；
- 使用 Releases、Tags 和 Packages 管理发布版本；
- 为 AI 开发任务提供可追踪的 Commit、Diff、PR 和证据。

## 我应该按什么顺序学习

| 顺序 | 文档 | 我会学到什么 |
|---|---|---|
| 1 | `01-Git与GitHub有什么区别.md` | 本地 Git 和云端 GitHub 分别负责什么 |
| 2 | `02-GitHub免费版与付费版.md` | Free、Pro、Team、Enterprise 怎样选择 |
| 3 | `03-仓库与文件管理.md` | 创建仓库、可见性、README、License、版本和大文件 |
| 4 | `04-分支Commit-PR与合并.md` | 不直接破坏主分支的标准开发流程 |
| 5 | `05-Issues-Projects与协作.md` | 管理需求、任务、缺陷、里程碑和讨论 |
| 6 | `06-Actions-Pages-Packages-Codespaces.md` | 自动测试、部署、网站、包和云端开发环境 |
| 7 | `07-权限安全与仓库保护.md` | 权限、分支保护、密钥、依赖和安全规则 |
| 8 | `08-Git安装配置与认证.md` | 在电脑上安装 Git 并连接 GitHub |
| 9 | `09-Git常用命令手册.md` | 日常命令、撤销、恢复、标签和 Worktree |
| 10 | `10-一人开发标准工作流.md` | 一个人如何稳定地开发和发布项目 |
| 11 | `11-AI与GitHub协作工作流.md` | 怎样让 ChatGPT、Claude Code、Cursor 安全修改仓库 |
| 12 | `12-常见错误与恢复.md` | 冲突、推送失败、误删、错误提交和密钥泄露的处理 |

## 我第一次只需要掌握什么

第一次使用时，我先掌握六个动作：

```text
git clone
→ git switch -c
→ git status
→ git add
→ git commit
→ git push
→ 创建 Pull Request
```

其他命令在遇到对应问题时再学。

## GitHub 网页和 Git 命令怎样配合

```mermaid
flowchart LR
    A[我的电脑] -- Git命令 --> B[本地仓库]
    B -- push --> C[GitHub远程仓库]
    C --> D[Pull Request和代码审查]
    D --> E[合并到main]
    E --> F[Actions测试和部署]
    C -- clone/pull --> A
```

## 与 AI Dev KB 的关系

- `05-project-template/` 保存项目事实和计划；
- 本目录说明代码怎样被保存、修改、审查和恢复；
- `PLAN_AND_STATE.md` 中的任务应关联分支、Commit 或 PR；
- `DECISIONS_RISKS_EVIDENCE.md` 可以记录测试结果和 PR 证据；
- AI 没有真实 GitHub 工具结果时，不得声称已经提交或合并。

## 资料更新时间

GitHub 套餐、配额和收费可能变化。

本目录套餐信息最后核验日期：`2026-07-07`。

使用前应再次查看 GitHub 官方 Pricing 和 Billing 页面。

完整参考资料见 [`REFERENCES.md`](./REFERENCES.md)。
