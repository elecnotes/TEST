# 常用 Git 工作流 & 命令小抄

下面是一套典型的开发流程与常用命令，适合日常使用。

1) 获取仓库并新建分支
```bash
git clone git@github.com:owner/repo.git
cd repo
git fetch origin
git checkout -b feat/123-brief-description origin/main
```

2) 开发流程（本地）
```bash
# 编辑代码...
git status
git add .
git commit -m "feat(auth): add login endpoint (#123)"
```

3) 推送分支并在 GitHub 创建 PR
```bash
git push -u origin feat/123-brief-description
# 然后打开 GitHub 新建 PR，填写模板
```

4) 同步远端 main（处理冲突）
```bash
git checkout main
git pull origin main
git checkout feat/123-brief-description
git rebase main   # 或 git merge main
# 解决冲突 -> git add . -> git rebase --continue
git push --force-with-lease  # 若使用 rebase
```

5) 合并策略（由仓库维护者选择）
- Merge commit：保留合并节点
- Squash and merge：把多个提交压成一个（清理历史)
- Rebase and merge：将提交放在目标分支之上（保持线性历史）

6) 常见命令速查
```bash
git log --oneline --graph --decorate
git diff HEAD~1..HEAD
git stash        # 临时保存工作区改动
git stash pop
git reset --soft <commit>  # 调整最近提交
```

注意：在共享分支上避免强推（force push）除非你清楚后果并与团队沟通。
