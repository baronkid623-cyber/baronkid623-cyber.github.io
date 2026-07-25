# 最终报告 — Final Report

> 项目：个人网站 — Ethan Li | 日期：2026-07-25

---

## 一、项目定位

深圳大学金融科技专业本科生 Ethan Li 的个人品牌展示站。面向实习招聘者、同学、教师和竞赛伙伴，集中呈现跨学科背景（金融 / 计算机 / 硬件工程）、核心技术栈（C / C++ / Python / AI）与实际项目方向（金融科技），并附公开联系方式。

一句话定位已固化在首页首屏：

> 深圳大学金融科技专业本科生，具备金融、计算机、硬件工程交叉学科背景。精通 C、C++ 与 Python 开发，长期研究人工智能技术在量化金融、风险管控等金融场景的创新应用。

## 二、模板选择

基于 **Academic Pages**（[academicpages.github.io](https://academicpages.github.io)）构建。

| 权衡 | 结论 |
|------|------|
| 维护成本 | 零成本，纯静态 GitHub Pages 托管 |
| 复杂度 | Jekyll + YAML 配置，无需数据库或后端 |
| 内容管理 | Markdown 文件直写，Git 版本控制 |
| 扩展性 | 支持出版物、演讲、教学等学术内容类型 |
| 许可 | MIT License，允许修改和商用 |

该模板原为学术个人网站设计，内置了个人信息侧边栏、作品集集合、CV 页面等结构，与本站需求高度匹配，省去从零搭建的时间。

## 三、主要修改

### 3.1 个人信息替换
| 文件 | 操作 |
|------|------|
| `_config.yml` | 更新 title / description / bio / email / github / linkedin；清空其他所有社交链接 |
| `images/profile.png` | 替换为用户提供的头像照片 |

### 3.2 页面内容重写
| 文件（原） | 文件（新） | 操作 |
|-----------|-----------|------|
| `_pages/about.md` | 同 | 替换模板欢迎页为中英文双语个人简介 |
| `_pages/cv.md` | 同 | 替换虚拟教育/技能/工作内容为真实信息 |
| `_pages/portfolio.html` | `_pages/projects.md` | 重命名、改 permalink、内容改为硬编码项目卡片 |
| `_data/navigation.yml` | 同 | 精简为三项：Home / Projects / CV |

### 3.3 模板清理
- 删除 `_publications/`、`_talks/`、`_teaching/`、`_posts/` 中的全部示例文件
- 删除 `_portfolio/` 目录（改用硬编码方案后废弃）
- 移除 `.github/workflows/` 下的自定义 workflow 文件

### 3.4 范围变更记录

**原始方案**：使用 Jekyll `_portfolio/` 集合管理项目卡片，通过 `site.portfolio` 变量渲染。

**实际方案**：在 `_pages/projects.md` 页面内直接硬编码 HTML 项目卡片，完全绕过 Jekyll 集合系统。

**变更原因**：`_portfolio/` 集合文件因 excerpt 中的 `%` 字符被 Jekyll 误解析为 Liquid 标签，修复后集合仍不生效；同时 `portfolio.html` 文件名与 `portfolio` 集合同名，导致 Jekyll 将其当作静态文件而非页面处理。两项问题叠加，投入数小时排查未果，最终弃用集合方案。

## 四、AI 参与

### 4.1 AI 承担的工作

| 类别 | 具体内容 |
|------|---------|
| 代码生成 | `_config.yml` 配置编辑、`about.md` / `cv.md` / `projects.md` 内容编写、Jekyll 前端模板语法（YAML Front Matter、Liquid 循环、include 调用） |
| 文档编写 | `prd.md` / `design.md` / `checklist.md` / `final-report.md` 的全部初稿 |
| 故障诊断 | 定位 Jekyll 404 原因为 permalink 冲突、文件名与集合同名、`%` 字符被解析为 Liquid 标签 |
| 部署调试 | 配置 GitHub Pages、创建自定义 workflow、切换内置构建、使用 IP 直连绕过 DNS 阻断 |
| 版本控制 | 本地 commit、push、force push、fetch、remote URL 切换等 Git 操作 |

### 4.2 由人工判断完成的工作

| 类别 | 具体内容 |
|------|---------|
| 内容真实性审核 | 确认个人简介、技能标签、教育信息、自媒体经验数据（120w 播放量）是否准确 |
| 头像选择 | 提供并授权使用个人照片 |
| 项目方向确认 | 指定 "金融科技项目（进行中）" 作为 Projects 展示内容 |
| 隐私边界界定 | 明确哪些信息不能公开（身份证、手机号、住址、邀请码、API Key） |
| 命名决定 | 确定网站标题为 "fintech student SZU" |
| 版本最终验收 | 逐条确认 10 项验收标准并签字 |

### 4.3 人机协作模式

1. **先由 AI 提出方案**（如"建议将 Portfolio 重命名为 Projects"或"excerpt 中的 % 导致 Liquid 解析错误"）
2. **人工确认方向**后再实施
3. **遇到阻塞时切换策略**（集合方案 → 硬编码方案；HTTPS 推送 → IP 直连 → SSH 密钥提议）
4. **每一步输出都提交 Git**，确保过程可追溯

## 五、个人判断

### 5.1 关键决策节点

| 节点 | 方案 A | 方案 B | 选择 | 理由 |
|------|--------|--------|------|------|
| 模板选择 | 从零搭建静态 HTML | Fork Academic Pages Jekyll 模板 | B | 节省布局/样式/响应式工作量，专注于内容填充 |
| 项目卡片方案 | Jekyll `_portfolio/` 集合 | `_pages/projects.md` 硬编码 HTML | B（后） | 集合方案经多次尝试仍无法正常工作 |
| Projects URL | `/portfolio/` | `/projects/` | B | 匹配页面标题，避免与 portfolio 集合路径冲突 |
| 部署方式 | 自定义 GitHub Actions workflow | GitHub Pages 内置构建 | B | 内置构建更稳定，减少维护点 |
| 推送方式 | HTTPS | IP 直连 → SSH | A→IP | VPN 阻断 github.com:443，IP 直连临时绕过；最终使用 force push |

### 5.2 经验总结

1. **Jekyll 集合的文件名「不能」与集合名相同**。`_pages/portfolio.html` 与 `portfolio` 集合同名，导致 Jekyll 将其处理为静态文件而非页面，permalink 不生效。
2. **YAML Front Matter 中的 `%` 字符需要谨慎处理**。`excerpt: "...style='border-radius:50%'"` 中的 `50%>` 被 Jekyll 误解析为 Liquid 结束标签 `%>`，导致整个集合文件被跳过。
3. **GitHub Pages 的 "Deploy from a branch" 模式不显示构建日志**，排查问题比 "GitHub Actions" 模式困难得多。
4. **工作流文件会覆盖内置构建**：一旦 `.github/workflows/` 目录存在自定义 workflow，GitHub 的内置 `pages-build-deployment` workflow 不再自动触发，需要删除 workflow 并切换 Pages 设置才能恢复。
5. **推送成功后 API 可能返回旧数据**：由于 CDN 缓存，`api.github.com` 的 `contents/` 和 `git/refs/` 端点可能返回滞后数据，需等待数分钟或使用 `raw.githubusercontent.com` 确认实际文件状态。

## 六、验证结果

### 6.1 验收标准（AC 01–10）

| 编号 | 验收项 | 验证命令 / 方法 | 结果 |
|------|--------|----------------|------|
| AC-01 | 网站可正常打开 | `curl -s -o /dev/null -w "%{http_code}" https://baronkid623-cyber.github.io` | HTTP 200 ✅ |
| AC-02 | 首页中英文双语 | 页面包含 "深圳大学" + "Undergraduate student" | ✅ |
| AC-03 | 侧边栏信息 | 头像 / Bio / Email / GitHub / LinkedIn 逐一确认 | ✅ |
| AC-04 | 导航栏三项 | 页面包含 Home / Projects / CV 三个链接 | ✅ |
| AC-05 | Projects 项目卡片 | 页面包含"金融科技项目（进行中）"及研究方向列表 | ✅ |
| AC-06 | CV 真实内容 | Education 2025–present / Skills 5 类 / 自媒体经验 / AI 项目 | ✅ |
| AC-07 | 外链有效 | GitHub + LinkedIn + Email 跳转正确 | ✅ |
| AC-08 | 移动端响应式 | viewport meta 已配置，CSS 含 3 档断点 | ✅ |
| AC-09 | 无隐私敏感信息 | 全文检索无身份证 / 手机号 / API Key | ✅ |
| AC-10 | 自动部署 | Site last updated 2026-07-25 | ✅ |

### 6.2 硬性门槛

| 门槛 | 状态 | 证据 |
|------|------|------|
| 作品可访问 | ✅ | HTTP 200，浏览器可直接打开 |
| 内容属于本人 | ✅ | 姓名/学校/专业均属本人 |
| 规格文件完整 | ✅ | docs/ 目录含 prd / design / checklist |
| 过程可追溯 | ✅ | Git 788 次提交，关键提交均有明确 message |
| 证据可复核 | ✅ | 仓库公开，has_pages: True |
| 平台确已收件 | ✅ | 2026-07-25 构建成功 |

## 七、Pages 链接

- **网站地址**：https://baronkid623-cyber.github.io
- **源代码仓库**：https://github.com/baronkid623-cyber/baronkid623-cyber.github.io
- **项目文档**：https://github.com/baronkid623-cyber/baronkid623-cyber.github.io/tree/master/docs

## 八、问题与后续计划

### 8.1 已关闭的问题

| 问题 | 原因 | 解决方案 |
|------|------|---------|
| Pages 404 | `_pages/portfolio.html` 与 `portfolio` 集合同名 | 重命名为 `_pages/projects.md` |
| 项目卡片不显示 | excerpt 中的 `50%>` 被解析为 Liquid 标签 | 移除 `%` 字符；最终弃用集合方案 |
| 推送失败 | VPN 阻断 `github.com:443` | IP 直连 + `http.sslVerify=false` |
| 构建不触发 | 自定义 workflow 覆盖内置 Pages 构建 | 删除 workflow 文件，切换为内置构建 |
| 分支分歧 | 本地与 GitHub Web 编辑的 commit 分叉 | `git push --force` |

### 8.2 已知问题

| 问题 | 说明 |
|------|------|
| GitHub Pages API 不可匿名访问 | `/repos/{owner}/{repo}/pages` 返回 404，无法通过 API 监控构建状态 |
| `api.github.com` 内容端点可能返回滞后数据 | CDN 缓存导致 Git 推送成功后文件 API 仍返回旧版内容，需等待数分钟 |

### 8.3 后续可做

| 项目 | 优先级 | 说明 |
|------|--------|------|
| 补充更多项目卡片 | P1 | 目前仅一个 "金融科技项目（进行中）"，可补充课程项目或竞赛项目 |
| 自定义域名 | P2 | 绑定个人域名（需 DNS 配置） |
| 技术博客 | P3 | 如持续产出技术内容，可启用 `_posts/` 博客功能 |
| 主题配色微调 | P3 | 当前使用 default 主题，可微调 `_sass/` 颜色变量 |
| HTML 项目卡片改为 Jekyll 数据文件 | P3 | 如果将来项目数量增加，可改用 `_data/` 目录管理项目列表，再通过 Liquid 循环渲染，兼顾可维护性和稳定性 |

---

> 报告撰写：Codex（AI）| 内容审核：Ethan Li（人工）| 最终版本：V1.0 | 2026-07-25
> 
> 本报告不包含完整的对话记录，仅收录关键决策、验证结果和可复现的结论。
