# 示例：Issue 与 Pull Request

下面包含两个示例 Issue（一个 Bug 报告和一个功能需求）以及一个示例 Pull Request。你可以直接复制这些文本在实际创建 Issue/PR 时使用，或在仓库中保留为示例参考。

---

## 示例 Issue（Bug 报告）

标题：bug: 登录页在输入空密码时返回 500 错误

描述：
- 重现步骤：
  1. 打开 https://example.com/login
  2. 在用户名框输入有效用户名（例如 test@example.com）
  3. 留空密码框，点击登录按钮
- 期望结果：
  - 前端应提示 "请输入密码" 或后端返回 400/422 的参数校验错误，不应出现 500 服务器错误。
- 实际结果：
  - 页面返回 500 错误，控制台看到后端抛出 NullPointerException（或对应语言的空引用异常）。
- 复现环境：
  - Web: Chrome 120 / macOS 13
  - 后端: api.example.com (v1.2.3)
- 日志或报错：
  - 后端日志片段：
    "java.lang.NullPointerException at com.example.auth.LoginHandler.handle(LoginHandler.java:45)"
- 暂时解决方法：
  - 无
- 优先级：P1
- 建议标签：bug, needs-triage, high-priority

---

## 示例 Issue（功能需求 / Task）

标题：feat: 增加用户导出为 CSV 的功能

背景与目标：
- 为什么需要：运维同学希望定期导出用户列表用于离线分析与客户支持。
- 用户场景：管理员在管理后台点击 "导出用户"，下载包含用户 ID、邮箱、注册时间和状态的 CSV 文件。

需求描述：
- 后端 API：GET /admin/users/export?format=csv
- 导出的字段：id, email, created_at, status
- 需支持过滤（按创建时间区间、状态）
- 权限：仅管理员角色可访问
- 成功标准：在 10 万用户规模下导出完成时间 < 60s（或返回任务异步下载 link）

相关链接：#12（如果存在）

建议标签：enhancement, backend, admin

---

## 示例 Pull Request（将与上方某个 Issue 关联）

标题：feat(admin): add CSV export for users (relates to #<issue-number>)

说明：
- 变更点：
  - 新增后端接口 /admin/users/export，支持 CSV 输出和按条件过滤
  - 增加单元测试覆盖导出逻辑
  - 更新文档（CONTRIBUTING.md 中添加导出接口说明）
- 关联 Issue：Relates to #<issue-number>

类型：新功能 (feat)

Checklist：
- [x] 本地通过相关单元测试
- [x] 已更新文档说明
- [ ] CI 校验通过

测试步骤（本地）：
1. git checkout <branch>
2. 启动后端服务（参见 README）
3. 发送请求：curl -u admin:pw "http://localhost:8080/admin/users/export?format=csv&status=active"
4. 期望结果：返回 CSV 文件，第一行包含标题 id,email,created_at,status

备注：若导出数据量较大，推荐后端异步化并返回临时下载链接，避免阻塞请求。

---

文件结束
