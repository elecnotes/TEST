# Pull Request 模板

请在新建 PR 时填写以下内容，便于审查与合并。

## 标题格式
- feat(scope): 简短描述
- fix(scope): 简短描述
- docs: 简短描述

示例：feat(auth): add login endpoint

---

## 说明（Description）
请简要说明这次变更做了什么，为什么要做，以及与 Issue 的关联。

- 变更点：
  - 
- 关联 Issue：Fixes #<issue-number> / Relates to #<issue-number>

---

## 类型（select one）
- [ ] Bug 修复 (fix)
- [ ] 新功能 (feat)
- [ ] 文档 (docs)
- [ ] 性能优化 (perf)
- [ ] 测试 (test)
- [ ] 其他（请说明）：

---

## Checklist（合并前请确保）
- [ ] 我已在本地运行并通过相关测试
- [ ] 我已在变更说明中写明影响范围和回滚方案（如有）
- [ ] 我已将变更拆分为小而可审查的提交（若适用）
- [ ] 我已更新/添加必要的文档
- [ ] CI 校验通过（或已知的 CI 问题说明）

---

## 测试步骤（如何在本地复现测试）
1. git checkout <branch>
2. ...
3. 期望结果：

---

## 备注 / 截图（如有）
