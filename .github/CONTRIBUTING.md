# 贡献指南（CONTRIBUTING）

欢迎贡献！以下是推荐的工作流和格式规范，有助于保持仓库整洁与协作高效。

## 分支与命名规范
- main / master：稳定分支，仅合并已通过审查与 CI 的变化。
- 开发分支（可选）：dev
- 功能/修复分支命名：
  - feat/<issue-number>-短描述（例如 feat/123-add-login）
  - fix/<issue-number>-短描述
  - chore/<短描述>

## 提交信息规范（推荐使用 Conventional Commits）
- feat(scope): 描述 — 新功能
- fix(scope): 描述 — 修复 bug
- docs: 描述 — 文档修改
- style: 描述 — 代码格式或风格调整（不影响逻辑）
- refactor: 描述 — 重构（不改变行为）
- test: 描述 — 添加/修改测试
- chore: 描述 — 构建/配置/其他杂项

示例：
- feat(auth): add token refresh endpoint
- fix(login): handle empty password case

## PR 大小与粒度
- 每个 PR 尽量聚焦一个功能或���个 bug，避免把多个不相关改动合并在一起。
- 如果改动很大，考虑拆成多个 PR（例如：API + 文档 + 前端三部分分别提交）。

## 代码审查要点
- 代码风格是否一致
- 是否包含单元测试 / 集成测试
- 是否考虑了错误处理与边界情况
- 性能/安全相关的影响（如 SQL 注入、XSS、敏感信息）
- 文档是否需要更新

## 运行测试与本地环境
- 本地搭建步骤（示例）：
  1. git clone <repo>
  2. cd <repo>
  3. npm install
  4. npm test

（请在项目根目录补充真实的运行/测试命令）

## 其他
- 如需大改动（架构层面），请先在 Issue 或 Discussion 中提出 RFC，征求团队意见。
- 感谢每一位贡献者！在合并时请保留有意义的 commit message，有助于变更追踪。
