# Personal Website Builder Skill 🌐

本 Skill 旨在帮助用户利用 AI 快速设计、生成并部署个性化网页（支持 **学术风**、**创意作品集** 和 **3D 交互房间** 三种视觉风格），并一键部署至 Vercel。

---

## 📁 目录结构

```text
personal-website-builder/
├── SKILL.md      # Skill 核心规则与 Prompt 配置文件
└── README.md     # 使用指引与部署教程
```

---

## 🚀 如何安装与使用

### 1. 配置到 AI 客户端/Agent
* **Cursor / Windsurf / Claude Desktop**：将 `SKILL.md` 放置在项目的 `.cursor/rules/`、`.windsurfrules` 或 Skill 目录下，或者直接将内容粘贴给 AI。
* **自定义 AI Agent / Open-WebUI**：在 System Prompt 或 Skills 列表中追加 `SKILL.md` 内容。

---

## 💡 使用说明与命令示例

在对话中直接发送指令触发 Skill：

* **生成 3D 房间网页**：
  > “帮我用 3D 交互房间风格写一个个人主页，包含项目展示、个人简介和联系方式。”
* **生成学术主页**：
  > “我是一名研究员，请帮我生成一个 Academic 风格的学术个人主页代码。”
* **部署指导**：
  > “教我如何将刚写好的个人网页部署到 Vercel 上。”

---

## 🛠️ Vercel 一键部署流程

1. **获取 Token**：
   访问 [Vercel Token 页面](https://vercel.com/account/tokens) 并创建一个全新的 Token。

2. **配置本地变量**：
   在网站代码根目录下创建 `.env.local` 文件并填入：
   ```env
   VERCEL_TOKEN=你的_VERCEL_TOKEN
   ```

3. **执行一键发布**：
   在终端运行以下命令，AI 生成的网页即可瞬间上线并生成公网访问链接：
   ```bash
   npx vercel --token=$VERCEL_TOKEN --prod --yes
   ```

4. **绑定自定义域名（可选）**：
   根据提示前往 Cloudflare、阿里云或腾讯云配置 DNS 记录（如 CNAME 记录指向 `cname.vercel-dns.com`），即可完成域名绑定。