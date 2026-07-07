# Git 常用命令速查

```bash
# 查看状态
git status

# 创建并切换分支
git switch -c feature/my-task

# 查看修改
git diff
git diff --staged

# 选择修改并提交
git add -p
git commit -m "feat: describe change"

# 推送新分支
git push -u origin feature/my-task

# 获取远程更新
git fetch origin
git pull --ff-only

# 查看历史
git log --oneline --graph --decorate --all

# 取消暂存
git restore --staged <file>

# 恢复未提交文件
git restore <file>

# 安全撤销已共享 Commit
git revert <commit>

# 临时保存
git stash push -m "WIP"
git stash pop

# 查找丢失历史
git reflog
```

高风险命令如 `reset --hard`、`clean -fd`、强制推送和对共享分支 rebase，应先阅读 `09-Git常用命令手册.md` 和 `12-常见错误与恢复.md`。
