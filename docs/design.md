# 设计文档 — Design Doc

> 项目：个人网站 — Ethan Li | 版本：V1.1 | 日期：2026-07-25

---

## 页面区块与浏览顺序

访问者进入网站后的典型浏览路径：

```
入口 → Home（首页）
       │
       ├── 阅读中英文简介
       ├── 查看侧边栏（头像 / Bio / 联系方式）
       │
       ├── 点击 Projects → 浏览项目卡片
       │     └── 查看研究方向列表
       │
       ├── 点击 CV → 浏览教育 / 技能 / 项目经历
       │
       └── 点击侧边栏 GitHub / LinkedIn → 跳转外部链接
```

每个页面从上到下的区块顺序：

**Home（/）**
1. 顶部导航栏
2. Hero 区（首页标题 + 中英文简介正文）
3. 侧边栏（头像 / 姓名 / Bio / 位置 / 学校 / Email / GitHub / LinkedIn）
4. Quick Links 区
5. 页脚（版权 + 构建日期）

**Projects（/projects/）**
1. 顶部导航栏
2. 侧边栏（同上）
3. 页面标题 "Projects"
4. 项目卡片（标题 + 正文内容 "金融科技项目（进行中）" + 研究方向列表 + 状态标注）
5. 页脚

**CV（/cv/）**
1. 顶部导航栏
2. 侧边栏（同上）
3. 页面标题 "CV"
4. Education / Skills / Work experience / Projects 四个区块
5. 页脚

## 颜色、字体与整体风格

### 色彩系统

| 用途 | 色值 | 应用位置 |
|------|------|---------|
| 主色 | `#1A3C6E`（深蓝） | 标题、强调色、按钮、链接 |
| 辅色 | `#2D7D9A`（湖蓝） | 链接 hover 状态 |
| 背景色 | `#F5F7FA`（浅灰） | 页面整体底色 |
| 卡片背景 | `#FFFFFF`（白） | 内容区块 |
| 正文色 | `#333333`（深灰） | 正文文本 |
| 次要文字 | `#666666`（中灰） | 副标题、辅助说明 |
| 边框 | `#E0E4E8`（浅灰） | 卡片边框、分割线 |

### 字体

| 场景 | 字体栈 |
|------|--------|
| 中文正文 | Microsoft YaHei, PingFang SC, Noto Sans SC, system-ui |
| 英文正文 | system-ui, -apple-system, sans-serif |
| 代码 | Consolas, Cascadia Code, monospace |

### 整体风格

学术感、简约、扁平化。无渐变背景、无装饰性插图、无动画动效。信息优先，留白充足。

## 桌面端和移动端要求

| 特性 | 桌面端 ≥ 1024px | 移动端 ≤ 767px |
|------|----------------|---------------|
| 导航栏 | 水平排列 Home / Projects / CV | 折叠为汉堡菜单（☰） |
| 侧边栏 | 固定在左侧 | 移至正文上方 |
| 首页排版 | 侧边栏 + 正文并排 | 单列纵向堆叠 |
| 字号 | 16px 正文 / 28px 章节标题 | 14px 正文 / 22px 章节标题 |
| 页面内边距 | 左右 10% | 左右 1rem |
| 平板端 768–1023px | 侧边栏缩短，间距缩减 | — |

验证方法：Chrome DevTools → 设备模拟 → iPhone 12 → 检查无横向滚动条、无内容重叠。

## 关键文件分别负责什么

| 文件 | 职责 | 产出的效果 |
|------|------|-----------|
| `_config.yml` | 站点全局配置：标题、描述、作者信息、社交链接、插件、集合等 | 侧边栏头像/姓名/Bio/邮箱/GitHub/LinkedIn、页面 `<title>`、SEO meta |
| `_pages/about.md` | 首页（permalink: /）内容 | 中英文双语简介 + Quick Links |
| `_pages/projects.md` | Projects 页面内容（硬编码 HTML） | 项目卡片展示：标题 + 描述 + 研究方向列表 |
| `_pages/cv.md` | CV 页面内容 | 教育/技能/工作经验/项目经历四个区块 |
| `_data/navigation.yml` | 顶部导航栏条目 | 导航栏显示 Home / Projects / CV |
| `images/profile.png` | 侧边栏头像图片 | 头像显示在侧边栏顶部 |
| `assets/css/main.scss` | 全局样式（模板自带，未修改） | 颜色、字体、布局、响应式 |
| `_layouts/` | 页面模板（模板自带，未修改） | 页面骨架、侧边栏、导航、页脚 |
| `_includes/` | 组件片段（模板自带，未修改） | 作者信息卡片、社交图标、页头等 |
| `docs/` 目录 | 项目文档（新增） | prd.md / design.md / checklist.md |
| `Gemfile` | Ruby 依赖声明（模板自带，未修改） | 构建时安装 Jekyll 及相关插件 |

## 保留模板的哪些部分，修改哪些部分

### 保留（模板原有，未修改）

| 部分 | 原因 |
|------|------|
| `_layouts/` 全部文件 | Academic Pages 的页面骨架和布局 |
| `_includes/` 全部文件 | 侧边栏组件、SEO 组件、页脚等 |
| `assets/css/main.scss` + `_sass/` | 全局样式体系 |
| `assets/js/` | 导航交互、主题切换等 JavaScript |
| `Gemfile` + `_config.yml` 中的插件声明 | 构建依赖和 Jekyll 配置 |
| `_config.yml` 中的 collections 配置 | 保留 teaching / publications / portfolio / talks 集合定义（即使 portfolio 当前未使用） |

### 修改或替换

| 文件 | 修改内容 |
|------|---------|
| `_config.yml` | title（→"fintech student SZU"）、description、author.bio、author.email、author.github、author.linkedin；清空其他所有社交链接 |
| `_pages/about.md` | 替换全部内容：中英文双语简介 + Quick Links |
| `_pages/cv.md` | 替换 Education / Skills / Work experience / Projects 为真实内容 |
| `_pages/portfolio.html` | 重命名为 `projects.md`，permalink 改为 `/projects/`，内容改为硬编码 HTML 项目卡片 |
| `_data/navigation.yml` | 只保留三项：Home（`/`）、Projects（`/projects/`）、CV（`/cv/`） |
| `images/profile.png` | 替换为用户提供的头像照片 |

### 已删除

| 路径 | 原因 |
|------|------|
| `_portfolio/competition-platform.md` | 改用硬编码方案后不再需要 |
| `_portfolio/fintech-project-wip.md` | 改用硬编码方案后不再需要 |
| `_publications/*.md` | 模板示例文件，无真实内容 |
| `_talks/*.md` | 同上 |
| `_teaching/*.md` | 同上 |
| `_posts/*.md` | 同上 |
| `.github/workflows/` 自定义 workflow | 改用 GitHub Pages 内置构建 |

## 图片和外部素材的来源与许可

| 图片 | 来源 | 许可 |
|------|------|------|
| `images/profile.png`（头像） | 用户本人提供 | 用户本人授权公开使用 |
| `images/favicon.ico` / `.png` / `.svg` | Academic Pages 模板自带 | MIT License（模板附带） |
| `images/apple-touch-icon-*` | Academic Pages 模板自带 | MIT License |
| `assets/webfonts/fa-*.ttf/.woff2` | Font Awesome 免费版 | SIL OFL 1.1（Font Awesome Free License） |
| 主题页面截图（`images/themes/`） | Academic Pages 模板自带 | MIT License |

**不加载任何外部资源**。所有 CSS、JS、字体和图标均从站点自身 CDN（GitHub Pages）加载，不请求第三方域名。唯一的例外是 MathJax（从 `cdn.jsdelivr.net` 加载），但仅限于页面包含数学公式时，当前网站未使用该功能。

## 关键决策记录

| 决策 | 替代方案 | 选择原因 |
|------|---------|---------|
| 项目卡片硬编码而非 Jekyll collection | `_portfolio/` 集合文件 | collection 因 Liquid 解析 `%` 字符失败，修复后集合仍不生效，最终弃用 |
| portfolio.html → projects.md | 保持原文件名 | 文件名与 `portfolio` 集合重名，Jekyll 将其当作静态文件而非页面 |
| permalink /projects/ | 保持 /portfolio/ | 匹配页面标题 Projects，且避免与集合路径混淆 |
| force push 覆盖远程 | 正常 push | 本地与 GitHub Web 编辑的 commit 分歧，网络不稳定无法 pull 后合并 |
| IP 直连 + SSL 禁用 | 正常 HTTPS | VPN 阻断 `github.com:443`，IP 地址直连绕过 DNS 解析失败 |
| 部署方式：内置构建 | 自定义 GitHub Actions workflow | 内置构建更稳定，无需维护 workflow |
