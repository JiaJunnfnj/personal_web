# 个人简历单页 - 使用说明

本项目为**纯原生 HTML5 + CSS3 + JavaScript** 实现的单页简历，无任何前端框架与外部依赖。直接双击 `resume.html` 用浏览器打开即可使用。

---

## 如何替换个人信息

### 1. 个人简介

- **姓名**：在页面中找到 `id="intro-name"` 的标签，修改其中的文字。
- **职业/职位**：修改 `id="intro-job"` 的文本。
- **个人介绍**：修改 `id="intro-desc"` 内的段落内容。
- **技能标签**：在 `id="intro-skills"` 的 div 内增删或修改带有 `data-skill` 的 `span.skill-tag`，例如：
  ```html
  <span class="skill-tag" data-skill>你的技能名</span>
  ```
  点击标签可切换高亮效果。

### 2. 照片轮播

- 将每个轮播项里的 `<div class="placeholder">...</div>` **整体替换**为一张图片，例如：
  ```html
  <img src="https://你的图床或本地路径/photo1.jpg" alt="照片1">
  ```
- 支持至少 3 张图；若需更多张，复制一个 `.carousel-item` 块并相应增加底部圆点（或保持 3 张即可）。
- 轮播间隔在 JS 中的 `CAROUSEL_INTERVAL`（默认 3000 毫秒）可改；鼠标悬停时会暂停轮播。

### 3. 社交媒体 / 联系方式

- **GitHub**：把对应 `a.social-item` 的 `href` 改成你的 GitHub 主页地址。
- **知乎**：同上，改为你的知乎主页。
- **微信**：可保留 `href="#"` 或改为你的微信号展示页/二维码页面。
- **邮箱**：将 `href="mailto:your@email.com"` 中的 `your@email.com` 改为你的邮箱。
- 图标为内联 SVG（Base64），无需引入外部图标库；如需更换图标，可替换 `.social-icon` 的 `background-image` 或使用图片。

### 4. AI 交流模块（模拟）

- 此为**静态模拟**，无真实 AI 接口。用户发送的内容会显示在对话区，并自动回复一段**预设文案**。
- 修改预设回复：在 `resume.html` 的 `<script>` 中搜索 `MOCK_AI_REPLY`，修改其字符串即可。
- 欢迎语在 `#chat-messages` 内的第一条 `.chat-bubble.ai` 中修改。

---

## 文件说明

- **resume.html**：唯一需要的文件，内含全部 HTML、CSS、JS，无外部依赖。
- 部署时只需上传此文件到任意静态空间（如 GitHub Pages、Vercel、服务器）即可。

---

## 技术说明

- 布局：CSS3 Flex / Grid，响应式适配 PC、平板、手机。
- 交互：技能标签点击高亮、轮播自动/手动切换与悬停暂停、模拟对话发送与回车发送。
- 风格：浅色系（白底 + 深蓝文字），点缀色为蓝色，可在 `:root` 的 CSS 变量中调整颜色。

如有需要，可自行在页面中增加更多区块，并在顶部导航中增加对应锚点链接（`href="#区块id"`）。
