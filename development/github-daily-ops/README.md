# 🔄 GitHub 每日运营工作流

> 自动化 GitHub 仓库的日常运营维护

---

## 📋 功能

- ✅ 每日自动更新 README 统计数据
- ✅ 检查并同步仓库最新提交
- ✅ 生成每日运营报告
- ✅ 自动推送更新到 GitHub

---

## ⚙️ 配置

### 前置条件

1. GitHub Personal Access Token
2. 已安装 `github` Skill
3. 配置好 Git 凭证

### 设置步骤

**1. 配置定时任务**

```bash
# 编辑 crontab
crontab -e

# 添加每日运营任务（早上 6:00）
0 6 * * * /path/to/github-daily-ops.sh >> /path/to/logs/github-ops.log 2>&1
```

**2. 配置环境变量**

```bash
# 在脚本中设置
GITHUB_TOKEN="your-token-here"
REPOS_DIR="$HOME/.openclaw/workspace/github-repos"
```

---

## 🔧 使用方法

### 手动执行

```bash
# 更新单个仓库
./github-daily-ops.sh openclaw-recommended-skills

# 更新所有仓库
./github-daily-ops.sh --all
```

### 自动执行

配置 crontab 后，每天早上 6:00 自动执行。

---

## 📊 输出示例

```
🦞 GitHub 每日运营 - 2026-03-18
==========================================
📁 openclaw-recommended-skills
  ✅ 统计数据已更新
  ✅ README 已更新
  ✅ 已推送到 GitHub

📁 openclaw-starter
  ✅ 统计数据已更新
  ✅ 已推送到 GitHub

==========================================
✅ 运营完成！共更新 3 个仓库
```

---

## 🔗 相关资源

- [GitHub CLI 文档](https://cli.github.com/manual/)
- [OpenClaw Cron 文档](https://docs.openclaw.ai/cron)

---

**创建时间:** 2026-03-18  
**维护者:** @xxuan66
