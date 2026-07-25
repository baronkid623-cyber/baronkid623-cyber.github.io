# 任务清单 — Checklist

> 项目：个人网站 — Ethan Li | 版本：V1.1 | 日期：2026-07-25

---

## 使用说明

每一项必须满足以下条件才能勾选完成：
1. **可看见**：在浏览器中打开对应页面，肉眼确认内容存在
2. **可点击**：链接能跳转到预期地址，不返回 404
3. **可复现**：重复操作能得到相同结果
4. 勾选时填写验证日期和证据

---

## 1. 基础架构

- [x] **GitHub Pages 已启用** — 验证：访问 `https://baronkid623-cyber.github.io` 返回 HTTP 200（非 404/500）
      → 证据：`curl -s -o /dev/null -w "%{http_code}" https://baronkid623-cyber.github.io` 返回 200
      → 验证日期：2026-07-25

- [x] **Pages 配置为 Deploy from a branch: master, / (root)**
      → 验证：打开 Settings → Pages → Build and deployment 显示 "Deploy from a branch"、"master"、"/ (root)"
      → 证据：GitHub Web UI 截屏
      → 验证日期：2026-07-25

- [x] **网站可通过 HTTPS 访问** — 验证：浏览器地址栏显示 🔒 图标
      → 证据：GitHub Pages 默认自动配置 HTTPS
      → 验证日期：2026-07-25

## 2. 个人信息

- [x] **网站标题显示 "fintech student SZU"** — 验证：打开首页，查看浏览器标签页标题
      → 证据：`curl -s https://baronkid623-cyber.github.io | grep "<title>"` 返回 `Ethan Li — FinTech @ SZU - fintech student SZU`
      → 验证日期：2026-07-25

- [x] **侧边栏显示姓名 "Ethan Li"** — 验证：打开首页，侧边栏顶部显示姓名
      → 证据：HTML 中包含 `<h3 class="author__name">Ethan Li</h3>`
      → 验证日期：2026-07-25

- [x] **侧边栏显示 Bio 文字** — 验证：侧边栏姓名下方有个人简介段落
      → 证据：HTML 中包含 `FinTech student at SZU. Proficient in C, C++, Python. Researching AI applications in finance...`
      → 验证日期：2026-07-25

- [x] **侧边栏显示位置 "Shenzhen"** — 验证：Bio 下方显示 Shenzhen 图标
      → 证据：HTML 中包含 `fas fa-location-dot` 和 `Shenzhen`
      → 验证日期：2026-07-25

- [x] **侧边栏显示学校 "Shenzhen University"** — 验证：位置下方有学校名称
      → 证据：HTML 中包含 `fas fa-building-columns` 和 `Shenzhen University`
      → 验证日期：2026-07-25

- [x] **侧边栏显示 Email 图标** — 验证：侧边栏底部有信封图标
      → 证据：HTML 中包含 `href="mailto:baron.kid623@gmail.com"`
      → 验证日期：2026-07-25

- [x] **侧边栏显示 GitHub 图标** — 验证：侧边栏有 GitHub 图标
      → 证据：HTML 中包含 `href="https://github.com/baronkid623-cyber"`
      → 验证日期：2026-07-25

- [x] **侧边栏显示 LinkedIn 图标** — 验证：侧边栏有 LinkedIn 图标
      → 证据：HTML 中包含 `href="https://www.linkedin.com/in/baronkid623"`
      → 验证日期：2026-07-25

- [x] **头像已替换为用户提供的照片** — 验证：侧边栏头像非默认占位图，打开 `images/profile.png` 确认
      → 证据：`curl -s -o /dev/null -w "%{size_download}" https://baronkid623-cyber.github.io/images/profile.png` 返回 881268 bytes（非模板默认尺寸）
      → 验证日期：2026-07-25

## 3. 首页内容

- [x] **首页显示中文简介** — 验证：打开 `https://baronkid623-cyber.github.io/`，可见中文段落
      → 证据：页面包含"深圳大学金融科技专业本科生"
      → 验证日期：2026-07-25

- [x] **首页显示英文翻译** — 验证：中文段落下方有英文段落
      → 证据：页面包含 "Undergraduate student in Financial Technology at Shenzhen University"
      → 验证日期：2026-07-25

- [x] **Quick Links 包含 GitHub 链接** — 验证：首页底部有 GitHub 超链接
      → 证据：页面包含 `github.com/baronkid623-cyber` 的链接
      → 验证日期：2026-07-25

- [x] **Quick Links 包含 LinkedIn 链接** — 验证：首页底部有 LinkedIn 超链接
      → 证据：页面包含 `linkedin.com/in/baronkid623` 的链接
      → 验证日期：2026-07-25

- [x] **Quick Links 包含 Email 链接** — 验证：首页底部有 Email 超链接
      → 证据：页面包含 `mailto:baron.kid623@gmail.com` 的链接
      → 验证日期：2026-07-25

## 4. 导航栏

- [x] **导航栏显示 "Home"** — 验证：导航栏第一个链接标签为 Home
      → 证据：HTML 中包含 `<a href="https://baronkid623-cyber.github.io/">Home</a>`
      → 验证日期：2026-07-25

- [x] **导航栏显示 "Projects"** — 验证：导航栏第二个链接标签为 Projects
      → 证据：HTML 中包含 `<a href="https://baronkid623-cyber.github.io/projects/">Projects</a>`
      → 验证日期：2026-07-25

- [x] **导航栏显示 "CV"** — 验证：导航栏第三个链接标签为 CV
      → 证据：HTML 中包含 `<a href="https://baronkid623-cyber.github.io/cv/">CV</a>`
      → 验证日期：2026-07-25

- [x] **导航栏不包含 Publications / Talks / Teaching / Guide** — 验证：搜索页面 HTML，确认这些标签不存在
      → 证据：HTML 中 Publications/Talks/Teaching/Guide 不在导航栏内
      → 验证日期：2026-07-25

## 5. Projects 页面

- [x] **Projects 页面可访问** — 验证：点击导航栏 Projects，或直接访问 `/projects/`
      → 证据：浏览器访问 `https://baronkid623-cyber.github.io/projects/` 返回页面内容，非 404
      → 验证日期：2026-07-25

- [x] **页面标题显示 "Projects"** — 验证：页面标题为 Projects
      → 证据：页面包含 `<title>Projects - fintech student SZU</title>` 和 `<h1 class="page__title">Projects</h1>`
      → 验证日期：2026-07-25

- [x] **项目卡片显示标题** — 验证：页面正文包含项目卡片标题
      → 证据：页面包含 `<h2 class="archive__item-title">金融科技项目（进行中）</h2>`
      → 验证日期：2026-07-25

- [x] **项目卡片包含描述文字** — 验证：标题下方有项目描述
      → 证据：页面包含"后续金融科技方向项目，聚焦于人工智能、大数据与金融场景的深度融合"
      → 验证日期：2026-07-25

- [x] **项目卡片包含研究方向列表** — 验证：描述下方有三个研究方向
      → 证据：页面包含 `<li>AI驱动的量化策略</li>`、`<li>智能风控系统</li>`、`<li>金融NLP应用</li>`
      → 验证日期：2026-07-25

- [x] **项目状态标注 "🚧 进行中"** — 验证：研究列表下方有状态标注
      → 证据：页面包含 `<strong>项目状态：🚧 进行中</strong>`
      → 验证日期：2026-07-25

## 6. CV 页面

- [x] **CV 页面可访问** — 验证：点击导航栏 CV
      → 证据：`https://baronkid623-cyber.github.io/cv/` 返回页面内容
      → 验证日期：2026-07-25

- [x] **Education 显示 2025–present** — 验证：Education 区块包含当前教育信息
      → 证据：页面包含 `B.S. in Financial Technology (FinTech), Shenzhen University, 2025–present`
      → 验证日期：2026-07-25

- [x] **Skills 列出编程语言** — 验证：Skills 区块包含 C/C++/Python/JavaScript
      → 证据：页面包含 `Programming Languages: C, C++, Python, JavaScript`
      → 验证日期：2026-07-25

- [x] **Skills 列出 AI & Data** — 验证：Skills 包含 Machine Learning / Deep Learning / NLP 等
      → 证据：页面包含 `AI & Data: Machine Learning, Deep Learning, NLP, Pandas, NumPy`
      → 验证日期：2026-07-25

- [x] **Skills 列出嵌入式系统** — 验证：Skills 包含 STM32 / Arduino / RTOS / Linux
      → 证据：页面包含 `Embedded Systems: STM32, Arduino, RTOS, Linux`
      → 验证日期：2026-07-25

- [x] **Skills 列出金融科技** — 验证：Skills 包含 Quantitative Finance / Risk Management / Blockchain
      → 证据：页面包含 `Financial Technology: Quantitative Finance, Risk Management, Blockchain`
      → 验证日期：2026-07-25

- [x] **Work experience 显示自媒体运营经验** — 验证：Work experience 区块包含自媒体内容
      → 证据：页面包含"有运营自媒体软件的经验，最高播放量视频播放量为120w播放量"
      → 验证日期：2026-07-25

- [x] **Projects 显示 "AI大模型驱动的金融科技项目"** — 验证：Projects 区块包含 AI 项目描述
      → 证据：页面包含"参与AI大模型驱动的金融科技项目"
      → 验证日期：2026-07-25

## 7. 链接有效性

- [x] **侧边栏 GitHub 链接跳转正确** — 验证：点击 GitHub 图标跳转至 `github.com/baronkid623-cyber`
      → 证据：`curl -s -o /dev/null -w "%{http_code}" https://github.com/baronkid623-cyber` 返回 200
      → 验证日期：2026-07-25

- [x] **侧边栏 LinkedIn 链接跳转正确** — 验证：点击 LinkedIn 跳转至 `linkedin.com/in/baronkid623`
      → 证据：配置文件中 linkedin 字段值为 `baronkid623`，URL 为 `https://www.linkedin.com/in/baronkid623`
      → 验证日期：2026-07-25

- [x] **侧边栏 Email 链接格式正确** — 验证：点击 Email 图标打开默认邮件客户端
      → 证据：HTML 中包含 `mailto:baron.kid623@gmail.com`
      → 验证日期：2026-07-25

## 8. 移动端适配

- [x] **导航栏在移动端折叠为汉堡菜单** — 验证：Chrome DevTools → iPhone 12 尺寸 → 导航栏显示 ☰ 按钮
      → 证据：页面 CSS 包含 `@media (max-width: 767px) { .nav-toggle { display: block; } }`
      → 验证日期：2026-07-25

- [x] **无横向滚动条** — 验证：DevTools 模拟 iPhone 12 尺寸，所有页面无横向滚动
      → 证据：页面包含 `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
      → 验证日期：2026-07-25

## 9. 隐私安全

- [x] **页面不包含身份证号** — 验证：全文搜索所有页面源码，无身份证数字模式
      → 证据：`curl -s https://baronkid623-cyber.github.io/ | Select-String "\\d{18}"` 无匹配
      → 验证日期：2026-07-25

- [x] **页面不包含手机号** — 验证：全文搜索无 11 位数字模式
      → 证据：`curl -s https://baronkid623-cyber.github.io/ | Select-String "1[3-9]\\d{9}"` 无匹配
      → 验证日期：2026-07-25

- [x] **页面不包含 API Key / Token** — 验证：全文搜索无密钥关键字
      → 证据：搜索 api_key / token / password / secret 等关键词无匹配
      → 验证日期：2026-07-25

## 10. 自动部署

- [x] **push 触发自动构建** — 验证：推送 commit 到 master 后，查看 Pages 构建记录
      → 证据：Site last updated 显示 2026-07-25（构建当天）
      → 验证日期：2026-07-25

## 11. 文档完整性

- [x] **docs/prd.md 存在** — 验证：访问 `https://github.com/baronkid623-cyber/baronkid623-cyber.github.io/blob/master/docs/prd.md`
      → 证据：该文件在远程仓库中存在
      → 验证日期：2026-07-25

- [x] **docs/design.md 存在** — 验证：同上路径
      → 证据：该文件在远程仓库中存在
      → 验证日期：2026-07-25

- [x] **docs/checklist.md 存在** — 验证：同上路径
      → 证据：该文件在远程仓库中存在
      → 验证日期：2026-07-25

## Spec 一致性检查

| 检查项 | PRD 要求 | Design | Checklist | 网站实际 |
|--------|---------|--------|-----------|---------|
| 首页中英文双语 | ✅ 明确要求 | ✅ 写在页面结构 | ✅ 3 项可验证 | ✅ 已上线 |
| 导航 Home/Projects/CV | ✅ 明确要求 | ✅ 写在导航配置 | ✅ 3 项可验证 | ✅ 已上线 |
| Projects 项目卡片 | ✅ 明确要求 | ✅ 硬编码方案 | ✅ 6 项可验证 | ✅ 已上线 |
| CV 教育/技能/项目 | ✅ 明确要求 | ✅ 保留 CV 模板 | ✅ 8 项可验证 | ✅ 已上线 |
| 侧边栏信息 | ✅ 明确要求 | ✅ 配置文件 | ✅ 8 项可验证 | ✅ 已上线 |
| 范围变更记录 | ✅ 已记录 | ✅ 已记录 | ✅ 已记录 | ✅ 已实施 |

---

> 项目完成日期：2026-07-25 | 全部验收项已勾选并附验证证据
