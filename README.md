<div align="center">💬 AI Chat Client

一个单文件、纯前端、开箱即用的 AI 对话客户端

兼容 OpenAI 格式接口 · 支持流式输出 · 多模态图片 · 移动端适配

🌐 在线体验 · 功能特性 · 快速开始 · 常见问题

</div>---

🌐 在线体验

无需安装，打开即用：

👉 https://ai-ol.pages.dev

在线版已部署在 Cloudflare Pages，支持 HTTPS，可避免本地 file:// 打开时的 CORS 限制。

---

✨ 项目简介

AI Chat Client 是一个无需构建、无需后端、单文件部署的 AI 对话网页客户端。

它兼容所有遵循 OpenAI 接口规范的 API（如 DeepSeek、OpenAI、Moonshot、通义千问、本地 Ollama、One API 等），只需填入接口地址和 Key 即可开始对话。

所有配置和聊天记录保存在浏览器本地（localStorage），不会上传到任何第三方服务器。

---

🚀 功能特性

分类 功能 说明
💬 对话 流式输出 打字机效果逐字显示，支持中途停止生成
🖼️ 多模态 图片上传 支持 jpg/png/gif/webp，大图自动压缩为 JPEG
🔌 兼容性 OpenAI 格式 任意兼容 /v1/chat/completions 的服务均可使用
🧠 模型管理 一键获取列表 通过 /v1/models 拉取模型，也支持手动添加模型 ID
⚙️ 参数控制 精细调节 temperature / top_p / max_tokens / 系统提示词
📊 诊断 延迟测试 一键测试接口连通性和响应耗时
💾 持久化 本地存储 配置、对话历史保存在浏览器，刷新不丢失
📱 响应式 移动端适配 手机 / 平板 / 桌面自适应布局
🎨 界面 现代 UI Tailwind CSS + 渐变动效 + 流畅过渡动画
🔒 访问控制 滑块验证 可选的滑动验证码，防止误触/爬虫

---

📸 界面预览

在线预览：https://ai-ol.pages.dev

桌面端 移动端
./IMG_3993.PNG ./IMG_3992.PNG

---

🏁 快速开始

方式一：直接在线使用（推荐）

打开 https://ai-ol.pages.dev，填写接口地址和 API Key 即可开始对话。

方式二：本地直接打开

```bash
git clone https://github.com/xiaoovo663/AI-Chat-Client.git
cd AI-Chat-Client
```

双击打开 index.html 即可使用。

⚠️ 注意：本地以 file:// 协议打开时，浏览器会触发 CORS 跨域限制，调用远程 API 可能失败。推荐使用在线版或本地静态服务器。

方式三：部署到 Cloudflare Pages

本项目已部署示例：https://ai-ol.pages.dev

自行部署步骤：

1. Fork 本仓库
2. 登录 Cloudflare Pages
3. 点击 Create a project → Connect to Git
4. 选择你的仓库
5. 构建配置：
   · Framework preset：None
   · Build command：留空
   · Build output directory：/
6. 点击 Save and Deploy

---

⚙️ 使用说明

1. 填写接口配置

点击左上角 ☰ 打开侧边栏，填写：

字段 示例 说明
接口地址 https://api.deepseek.com/v1 OpenAI 格式的 Base URL
API Key sk-xxxxxxxx 各平台申请的密钥
模型 deepseek-chat 点击 🔄 自动获取，或手动添加

💡 接口地址需包含版本路径（如 /v1），程序会自动拼接 /chat/completions 和 /models。

2. 保存并开始对话

点击 「保存配置」，回到输入框即可发送消息。

3. 上传图片（可选）

· 点击 🖼️ 按钮选择图片，支持多张
· 必须使用 vision 多模态模型（如 gpt-4o、qwen-vl-max 等）
· 图片会自动压缩到最长边 1280px，减少 Token 消耗

---

🌐 兼容的 API 服务商

服务商 Base URL 示例
DeepSeek https://api.deepseek.com/v1
OpenAI https://api.openai.com/v1
Moonshot https://api.moonshot.cn/v1
通义千问 https://dashscope.aliyuncs.com/compatible-mode/v1
Ollama http://localhost:11434/v1
SiliconFlow https://api.siliconflow.cn/v1

---

❓ 常见问题

<details>
<summary><b>1. 提示 "Failed to fetch" 或跨域错误？</b></summary>浏览器控制台报 CORS 错误，说明接口禁止浏览器直连。解决方案：

· ✅ 使用在线版 https://ai-ol.pages.dev（HTTPS 环境）
· ✅ 确认 API 服务商支持 CORS
· ✅ 使用 One API 等网关中转

</details><details>
<summary><b>2. 上传图片后模型报错 / 无响应？</b></summary>图片输入必须使用 vision 多模态模型，普通文本模型不支持 image_url 格式。

</details><details>
<summary><b>3. 提示 "401 Unauthorized"？</b></summary>· 检查 API Key 是否填写正确（注意前后空格）
· 检查 Key 是否已过期或额度不足

</details>---

🙏 致谢

· Tailwind CSS
· Font Awesome
· Cloudflare Pages

---

<div align="center">⭐ 如果这个项目对你有帮助，欢迎点亮一颗 Star！

Made with ❤️ by xiaoovo663

</div>
