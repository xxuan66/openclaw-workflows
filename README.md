# ⚡ OpenClaw Workflows

> 🔄 OpenClaw 自动化工作流集合 - 从单一功能到自动化流程

[![Updated](https://img.shields.io/badge/updated-2026--03--13-blue)](https://github.com/xxuan66/openclaw-workflows)
[![License](https://img.shields.io/badge/license-MIT-blue)](https://github.com/xxuan66/openclaw-workflows/blob/main/LICENSE)
[![Stars](https://img.shields.io/github/stars/xxuan66/openclaw-workflows?style=social)](https://github.com/xxuan66/openclaw-workflows/stargazers)

---

**⭐ 如果这个项目对你有帮助，请给个 Star！**

---

## 🚀 快速开始

### 安装工作流

```bash
# 克隆项目
git clone https://github.com/xxuan66/openclaw-workflows.git

# 选择工作流
cd openclaw-workflows/productivity

# 查看使用说明
cat daily-briefing/README.md
```

---

## 📂 工作流分类

### 💼 办公效率 (Productivity)

| 工作流 | 描述 | 难度 |
|--------|------|------|
| **daily-briefing** | 每日简报自动汇总 | ⭐⭐ |
| **meeting-notes** | 会议纪要整理 | ⭐⭐ |
| **email-summary** | 邮件摘要分类 | ⭐⭐⭐ |
| **task-manager** | 任务自动管理 | ⭐⭐⭐ |

---

### 💻 开发效率 (Development)

| 工作流 | 描述 | 难度 |
|--------|------|------|
| **pr-review** | PR 自动审查 | ⭐⭐⭐ |
| **bug-triage** | Bug 自动分类 | ⭐⭐⭐ |
| **release-notes** | 发布说明生成 | ⭐⭐ |
| **code-document** | 代码文档生成 | ⭐⭐⭐⭐ |

---

### 📱 社交媒体 (Social Media)

| 工作流 | 描述 | 难度 |
|--------|------|------|
| **weibo-post** | 微博自动发布 | ⭐⭐ |
| **content-calendar** | 内容日历管理 | ⭐⭐⭐ |
| **trend-monitor** | 热点监控 | ⭐⭐⭐⭐ |

---

### 📊 研究分析 (Research)

| 工作流 | 描述 | 难度 |
|--------|------|------|
| **paper-summary** | 论文摘要 | ⭐⭐⭐ |
| **market-research** | 市场调研 | ⭐⭐⭐⭐ |
| **competitor-analysis** | 竞品分析 | ⭐⭐⭐⭐ |

---

## 📋 工作流示例

### 每日简报 (daily-briefing)

**功能：** 每天早上 8 点自动汇总新闻、天气、日程

**所需 Skill：**
- searxng - 新闻搜索
- tavily-search - 实时信息
- summarize - 内容摘要

**配置步骤：**

1. 创建 cron 任务
```bash
openclaw cron add --schedule "0 8 * * *" \
  --command "openclaw agent -m '汇总今日新闻'"
```

2. 配置通知渠道
```bash
openclaw message send --channel feishu \
  --target <chat_id> --message "每日简报已就绪"
```

**完整配置：** [查看 daily-briefing/](productivity/daily-briefing/)

---

### PR 自动审查 (pr-review)

**功能：** 自动审查 GitHub PR，检查代码质量

**所需 Skill：**
- github - GitHub API
- skill-vetter - 安全检查

**配置步骤：**

1. 配置 GitHub Token
```bash
export GH_TOKEN=ghp_xxx
```

2. 设置 webhook
```bash
# 在 GitHub 仓库设置中添加 webhook
# Payload URL: your-server/webhook
```

**完整配置：** [查看 pr-review/](development/pr-review/)

---

## 🔧 创建工作流

### 工作流结构

```
workflow-name/
├── README.md           # 使用说明
├── config.json         # 工作流配置
├── skills.json         # 所需 Skill
├── cron.json           # 定时任务（可选）
└── examples/           # 使用示例
```

### 模板文件

**config.json 示例：**
```json
{
  "name": "daily-briefing",
  "description": "每日简报自动汇总",
  "version": "1.0.0",
  "skills": ["searxng", "tavily-search", "summarize"],
  "cron": "0 8 * * *",
  "output": ["feishu", "telegram"]
}
```

---

## 📚 相关项目

| 项目 | 描述 |
|------|------|
| [openclaw-recommended-skills](https://github.com/xxuan66/openclaw-recommended-skills) | Skill 推荐清单 |
| [openclaw-starter](https://github.com/xxuan66/openclaw-starter) | 场景化配置模板 |
| [openclaw-commands](https://github.com/xxuan66/openclaw-commands) | 常用指令速查 |

---

## 🤝 贡献

欢迎分享你的工作流！

1. Fork 项目
2. 创建工作流目录
3. 添加配置和文档
4. 提交 PR

### 贡献指南

- 提供完整的使用说明
- 包含配置示例
- 标注所需 Skill
- 说明适用场景

---

## 💡 工作流灵感

**不知道做什么工作流？**

- 自动回复常见邮件
- 社交媒体定时发布
- 代码提交自动分类
- 竞品价格监控
- 行业新闻聚合
- 学习笔记整理

---

## 📄 License

MIT License

---

**最后更新:** 2026-03-13  
**维护者:** [@xxuan66](https://github.com/xxuan66)

---

## 🆕 2026-03-13 更新

- ✅ 更新 README 日期标识至 2026-03-13
- ✅ WORKFLOWS_INDEX.md 补充使用建议
- ✅ 新增工作流调试技巧

---

## 🆕 2026-03-12 更新

- ✅ 更新 README 日期标识
- ✅ 工作流索引小幅完善
- ✅ 添加工作流灵感扩展
