# 设计文档 — Design Doc

> 项目：个人网站 — Ethan Li | 版本：V1.0 | 日期：2026-07-25

---

## 1. 技术选型

| 维度 | 选型 | 原因 |
|------|------|------|
| 框架 | Jekyll 4.x | GitHub Pages 原生支持 |
| 主题 | Academic Pages | 基于 Minimal Mistakes，适合学术/个人作品集 |
| 内容格式 | Markdown + YAML Front Matter | 结构化，与 Git 友好 |
| 托管 | GitHub Pages | 免费、自动 HTTPS、全球 CDN |
| 部署 | Deploy from a branch: master | push 触发自动构建 |

## 2. 目录结构

```
_config.yml        # 站点全局配置
_data/             # 结构化数据
  navigation.yml   # 导航栏配置
_pages/            # 独立页面
  about.md         # 首页（中英文双语）
  projects.md      # 项目展示（硬编码卡片）
  cv.md            # 在线简历
_portfolio/        # （已删除，改用硬编码）
_posts/            # （已清空模板示例）
_publications/     # （已清空）
_talks/            # （已清空）
_teaching/         # （已清空）
images/            # 图片资源
  profile.png      # 头像
docs/              # 项目文档
  prd.md           # 产品需求文档
  design.md        # 本文件
  checklist.md     # 任务清单
```

## 3. 页面结构

```
┌─────────────────────────────┐
│ 导航 Nav: Home / Projects / CV │
├─────────────────────────────┤
│ 侧边栏                       │
│ ┌───┐                      │
│ │头像│ 姓名: Ethan Li       │
│ └───┘ Bio | 邮箱 | GitHub | LinkedIn │
├─────────────────────────────┤
│ 主内容区                     │
│ - 首页: 中英文双语简介        │
│ - Projects: 项目卡片         │
│ - CV: 教育/技能/项目         │
├─────────────────────────────┤
│ 页脚                         │
└─────────────────────────────┘
```

## 4. 颜色与字体

主色 #1A3C6E（深蓝） | 辅色 #2D7D9A（湖蓝）
背景 #F5F7FA（浅灰） | 正文 #333333（深灰）

字体：system-ui / Microsoft YaHei / PingFang SC

## 5. 关键决策记录

| 决策 | 原因 |
|------|------|
| 项目卡片硬编码而非 Jekyll collection | _portfolio/ 集合因 Liquid 解析 % 字符反复失败 |
| 文件名 portfolio.html → projects.md | 避免与 portfolio 集合命名冲突 |
| URL 从 /portfolio/ 改为 /projects/ | 匹配页面标题，解决 permalink 冲突 |
| 删除 _portfolio/ 目录 | 改用 projects.md 页面内直接嵌入 HTML |
| 添加 _portfolio 到 include 列表 | 尝试让集合生效（后因硬编码方案废弃） |
| 强制推送 (force push) | 本地与远程分支分歧导致无法正常推送 |
| IP 直连 + SSL 禁用 | VPN 阻断 github.com DNS 解析时的临时解决方案 |

## 6. 响应式断点

Desktop ≥ 1024px：三列 | Tablet 768–1023px：两列 | Mobile ≤ 767px：单列

## 7. 隐私说明

- 纯静态页面，不设 Cookie，不嵌入第三方脚本
- 仅公开邮箱、GitHub、LinkedIn 作为联系方式
- 不包含身份证、手机号、住址、API Key 等敏感信息
