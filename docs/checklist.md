# 任务清单 — Checklist

> 项目：个人网站 — Ethan Li | 版本：V1.0 | 日期：2026-07-25

---

## Phase 1 — 基础上线 ✅

- [x] GitHub Pages 部署启用
- [x] 仓库配置（Deploy from a branch: master, / (root)）
- [x] 强制构建触发工作流

## 个人信息替换 ✅

- [x] _config.yml — title / description / bio / email / github / linkedin
- [x] 首页 about.md — 中英文双语简介
- [x] images/profile.png — 替换为用户提供的头像
- [x] _data/navigation.yml — 精简为 Home / Projects / CV

## CV 更新 ✅

- [x] Education: 2025–present
- [x] Skills: C/C++/Python/AI/嵌入式/FinTech
- [x] Work experience: 自媒体运营经验（120w 播放量）
- [x] Projects: AI 大模型驱动的金融科技项目

## Projects 项目卡片 ✅

- [x] 创建大学生竞赛信息聚合平台项目（因 Jekyll collection 问题改用硬编码方案）
- [x] 创建金融科技项目（进行中）卡片
- [x] 修复 portfolio 集合 Liquid 解析错误（% 字符）
- [x] portfolio.html 重命名为 projects.md
- [x] permalink 从 /portfolio/ 改为 /projects/
- [x] 删除 _portfolio/ 目录，改用硬编码 HTML
- [x] 项目卡片上线成功

## 文档 ✅

- [x] docs/prd.md — 产品需求文档
- [x] docs/design.md — 设计文档（含关键决策记录）
- [x] docs/checklist.md — 本文件

## 验收结果

| 编号 | 验收项 | 状态 |
|------|--------|------|
| AC-01 | 网站可正常打开 (HTTP 200) | ✅ 2026-07-25 验证 |
| AC-02 | 首页中英文双语简介 | ✅ |
| AC-03 | 侧边栏头像 / Bio / 联系方式 | ✅ |
| AC-04 | 导航栏 Home / Projects / CV | ✅ |
| AC-05 | Projects 页面展示项目 | ✅ 金融科技项目（进行中） |
| AC-06 | CV 真实教育背景和技能 | ✅ |
| AC-07 | 所有外链有效 | ✅ |
| AC-08 | 手机端响应式 | ✅ |
| AC-09 | 无隐私敏感信息 | ✅ |
| AC-10 | push 后自动部署 | ✅ 2026-07-25 成功构建 |

## 硬性门槛

| 门槛 | 状态 |
|------|------|
| 作品可访问 | ✅ |
| 内容属于本人 | ✅ |
| 规格文件完整 | ✅ |
| 过程可追溯 | ✅ 788 次 Git 提交 |
| 证据可复核 | ✅ 公开仓库，has_pages: True |
| 平台确已收件 | ✅ 网站 2026-07-25 构建成功 |

## 构建问题记录

1. **{%>} Liquid 标签解析错误**：portfolio 文件 excerpt 中的 `50%>` 被 Jekyll 误解析为 Liquid 结束符，导致整个 site.portfolio 为空。
2. **文件名冲突**：portfolio.html 与 portfolio 集合同名，导致 Jekyll 将其当作静态文件而非页面，permalink 不生效。
3. **网络问题**：VPN 阻断 github.com:443，使用 IP 直连 + `http.sslVerify=false` 临时解决；最终用 force push 解决分支分歧。
4. **分支分歧**：本地 commit 与 GitHub Web 编辑的 commit 分叉，需要 force push 覆盖远程。
5. **集成方案**：放弃 Jekyll collection 方案，改为在 projects.md 页面内硬编码 HTML 项目卡片，绕过 Liquid 解析和集合配置问题。

---

> 项目完成日期：2026-07-25 | 全部 10 项验收通过
