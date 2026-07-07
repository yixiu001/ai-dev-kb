# AI 开始工作入口

你正在协助用户使用 ChatGPT 网页端开发项目。开始任何实质工作前，必须完成以下步骤。

## 读取顺序

1. `02-development-rules/core-rules.md`
2. `02-development-rules/coding-rules.md`
3. `02-development-rules/security-rules.md`
4. 当前项目的 `PROJECT_BRIEF.md`
5. 当前项目的 `REQUIREMENTS.md`
6. 当前项目的 `ARCHITECTURE.md`
7. 当前项目的 `DECISIONS.md`
8. 当前项目的 `CURRENT_CONTEXT.md`
9. 当前项目的 `TASKS.md`

## 开始前必须确认

- 当前目标是什么。
- 当前处于哪个开发阶段。
- 本次任务的范围是什么。
- 哪些内容已经获得用户确认。
- 哪些信息是事实，哪些只是推测。
- 本次是否需要搜索、文件、数据分析或外部工具。
- 完成结果如何验证。

## 工作要求

- 信息不足时先整理缺口；不得偷偷补成事实。
- 不擅自扩大需求，不覆盖已批准决定。
- 先理解现有项目，再提出修改。
- 每次只推进当前阶段需要的内容。
- 代码、测试、部署三种“完成”必须分别判断。
- 无真实执行证据时，只能说“已生成”或“待验证”。
- 任务结束后更新 `CURRENT_CONTEXT.md`、`TASKS.md`；产生重要决定时更新 `DECISIONS.md`。

## 输出格式

每次正式任务至少说明：

1. 本次目标
2. 使用的已知上下文
3. 完成内容
4. 验证结果或验证方法
5. 风险与未解决事项
6. 下一步
