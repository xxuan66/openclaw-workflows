# 📰 每日简报工作流

> 每天早上 8 点自动汇总新闻、天气、日程

---

## 🎯 功能说明

自动执行以下任务：
1. ✅ 搜索今日热点新闻
2. ✅ 获取天气预报
3. ✅ 读取日历日程
4. ✅ 生成简报并发送

---

## 📦 所需 Skill

| Skill | 用途 | 必需 |
|-------|------|------|
| searxng | 新闻搜索 | ✅ |
| tavily-search | 实时信息 | ✅ |
| summarize | 内容摘要 | ✅ |
| gog | 日历读取 | ⭕ |

---

## ⚙️ 配置步骤

### 1. 创建 cron 任务

```bash
openclaw cron add \
  --schedule "0 8 * * *" \
  --command "openclaw agent -m '生成今日简报：新闻 + 天气 + 日程'" \
  --label "daily-briefing"
```

### 2. 配置通知渠道

**飞书：**
```bash
openclaw message send \
  --channel feishu \
  --target <chat_id> \
  --message "每日简报已就绪"
```

**Telegram：**
```bash
openclaw message send \
  --channel telegram \
  --target @username \
  --message "每日简报已就绪"
```

### 3. 测试运行

```bash
# 手动触发一次
openclaw agent -m "生成今日简报"
```

---

## 📋 示例输出

```
📰 每日简报 - 2026-03-10

🔥 热点新闻
1. OpenClaw 发布新版本
2. AI Agent 技术突破
3. ...

🌤️ 天气
上海：晴，15-22°C

📅 今日日程
- 10:00 团队会议
- 15:00 项目评审

祝您有美好的一天！
```

---

## 🔧 自定义

### 修改发送时间

编辑 cron 任务：
```bash
openclaw cron remove --label "daily-briefing"
openclaw cron add --schedule "0 7 * * *" ...  # 改为早上 7 点
```

### 添加更多内容

修改 agent 提示词：
```bash
openclaw agent -m "生成简报：新闻 + 天气 + 日程 + 股票 + 汇率"
```

---

## 📚 相关资源

- [openclaw-recommended-skills](https://github.com/xxuan66/openclaw-recommended-skills) - 推荐 Skill
- [openclaw-starter](https://github.com/xxuan66/openclaw-starter) - 场景配置

---

**创建日期:** 2026-03-10  
**难度:** ⭐⭐
