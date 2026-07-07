# Actions、Pages、Packages 与 Codespaces

> 面向：希望把 GitHub 从代码仓库升级为自动化开发平台的用户

## GitHub Actions

Actions 用于自动执行工作流，例如：

- 安装依赖；
- 运行格式检查；
- 构建项目；
- 运行测试；
- 安全扫描；
- 生成构建产物；
- 部署到测试或生产环境；
- 定时运行任务。

工作流文件放在：

```text
.github/workflows/
```

一个基础 Node.js CI 示例：

```yaml
name: CI

on:
  pull_request:
  push:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 22
          cache: npm
      - run: npm ci
      - run: npm run lint
      - run: npm test
      - run: npm run build
```

## Actions 中的 Secrets

密码和 Token 应存入 GitHub Secrets，不写入 YAML 或仓库。

常见层级：

- Repository secrets；
- Environment secrets；
- Organization secrets。

工作流仍需遵守最小权限，不要默认给所有任务写入仓库和生产环境的权限。

## Artifacts 和 Cache

- Artifact：保存构建结果、测试报告和日志；
- Cache：加速依赖安装，不应作为正式发布文件的唯一来源。

Artifacts 和 Packages 可能共享或占用套餐存储额度，应设置保留期限。

## Environments

环境可以表示：

- test；
- staging；
- production。

环境可以配置：

- Secrets；
- 允许部署的分支；
- 审批人；
- 等待时间；
- 保护规则。

生产部署应使用 Environment，而不是直接在普通工作流中暴露所有生产密钥。

## GitHub Pages

Pages 适合托管：

- 项目文档；
- 静态网站；
- 作品集；
- 前端构建产物。

它不直接提供传统后端数据库和长期运行服务器。动态应用通常需要其他部署平台。

## GitHub Packages

Packages 用于发布和保存：

- npm 包；
- Maven 包；
- NuGet 包；
- RubyGems；
- Container images。

私有包的存储和流量可能计费。发布包时应使用版本号、权限和自动化流程。

## GitHub Codespaces

Codespaces 是云端开发环境，适合：

- 不想配置本地环境；
- 快速进入统一开发环境；
- 临时审查 PR；
- 教学和演示；
- 在不同设备继续开发。

它基于容器和配置文件，可以在仓库中加入：

```text
.devcontainer/devcontainer.json
```

Codespaces 有计算和存储用量。个人套餐包含一定免费额度，超过后需要设置预算或付费。

## GitHub Releases

Releases 用于发布正式版本，可以关联 Tag、自动生成发行说明并上传构建文件。

推荐流程：

```text
合并发布内容
→ 创建版本 Tag
→ Actions 构建和测试
→ 生成 Release
→ 上传产物
→ 部署或分发
```

## 一人项目的最低自动化

至少建立：

1. PR 时运行 lint、test、build；
2. main 更新时再次运行完整检查；
3. 生产发布使用独立环境和 Secret；
4. 失败时禁止自动继续部署；
5. 保存测试报告和部署结果。

## 成本检查

- [ ] 我知道 Actions 每月包含分钟；
- [ ] 我知道 public 与 private 仓库计费可能不同；
- [ ] 我已限制 Artifact 保留时间；
- [ ] 我已设置 Codespaces 和 Actions 预算；
- [ ] 自动任务不会无限重试；
- [ ] 定时任务频率合理；
- [ ] AI 不会未经批准重复运行高成本工作流。
