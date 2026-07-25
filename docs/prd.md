# 产品需求文档 — PRD

> 项目：个人网站 — Ethan Li | 版本：V3.0（终版） | 日期：2026-07-25

---

## 1. 项目背景

基于 Academic Pages（Jekyll）模板构建个人品牌展示网站，托管于 GitHub Pages。面向实习招聘者、同学、教师和项目伙伴，展示 FinTech 方向的学习轨迹与能力积累。

## 2. 目标访问者

| 访问者 | 首要寻找的信息 |
|--------|--------------|
| 实习招聘者 / HR | 技术栈（C/C++/Python/AI）、项目经验、GitHub 链接 |
| 同学 / 项目伙伴 | 研究方向、技能标签、合作可能性 |
| 教师 / 导师 | 学术兴趣、FinTech 方向深度 |
| 竞赛队友 | 项目经验、技术能力、联系方式 |

## 3. 定位

> 深圳大学金融科技专业本科生，具备金融、计算机、硬件工程交叉学科背景。精通 C、C++ 与 Python 开发，长期研究 AI 在金融中的应用。

## 4. 本期包含内容

| 模块 | 文件 | 状态 |
|------|------|------|
| 网站标题与描述 | _config.yml | ✅ |
| 首页中英文双语简介 | _pages/about.md | ✅ |
| 侧边栏头像 / Bio / 联系方式 | _config.yml，images/profile.png | ✅ |
| 导航栏 Home / Projects / CV | _data/navigation.yml | ✅ |
| 项目卡片（硬编码） | _pages/projects.md | ✅ |
| CV 教育 / 技能 / 项目 | _pages/cv.md | ✅ |
| 删除模板示例文件 | _publications/，_talks/，_teaching/，_posts/ 已清空 | ✅ |
| 文档 | docs/prd.md，docs/design.md，docs/checklist.md | ✅ |

## 5. 不做什么

自定义域名、访客统计、评论系统、多语言切换、复杂交互、博客。

## 6. 验收标准

| 编号 | 验收项 | 结果 |
|------|--------|------|
| AC-01 | 网站可正常打开 (HTTP 200) | ✅ |
| AC-02 | 首页中英文双语简介 | ✅ |
| AC-03 | 侧边栏头像 / Bio / 联系方式 | ✅ |
| AC-04 | 导航栏 Home / Projects / CV | ✅ |
| AC-05 | Projects 页面展示项目 | ✅ |
| AC-06 | CV 真实教育背景和技能 | ✅ |
| AC-07 | 所有外链有效 | ✅ |
| AC-08 | 手机端响应式 | ✅ |
| AC-09 | 无隐私敏感信息 | ✅ |
| AC-10 | push 后自动部署 | ✅ |

## 7. 隐私边界

**不公开**：身份证号、学生证号、住址、手机号、课程邀请码、API Key、未授权照片。

**可公开**：姓名 Ethan Li、深圳大学、金融科技、公开邮箱 baron.kid623@gmail.com、GitHub、LinkedIn、技能和项目经历。

## 8. 附录

- 网站：https://baronkid623-cyber.github.io
- 源代码：https://github.com/baronkid623-cyber/baronkid623-cyber.github.io
- 技术栈：Jekyll + Academic Pages + GitHub Pages
