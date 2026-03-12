# 📋 工作流索引

> 快速找到你需要的工作流

---

## 🆕 今日新增 (Day 001 - 2026-03-10)

### ✅ daily-briefing (每日简报)

**分类：** 办公效率  
**难度：** ⭐⭐  
**状态：** ✅ 已完成

**功能：** 每天早上 8 点自动汇总新闻、天气、日程

**[查看详细说明](productivity/daily-briefing/README.md)**

---

## 📂 按分类查找

### 💼 办公效率 (Productivity)

| 工作流 | 难度 | 状态 | 链接 |
|--------|------|------|------|
| daily-briefing | ⭐⭐ | ✅ | [查看](productivity/daily-briefing/) |
| meeting-notes | ⭐⭐ | 🚧 准备中 | - |
| email-summary | ⭐⭐⭐ | 🚧 准备中 | - |

### 💻 开发效率 (Development)

| 工作流 | 难度 | 状态 | 链接 |
|--------|------|------|------|
| pr-review | ⭐⭐⭐ | 🚧 准备中 | - |
| bug-triage | ⭐⭐⭐ | 🚧 准备中 | - |

### 📱 社交媒体 (Social Media)

| 工作流 | 难度 | 状态 | 链接 |
|--------|------|------|------|
| weibo-post | ⭐⭐ | 🚧 准备中 | - |

---

## 📅 更新计划

| 日期 | 新增工作流 | 分类 |
|------|-----------|------|
| Day 001 (03-10) | daily-briefing | 办公效率 |
| Day 002 (03-11) | meeting-notes | 办公效率 |
| Day 003 (03-12) | pr-review | 开发效率 |
| Day 004 (03-13) | email-summary | 办公效率 |
| Day 005 (03-14) | weibo-post | 社交媒体 |

---

## 🔔 订阅更新

- ⭐ Star 项目 - 获取更新通知
- 👁️ Watch 项目 - 实时通知
- 📢 查看 [DAILY_UPDATES](../DAILY_UPDATES.md)

---

**最后更新:** 2026-03-13 (Day 004)

---

## 💡 工作流调试技巧（2026-03-13 新增）

> 当工作流不按预期运行时，可以参考以下调试步骤：

### 1. 检查 Cron 任务状态

```bash
# 查看所有任务
openclaw cron list

# 查看特定任务的执行历史
openclaw cron runs <job-id>
```

### 2. 检查日志

```bash
# 查看 Gateway 日志
openclaw gateway status

# 查看最近的系统消息
openclaw logs --limit 50
```

### 3. 隔离测试

```bash
# 手动触发工作流进行测试
openclaw cron run <job-id>

# 使用 isolated session 避免污染主对话
openclaw agent -m "测试工作流" --session-id test-workflow
```

### 4. 常见问题

| 问题 | 解决方案 |
|------|---------|
| 任务不执行 | 检查 Gateway 状态，确认 cron 启用 |
| 输出不完整 | 检查 timeout 设置，增加 yieldMs |
| 模型切换失败 | 确认模型名称正确，重启 Gateway |

---

## 🆕 2026-03-13 更新

- ✅ 更新索引日期至 2026-03-13
- ✅ 新增工作流调试技巧章节
- ✅ 补充常见问题排查方法

---

## 🆕 2026-03-12 更新

- ✅ 更新索引日期
- ✅ daily-briefing 说明文档已完善
- ✅ 工作流分类优化
