# Git 安装、配置与 GitHub 认证

> 面向：第一次在电脑上使用 Git 的用户

## 1. 安装 Git

### Windows

推荐安装 Git for Windows。安装后打开 PowerShell 或 Git Bash，执行：

```bash
git --version
```

如果返回版本号，说明安装成功。

### macOS

可以使用系统开发工具或包管理器安装。完成后同样执行：

```bash
git --version
```

### Linux

使用系统包管理器安装，例如 Debian/Ubuntu：

```bash
sudo apt update
sudo apt install git
```

## 2. 配置用户名和邮箱

```bash
git config --global user.name "你的名字"
git config --global user.email "你的GitHub邮箱"
```

查看配置：

```bash
git config --global --list
```

Git 的提交邮箱会影响 GitHub 是否把 Commit 关联到我的账户。需要隐私时可以使用 GitHub 提供的 noreply 邮箱。

## 3. 设置默认分支

```bash
git config --global init.defaultBranch main
```

以后执行 `git init` 时默认创建 `main`。

## 4. 设置换行符

Windows 常见：

```bash
git config --global core.autocrlf true
```

macOS/Linux 常见：

```bash
git config --global core.autocrlf input
```

团队应通过 `.gitattributes` 统一规则，避免同一个文件因为换行符产生大面积 Diff。

## 5. 连接 GitHub 的两种方式

### HTTPS

仓库地址类似：

```text
https://github.com/owner/repo.git
```

优点：容易理解，适合凭证管理器。

GitHub 不再使用账号密码进行 Git 操作，通常使用浏览器登录、Git Credential Manager 或 Personal Access Token。

### SSH

仓库地址类似：

```text
git@github.com:owner/repo.git
```

优点：长期开发方便，不需要反复输入凭证。

生成密钥示例：

```bash
ssh-keygen -t ed25519 -C "你的GitHub邮箱"
```

启动代理并添加密钥后，把公钥内容添加到 GitHub 账户的 SSH keys。

测试：

```bash
ssh -T git@github.com
```

不要把私钥内容发给 AI、上传到仓库或复制到公开聊天。

## 6. GitHub CLI

GitHub CLI 命令是 `gh`，可以：

- 登录 GitHub；
- 创建仓库；
- 创建和查看 PR；
- 查看 Issue；
- 查看 Actions；
- 管理 Release。

登录：

```bash
gh auth login
```

检查状态：

```bash
gh auth status
```

Git 和 `gh` 是不同工具：Git 管理版本，`gh` 操作 GitHub 平台功能。

## 7. 克隆仓库

HTTPS：

```bash
git clone https://github.com/owner/repo.git
```

SSH：

```bash
git clone git@github.com:owner/repo.git
```

进入目录：

```bash
cd repo
```

检查远程地址：

```bash
git remote -v
```

## 8. 把本地项目连接到 GitHub

```bash
git init
git add .
git commit -m "chore: initialize project"
git remote add origin https://github.com/owner/repo.git
git push -u origin main
```

执行 `git add .` 前先检查 `.gitignore`，避免把密钥和大型依赖提交进去。

## 9. Personal Access Token

Token 应：

- 使用最小权限；
- 设置有效期；
- 使用清晰名称；
- 不写入代码；
- 不发送到聊天；
- 不共享给其他人；
- 不再使用时立即撤销。

优先使用细粒度 Token，只授权必要仓库和操作。

## 10. 安装完成检查

```bash
git --version
git config --global user.name
git config --global user.email
gh auth status
git remote -v
```

- [ ] Git 可以运行；
- [ ] 用户名和邮箱正确；
- [ ] 默认分支是 main；
- [ ] HTTPS 或 SSH 认证成功；
- [ ] 可以克隆私有仓库；
- [ ] Token 和私钥没有泄露。

## 常见问题

### `git` 不是内部或外部命令

Git 未安装，或终端尚未刷新 PATH。重新打开终端并检查安装目录。

### 一直要求登录

检查 Credential Manager、Token 是否过期，或改用 SSH。

### Commit 没显示在 GitHub 贡献图

检查提交邮箱是否与 GitHub 账户关联、Commit 是否已 Push，以及仓库可见性设置。
