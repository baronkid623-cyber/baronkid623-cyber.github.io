# 产品需求文档 — PRD

> 项目：个人网站 — Ethan Li | 版本：V3.1 | 日期：2026-07-25

---

## 目标访问者是谁？他们最先寻找什么信息？

| 访问者 | 首要寻找的信息 | 在网站的哪里找到 |
|--------|--------------|----------------|
| 实习招聘者 / HR | 技术栈（C/C++/Python/AI）、项目经历、GitHub 链接 | 首页 → 侧边栏 → CV → Projects |
| 同学 / 项目伙伴 | 当前研究方向、技能标签、合作可能性 | 首页（中英文简介）→ 侧边栏 Bio |
| 教师 / 导师 | 学术兴趣、FinTech 方向深度、课程项目 | CV（教育/技能）→ About 首页 |
| 竞赛队友 | 项目方向、技术能力、联系方式 | Projects → 侧边栏（邮箱/GitHub） |

## 希望访问者看完后记住什么？

> 深圳大学金融科技专业本科生，金融/计算机/硬件交叉背景；精通 C/C++/Python，研究 AI 在金融中的应用；有实际项目经验（金融科技项目进行中）；联系方式一目了然。

## 本期必须包含哪些内容？

| 模块 | 位置 | 具体内容 |
|------|------|---------|
| 个人定位 | 首页 `_pages/about.md` | 中英文双语：一句话定位 + 技能标签 + Quick Links |
| 侧边栏身份 | `_config.yml` + `images/profile.png` | 头像（用户提供）、姓名 Ethan Li、Bio、所在地 Shenzhen、学校 Shenzhen University |
| 联系方式 | 侧边栏 + 首页底部 | 邮箱 baron.kid623@gmail.com、GitHub baronkid623-cyber、LinkedIn baronkid623 |
| 导航栏 | `_data/navigation.yml` | 三个入口：Home / Projects / CV |
| 项目展示 | `_pages/projects.md`（硬编码 HTML） | 金融科技项目（进行中）：AI驱动量化策略、智能风控系统、金融NLP 三个研究方向，标注 🚧 进行中 |
| 在线简历 | `_pages/cv.md` | Education: B.S. FinTech @ SZU 2025–present、Skills 分类列表、Work experience（自媒体120w播放量）、Projects（AI大模型金融科技项目） |
| 项目文档 | `docs/` 目录 | prd.md、design.md、checklist.md |

**范围变更记录**：Projects 最初使用 Jekyll `_portfolio/` 集合实现，因 Liquid 解析 `%` 字符失败且 collection 配置反复异常，最终改为 `_pages/projects.md` 内直接硬编码 HTML 卡片。

## 本期明确不做什么？

| 项目 | 原因 |
|------|------|
| 自定义域名 | `*.github.io` 足够；后续可加 |
| 访客统计 / 分析 | 保护访客隐私，不嵌入第三方脚本 |
| 评论系统 | 个人站点无需评论区 |
| 多语言切换 | 中英双语已直接展示在同一页面 |
| 复杂交互 / 动画 | 保持简洁学术风 |
| 电商 / 支付 | 非商业站点 |
| 博客系统 | 无持续输出内容时不做 |
| 联系方式表单 | 直接展示邮箱即可，不收集数据 |
| Jekyll `_portfolio/` 集合 | 改为硬编码方案 |

## 怎样判断网站完成？

| 编号 | 验收项 | 验证方法 | 预期结果 |
|------|--------|---------|---------|
| AC-01 | 网站可正常打开 | 浏览器访问 `baronkid623-cyber.github.io` | 返回 HTTP 200，非 404 |
| AC-02 | 首页中英文双语简介 | 肉眼核对首页文字 | 同时出现中文"深圳大学金融科技"和英文"Undergraduate student" |
| AC-03 | 侧边栏信息正确 | 肉眼核对侧边栏 | 头像显示 + Bio 含 FinTech/C++/Python + 邮箱/GitHub/LinkedIn 图标 |
| AC-04 | 导航栏三项 | 点击 Home / Projects / CV | 三个链接均可跳转且页面标题匹配 |
| AC-05 | Projects 页面有内容 | 访问 `/projects/` | 页面显示"金融科技项目（进行中）"及研究方向列表 |
| AC-06 | CV 真实内容 | 访问 `/cv/` | 显示 2025–present 教育 + 技能列表 + 自媒体经验 |
| AC-07 | 外链有效 | 点击侧边栏 GitHub 和 LinkedIn | 跳转到对应的公开个人页 |
| AC-08 | 手机端可读 | Chrome DevTools 切换到 iPhone 12 尺寸 | 导航折叠为汉堡菜单，内容无溢出 |
| AC-09 | 无隐私敏感信息 | 全文检索所有页面源码 | 无身份证号、手机号、住址、API Key |
| AC-10 | 自动部署 | 在 GitHub 上推送任意 commit | GitHub Actions 完成部署，网站更新 |

## 哪些信息不能公开？

| 类别 | 说明 |
|------|------|
| 身份证号 / 学生证号 | 任何证件号码不出现 |
| 家庭 / 宿舍地址 | 任何物理地址不出现 |
| 私人手机号 | 不公开手机号码 |
| 课程邀请码 | 不公开任何课程代码或邀请链接 |
| API Key / Token / 密码 | 任何密钥或认证凭证不出现 |
| 未授权照片 | 仅使用本人提供的头像照片 |

**可公开**：姓名 Ethan Li、学校（深圳大学）、专业（金融科技）、公开邮箱 baron.kid623@gmail.com、GitHub（baronkid623-cyber）、LinkedIn（baronkid623）、技术能力描述（C/C++/Python/AI）、项目经历描述。

## 附录

- 网站：https://baronkid623-cyber.github.io
- 源代码：https://github.com/baronkid623-cyber/baronkid623-cyber.github.io
- 技术栈：Jekyll + Academic Pages（Minimal Mistakes 衍生）+ GitHub Pages
- 框架版本：Jekyll 4.x，Ruby 3.2
- 部署方式：Deploy from a branch（master, /）
