# ⏰ Cron 自动化工作流

> 定时任务管理与自动化执行

**版本：** 1.0  
**创建日期：** 2026-03-11  
**作者：** @xxuan66

---

## 📋 概述

本工作流提供完整的定时任务管理方案，包括：
- 模型定时切换（夜间/白天）
- 每日简报生成
- GitHub 自动更新
- 批量任务编排

---

## 🚀 快速开始

### 1. 创建定时任务

```bash
# 每日简报 - 每天早上 9 点
openclaw cron add \
  --name "daily-briefing" \
  --schedule "0 9 * * *" \
  --message "生成今日简报：检查邮件、日历事件、天气情况" \
  --thinking minimal

# GitHub 更新 - 每天早上 6 点
openclaw cron add \
  --name "github-update" \
  --schedule "0 6 * * *" \
  --message "执行 GitHub 每日更新" \
  --thinking minimal
```

### 2. 查看任务列表

```bash
# 查看所有定时任务
openclaw cron list

# 查看任务详情
openclaw cron get <job-id>
```

### 3. 手动触发

```bash
# 立即执行指定任务
openclaw cron run <job-id>
```

---

## 🔄 模型定时切换

### 场景说明

- **夜间（22:00）**：切换到低成本模型，执行后台任务
- **白天（09:00）**：切换回默认模型，用于日常交互

### 配置示例

```json
{
  "name": "model-switch-night",
  "schedule": { "kind": "cron", "expr": "0 22 * * *" },
  "payload": { "kind": "systemEvent", "text": "已切换到夜间模型" },
  "sessionTarget": "main"
}
```

---

## 📦 批量任务编排

### 最佳实践

1. **合并检查任务**
   - 将邮件、日历、天气检查合并到一个 cron job
   - 减少 API 调用次数

2. **错峰执行**
   - 避开整点执行（如 9:05 而非 9:00）
   - 减少服务器负载

3. **独立会话**
   - 使用 `isolated session` 避免污染主对话
   - 每个任务使用独立的 session-id

---

## ⚠️ 注意事项

- 敏感信息（API keys）不要硬编码在 cron job 中
- 使用 `systemEvent` 类型用于主会话提醒
- 定期检查 cron 日志确保任务正常执行
- 定时任务使用 isolated session，避免污染主对话

---

## 📚 相关资源

- [OpenClaw Cron 文档](https://docs.openclaw.ai/cron)
- [DAILY_UPDATES.md](https://github.com/xxuan66/openclaw-recommended-skills/blob/main/DAILY_UPDATES.md)
- [openclaw-starter/cron-scenario.json](https://github.com/xxuan66/openclaw-starter/blob/main/configs/cron-scenario.json)

---

**更新日期：** 2026-03-11  
**维护者：** [@xxuan66](https://github.com/xxuan66)
