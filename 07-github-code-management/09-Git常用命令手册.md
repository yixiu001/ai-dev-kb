# Git 常用命令手册

> 面向：日常开发、撤销错误和查看历史的用户

## 1. 初始化与获取仓库

```bash
git init
git clone <仓库地址>
```

- `git init`：把当前目录变成 Git 仓库；
- `git clone`：下载远程仓库和历史。

## 2. 查看当前状态

```bash
git status
git status -sb
```

这是最常用、也最安全的命令。执行任何高风险操作前先看状态。

## 3. 查看变化

```bash
git diff
git diff --staged
git diff main...feature/login
```

- `git diff`：尚未暂存的修改；
- `git diff --staged`：准备提交的修改；
- 分支比较：查看功能分支与 main 的差异。

## 4. 暂存修改

```bash
git add <文件>
git add src/
git add -p
```

`git add -p` 可以逐块选择修改，适合避免把无关变化放进同一个 Commit。

谨慎使用：

```bash
git add .
```

执行前先检查 `.gitignore` 和 `git status`。

## 5. 创建 Commit

```bash
git commit -m "feat: add user login"
```

修改最近一次 Commit 消息或加入遗漏文件：

```bash
git commit --amend
```

如果 Commit 已经推送并被他人使用，不要随意 amend 后强制推送。

## 6. 查看历史

```bash
git log
git log --oneline --graph --decorate --all
git show <commit>
git blame <文件>
```

- `log`：查看 Commit 历史；
- `show`：查看某个 Commit；
- `blame`：查看每一行最后由哪个 Commit 修改，不用于责怪个人。

## 7. 分支操作

```bash
git branch
git branch -a
git switch -c feature/login
git switch main
git branch -d feature/login
```

- `switch -c`：创建并切换分支；
- `branch -d`：安全删除已合并分支；
- `branch -D`：强制删除，使用前确认不需要保留。

## 8. 远程仓库

```bash
git remote -v
git remote add origin <地址>
git remote set-url origin <新地址>
```

## 9. 获取远程更新

```bash
git fetch origin
git pull --ff-only
git pull --rebase
```

- `fetch`：只下载远程信息，不修改当前分支；
- `pull`：下载并整合；
- `--ff-only`：只允许快进，避免意外生成合并 Commit；
- `--rebase`：把本地 Commit 放到最新远程历史之后，使用前理解 rebase。

新手遇到复杂历史时，优先 `fetch` 后查看差异，不要盲目执行 pull。

## 10. 推送

```bash
git push
git push -u origin feature/login
git push origin --delete feature/login
```

第一次推送新分支使用 `-u` 建立上游关系。

不要随意使用强制推送。确需改写个人分支历史时，优先：

```bash
git push --force-with-lease
```

它比普通强制推送多一层远程状态检查，但仍属于高风险操作。

## 11. 合并

```bash
git switch main
git merge feature/login
```

正式项目更推荐通过 GitHub Pull Request 合并，让自动测试和审查先完成。

## 12. 撤销工作区修改

恢复一个尚未暂存的文件：

```bash
git restore <文件>
```

恢复全部尚未暂存修改：

```bash
git restore .
```

这会丢失未保存的修改，执行前先看 `git diff`。

## 13. 取消暂存

```bash
git restore --staged <文件>
```

文件内容不会消失，只是移出暂存区。

## 14. 撤销已提交修改

### 安全产生反向 Commit

```bash
git revert <commit>
```

适合已经推送或进入共享历史的 Commit。

### 移动本地分支指针

```bash
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1
```

- `--soft`：保留修改在暂存区；
- `--mixed`：保留修改在工作区；
- `--hard`：删除修改，高风险。

共享分支优先使用 `revert`，不要随意 `reset --hard` 后强推。

## 15. 临时保存修改

```bash
git stash push -m "WIP login"
git stash list
git stash pop
git stash apply stash@{0}
```

Stash 适合短期切换任务，不应长期代替 Commit。

## 16. 标签

```bash
git tag
git tag -a v1.0.0 -m "Release v1.0.0"
git push origin v1.0.0
git push origin --tags
```

发布前确认 Tag 指向正确 Commit。

## 17. Rebase

```bash
git fetch origin
git rebase origin/main
```

交互式整理本地 Commit：

```bash
git rebase -i HEAD~3
```

Rebase 会改写历史。只在尚未共享的个人分支或团队明确允许时使用。

冲突后：

```bash
git add <已解决文件>
git rebase --continue
```

放弃：

```bash
git rebase --abort
```

## 18. Cherry-pick

```bash
git cherry-pick <commit>
```

用于把某个特定 Commit 应用到当前分支。经常 cherry-pick 可能表示分支规划混乱。

## 19. Worktree

```bash
git worktree add ../project-task-001 -b task/001 main
git worktree list
git worktree remove ../project-task-001
```

Worktree 允许同一个仓库同时打开多个分支，适合多个 AI 任务隔离。不同 Worktree 仍共享 Git 历史，不能让多个任务修改同一业务边界。

## 20. 清理未追踪文件

先预览：

```bash
git clean -n
```

确认后删除：

```bash
git clean -fd
```

高风险：会删除未追踪文件。先确认其中没有重要内容。

## 21. 恢复丢失 Commit

```bash
git reflog
```

找到历史位置后可以创建恢复分支：

```bash
git branch recovery/<名称> <commit>
```

`reflog` 是误 reset、误切换或分支删除后的重要恢复工具。

## 日常最小命令集

```bash
git status
git switch -c <分支>
git diff
git add -p
git commit -m "<类型>: <说明>"
git push -u origin <分支>
git fetch origin
git log --oneline --graph --all
```

## 高风险命令清单

执行前必须确认：

```text
git reset --hard
git clean -fd
git branch -D
git push --force
git rebase 已共享分支
git filter-repo / 历史清理
```

最好先建立备份分支或 Tag，并让 AI 明确说明影响和恢复方式。
