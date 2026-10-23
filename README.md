# AI-Chat-Client
<div align="center">

# 💬 AI Chat Client

**一个单文件、纯前端、开箱即用的 AI 对话客户端**

兼容 OpenAI 格式接口 · 支持流式输出 · 多模态图片 · 移动端适配

[🌐 在线体验](https://ai-ol.pages.dev) · [功能特性](#-功能特性) · [快速开始](#-快速开始) · [使用说明](#-使用说明) · [常见问题](#-常见问题) · [贡献指南](#-贡献指南)

[![HTML](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/zh-CN/docs/Web/HTML)
[![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](./LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](./CONTRIBUTING.md)
[![Cloudflare Pages](https://img.shields.io/badge/Deployed_on-Cloudflare_Pages-F38020?logo=cloudflare&logoColor=white)](https://ai-ol.pages.dev)

</div>

---

## 🌐 在线体验

无需安装，打开即用：

👉 **https://ai-ol.pages.dev**

> 在线版已部署在 Cloudflare Pages，支持 HTTPS，可避免本地 `file://` 打开时的 CORS 限制。

---

## ✨ 项目简介

**AI Chat Client** 是一个**无需构建、无需后端、单文件部署**的 AI 对话网页客户端。

它兼容所有遵循 OpenAI 接口规范的 API（如 DeepSeek、OpenAI、Moonshot、通义千问、本地 Ollama、One API 等），只需填入接口地址和 Key 即可开始对话。

> 所有配置和聊天记录保存在浏览器本地（`localStorage`），**不会上传到任何第三方服务器**。

---

## 🚀 功能特性

| 分类 | 功能 | 说明 |
| --- | --- | --- |
| 💬 对话 | 流式输出 | 打字机效果逐字显示，支持中途停止生成 |
| 🖼️ 多模态 | 图片上传 | 支持 jpg/png/gif/webp，大图自动压缩为 JPEG |
| 🔌 兼容性 | OpenAI 格式 | 任意兼容 `/v1/chat/completions` 的服务均可使用 |
| 🧠 模型管理 | 一键获取列表 | 通过 `/v1/models` 拉取模型，也支持手动添加模型 ID |
| ⚙️ 参数控制 | 精细调节 | `temperature` / `top_p` / `max_tokens` / 系统提示词 |
| 📊 诊断 | 延迟测试 | 一键测试接口连通性和响应耗时 |
| 💾 持久化 | 本地存储 | 配置、对话历史保存在浏览器，刷新不丢失 |
| 📱 响应式 | 移动端适配 | 手机 / 平板 / 桌面自适应布局 |
| 🎨 界面 | 现代 UI | Tailwind CSS + 渐变动效 + 流畅过渡动画 |
| 🔒 访问控制 | 滑块验证 | 可选的滑动验证码，防止误触/爬虫 |
| 🇨🇳 中文友好 | 输入法兼容 | 中文输入法组合期间回车不误发 |

---

## 📸 界面预览

> 📌 建议在 `docs/` 目录放入截图，并替换下方占位路径。
>
> 在线预览：https://ai-ol.pages.dev

| 桌面端 | 移动端 |
| :---: | :---: |
| ![desktop](./docs/preview-desktop.png) | ![mobile](./docs/preview-mobile.png) |

---

## 🏁 快速开始

### 方式一：直接在线使用（推荐）

打开 **https://ai-ol.pages.dev**，填写接口地址和 API Key 即可开始对话。

### 方式二：本地直接打开

```bash
git clone https://github.com/your-username/ai-chat-client.git
cd ai-chat-client
```

双击打开 `index.html` 即可使用。

> ⚠️ **注意**：本地以 `file://` 协议打开时，浏览器会触发 **CORS 跨域限制**，调用远程 API 可能失败。推荐使用在线版或本地静态服务器。

### 方式三：本地静态服务器

```bash
# Python 3
python -m http.server 8080

# 或 Node.js（需先安装 serve）
npx serve .
```

然后访问 <http://localhost:8080>。

### 方式四：部署到 Cloudflare Pages

本项目已部署示例：**https://ai-ol.pages.dev**

自行部署步骤：

1. Fork 本仓库
2. 登录 [Cloudflare Pages](https://pages.cloudflare.com/)
3. 点击 **Create a project → Connect to Git**
4. 选择你的仓库
5. 构建配置：
   - **Framework preset**：`None`
   - **Build command**：留空
   - **Build output directory**：`/`
6. 点击 **Save and Deploy**
7. 部署完成后访问 `https://<项目名>.pages.dev`

也可以部署到 **GitHub Pages / Vercel / Netlify** 等任意静态托管平台。

---

## ⚙️ 使用说明

### 1. 填写接口配置

点击左上角 ☰ 打开侧边栏，填写：

| 字段 | 示例 | 说明 |
| --- | --- | --- |
| **接口地址** | `https://api.deepseek.com/v1` | OpenAI 格式的 Base URL |
| **API Key** | `sk-xxxxxxxx` | 各平台申请的密钥 |
| **模型** | `deepseek-chat` | 点击 🔄 自动获取，或手动添加 |

> 💡 接口地址需**包含**版本路径（如 `/v1`），程序会自动拼接 `/chat/completions` 和 `/models`。

### 2. 保存并开始对话

点击 **「保存配置」**，回到输入框即可发送消息。

### 3. 上传图片（可选）

- 点击 🖼️ 按钮选择图片，支持多张
- **必须使用 vision 多模态模型**（如 `gpt-4o`、`qwen-vl-max`、`deepseek-v4-flash-vision-exp` 等）
- 图片会自动压缩到最长边 1280px，减少 Token 消耗

---

## 🌐 兼容的 API 服务商

本客户端兼容所有遵循 **OpenAI 接口规范** 的服务：

| 服务商 | Base URL 示例 | 备注 |
| --- | --- | --- |
| DeepSeek | `https://api.deepseek.com/v1` | 官方推荐 |
| OpenAI | `https://api.openai.com/v1` | 需科学上网 |
| Moonshot | `https://api.moonshot.cn/v1` | 国内可用 |
| 通义千问 | `https://dashscope.aliyuncs.com/compatible-mode/v1` | 阿里云 |
| 智谱 GLM | `https://open.bigmodel.cn/api/paas/v4` | 国内可用 |
| Ollama | `http://localhost:11434/v1` | 本地模型 |
| One API | 你的部署地址 `/v1` | 网关聚合 |
| SiliconFlow | `https://api.siliconflow.cn/v1` | 国内可用 |

> 🚨 使用时如遇 **CORS 跨域错误**，请确认服务商是否允许浏览器直连。多数官方 API 已支持跨域；若不允许，可通过反向代理或自建网关解决。

---

## 🧩 项目结构

```
ai-chat-client/
├── index.html        # 单文件应用（原名 ai-ol.html）
├── README.md         # 本文档
├── LICENSE           # MIT 许可证
├── .gitignore        # Git 忽略规则
└── docs/             # 文档与截图（可选）
    ├── preview-desktop.png
    └── preview-mobile.png
```

整个应用仅有 **一个 HTML 文件**，无需 npm、无需构建，开箱即用。

---

## 🛠️ 技术栈

- **HTML5 + 原生 JavaScript** —— 零依赖
- **Tailwind CSS** —— 通过 CDN 引入，快速构建现代 UI
- **Font Awesome 4.7** —— 图标库
- **Fetch API + ReadableStream** —— 处理流式响应
- **Canvas API** —— 客户端图片压缩
- **localStorage** —— 配置与历史持久化
- **Cloudflare Pages** —— 静态站点托管

---

## ❓ 常见问题

<details>
<summary><b>1. 提示 "Failed to fetch" 或跨域错误？</b></summary>

浏览器控制台报 **CORS** 错误，说明接口禁止浏览器直连。解决方案：

- ✅ 使用在线版 **https://ai-ol.pages.dev**（HTTPS 环境）
- ✅ 部署到 **HTTPS** 环境（Cloudflare Pages / Vercel 等）
- ✅ 确认 API 服务商支持 CORS
- ✅ 使用 **One API** 等网关中转
- ✅ 自建反向代理（Nginx / Cloudflare Worker）

</details>

<details>
<summary><b>2. 上传图片后模型报错 / 无响应？</b></summary>

**图片输入必须使用 vision 多模态模型**，普通文本模型不支持 `image_url` 格式。

推荐模型：
- OpenAI：`gpt-4o` / `gpt-4o-mini`
- 通义千问：`qwen-vl-max` / `qwen-vl-plus`
- DeepSeek：`deepseek-v4-flash-vision-exp`（示例，请以实际可用模型为准）
- Moonshot：`moonshot-v1-8k-vision-preview`

</details>

<details>
<summary><b>3. 提示 "401 Unauthorized"？</b></summary>

- 检查 API Key 是否填写正确（注意前后空格）
- 检查 Key 是否已过期或额度不足
- 检查是否选错了服务商（如用 OpenAI Key 请求 DeepSeek 接口）

</details>

<details>
<summary><b>4. 聊天记录丢失了？</b></summary>

- 清理浏览器数据会清除 `localStorage`
- 隐私模式 / 无痕窗口关闭后不保留
- 建议定期导出重要对话（当前暂不支持导出，欢迎 PR）

</details>

<details>
<summary><b>5. 如何关闭滑块验证？</b></summary>

打开 `index.html`，找到 `window.addEventListener('load', ...)` 部分，改为直接调用：

```js
window.addEventListener('load', () => {
  renderAppPage();  // 直接进入聊天页，跳过滑块
});
```

</details>

<details>
<summary><b>6. 手机上的侧边栏无法打开？</b></summary>

- 确保屏幕宽度 < 768px（`md` 断点）
- 点击左上角 ☰ 图标打开
- 点击遮罩或右上角 × 关闭

</details>

<details>
<summary><b>7. 在线版和本地版有什么区别？</b></summary>

功能完全一致。在线版部署在 Cloudflare Pages，使用 HTTPS，可减少本地 `file://` 打开时的 CORS 问题，并支持手机直接访问。

在线地址：**https://ai-ol.pages.dev**

</details>

---

## 🤝 贡献指南

欢迎提交 Issue 和 PR！

### 开发流程

1. Fork 本仓库
2. 创建特性分支：`git checkout -b feature/your-feature`
3. 提交更改：`git commit -m "feat: 添加导出对话功能"`
4. 推送分支：`git push origin feature/your-feature`
5. 发起 Pull Request

### 提交规范

遵循 [Conventional Commits](https://www.conventionalcommits.org/zh-hans/)：

- `feat:` 新功能
- `fix:` 修复 Bug
- `docs:` 文档更新
- `style:` 代码格式（不影响功能）
- `refactor:` 重构
- `perf:` 性能优化

### 待办清单（欢迎认领）

- [ ] 对话导出（Markdown / JSON / 图片）
- [ ] 多会话管理（侧边栏历史列表）
- [ ] 深色 / 浅色主题切换
- [ ] 对话分享链接（URL 参数）
- [ ] 键盘快捷键（`Ctrl+K` 清屏等）
- [ ] Markdown 消息渲染 + 代码高亮
- [ ] PWA 支持（可离线使用）
- [ ] 多语言（英文 / 日文）

---

## 📄 License

本项目基于 [MIT License](./LICENSE) 开源，可自由使用、修改、分发。

---

## ⚠️ 免责声明

- 本工具仅用于技术学习与个人使用
- 请遵守所使用 API 服务商的服务条款
- 请勿将 API Key 硬编码后提交到公开仓库（本项目使用 `localStorage` 存储，不会写入代码）
- AI 生成内容仅供参考，请自行核实

---

## 🙏 致谢

- [Tailwind CSS](https://tailwindcss.com/) —— 实用优先的 CSS 框架
- [Font Awesome](https://fontawesome.com/) —— 图标库
- [Cloudflare Pages](https://pages.cloudflare.com/) —— 静态站点托管
- 所有贡献者与使用者 ❤️

---

<div align="center">

**⭐ 如果这个项目对你有帮助，欢迎点亮一颗 Star！**

在线体验：**https://ai-ol.pages.dev**

Made with ❤️ by [xiaoovo663](https://github.com/your-username)

</div>
