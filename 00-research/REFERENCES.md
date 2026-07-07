# 参考资料

访问与整理日期：2026-07-07

## 一、社区论坛与真实用户经验

- **[C1] Cursor Community — Context and large codebases**  
  https://forum.cursor.com/t/context-and-large-codebases/50750  
  主要启示：大型仓库最耗时的问题是找到正确上下文，不能依赖模型自动读取全部文件。

- **[C2] Reddit r/ChatGPTCoding — Use Context Handovers regularly to avoid hallucinations**  
  https://www.reddit.com/r/ChatGPTCoding/comments/1kv5sga  
  主要启示：长会话会漂移，应使用计划文件、阶段拆分和新会话交接。

- **[C3] Cursor Community — Structural failure modes**  
  https://forum.cursor.com/t/structural-failure-modes/161725  
  主要启示：Agent 可能在提问场景中擅自编辑、破坏不变量并在无测试时改变执行路径。

- **[C4] Reddit r/ClaudeAI — Existing codebases and context across features**  
  https://www.reddit.com/r/ClaudeAI/comments/1rdfgqj/vibe_coding_on_existing_codebases_is_a_nightmare/  
  主要启示：静态项目说明不能替代当前任务上下文和持续状态更新。

- **[C5] Reddit r/ClaudeCode — Managing multiple coding agents**  
  https://www.reddit.com/r/ClaudeCode/comments/1sr2ni6/how_are_you_guys_managing_multiple_ai_coding/  
  主要启示：Worktree 只隔离目录；真正降低冲突需要按模块和依赖图拆分所有权。

- **[C6] Replit Community — Deployment works in dev but fails in production**  
  https://replit.discourse.group/t/deployment-tips-please-bugs-problems/7308  
  主要启示：开发与生产环境差异、Secrets 和部署配置必须被显式管理。

- **[C7] Reddit r/vibecoding — Common failures after real users arrive**  
  https://www.reddit.com/r/vibecoding/comments/1rbruki/i_fix_apps_for_a_living_80_of_my_rescues_this/  
  主要启示：授权、支付失败、数据库设计、重复逻辑、错误处理和日志是原型产品化的主要缺口。

- **[C8] Gemini CLI GitHub Discussion — Biggest challenges**  
  https://github.com/google-gemini/gemini-cli/discussions/7432  
  主要启示：命令幻觉、终端挂起、过度覆盖文件和缺少最新文档接地是常见问题。

- **[C9] GitHub Community — Getting better results from Copilot Coding Agent**  
  https://github.com/orgs/community/discussions/174930  
  主要启示：任务必须缩小为直接步骤，并追踪测试覆盖、返工率和逃逸缺陷。

- **[C10] Reddit r/OpenAI — ChatGPT Projects stale-context anchoring**  
  https://www.reddit.com/r/OpenAI/comments/1tegniw/is_anyone_else_seeing_chatgpt_projects_get_stuck/  
  主要启示：多文件、长聊天中可能出现旧主题锚定，项目记忆不能代替当前状态文件。

- **[C11] Hacker News — Multi-agent software development is a distributed systems problem**  
  https://news.ycombinator.com/item?id=47761625  
  主要启示：多 Agent 需要共享状态、阶段门禁、确定性检查和失败恢复。

- **[C12] Stack Overflow — Is AI making your code worse?**  
  https://stackoverflow.blog/2024/03/22/is-ai-making-your-code-worse/  
  主要启示：AI 倾向新增代码而非复用已有代码，长期可能恶化维护性和测试覆盖。

- **[C13] Reddit r/vibecoding — Security failures in production apps**  
  https://www.reddit.com/r/vibecoding/comments/1np73ws/security_in_vibe_coded_web_apps_is_a_disaster/  
  主要启示：登录不等于授权，数据库行级权限必须真实测试。

## 二、实证研究

- **[R1] How Coding Agents Fail Their Users: 20,574 Real-World Sessions**  
  https://arxiv.org/abs/2605.29442  
  发现：七类失配覆盖项目读取、意图理解、规则遵循、范围、实现、执行和进度报告；多数可见解决仍需要用户明确纠正。

- **[R2] Where Do AI Coding Agents Fail? 33k Agentic Pull Requests**  
  https://arxiv.org/abs/2601.15195  
  发现：未合并 PR 通常改动更大、触及更多文件，并更常无法通过 CI；性能和缺陷修复任务更困难。

- **[R3] Evaluating AGENTS.md**  
  https://arxiv.org/abs/2602.11988  
  发现：上下文文件会增加探索和测试，但自动生成文件没有稳定提升成功率，平均增加约 20% 以上成本；最有价值的是短小、人工确认的额外信息。

- **[R4] Engineering Pitfalls in Claude Code, Codex, and Gemini CLI**  
  https://arxiv.org/abs/2603.20847  
  发现：对 3,800 多个公开 Bug 的分析中，API、集成和配置是重要根因，工具调用与命令执行是高发阶段。

- **[R5] Is Vibe Coding Safe?**  
  https://arxiv.org/abs/2512.03262  
  发现：功能正确不代表安全正确，面向生产的软件必须加入独立安全验证。

- **[R6] Novice Developers Produce Larger Review Overhead while Vibe Coding**  
  https://arxiv.org/abs/2602.23905  
  发现：低经验用户提交的 PR 变更更大、审查意见更多、接受率更低，不能用生成速度替代审查能力。

- **[R7] Unveiling Pitfalls: Why Code Agents Fail at GitHub Issue Resolution**  
  https://arxiv.org/abs/2503.12374  
  主要启示：执行环境、依赖、类型和数据库错误会显著增加推理和调试成本。

- **[R8] Developer Use of ChatGPT in GitHub Issue Trackers**  
  https://arxiv.org/abs/2412.06757  
  发现：ChatGPT 更多用于构思而非验证，测试相关使用不足，调试和自动化满意度较低。

## 三、官方与平台工程资料

- **[O1] OpenAI — Using Projects in ChatGPT**  
  https://help.openai.com/en/articles/10169521-using-projects-in-chatgpt

- **[O2] Cursor — Large Codebases**  
  https://docs.cursor.com/en/guides/advanced/large-codebases

- **[O3] Cursor — Agent Best Practices**  
  https://cursor.com/blog/agent-best-practices

- **[O4] Lovable — Response to April 2026 incident**  
  https://lovable.dev/blog/our-response-to-the-april-2026-incident

- **[O5] Lovable — Security overview**  
  https://docs.lovable.dev/features/security

- **[O6] Replit — Troubleshooting deployments**  
  https://docs.replit.com/build/troubleshooting

## 使用这些来源时的注意事项

- Reddit、Hacker News 和产品论坛主要提供问题发现与工作流经验，不应单独作为安全或架构结论的唯一依据。
- 论文提供总体趋势，但其模型、任务集和工具版本可能与当前 ChatGPT 网页端不同。
- 官方文档用于确认平台能力和操作方式，但不会完整披露用户实际失败模式。
- 本知识库只采用多个来源重复支持、且可转化为确定性工程措施的结论。
