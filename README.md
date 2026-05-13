# 科技芯前沿 — Hugo 博客

基于 Hugo 静态网站生成器搭建的科技博客，用于 SEO 引流涨粉。

## 快速开始

### 本地预览

```powershell
cd F:\workbuddy存储\2026-05-12-task-5\techcore-blog
C:\Users\admin01\hugo\hugo.exe server -D
```

浏览器打开 http://localhost:1313

### 构建站点

```powershell
C:\Users\admin01\hugo\hugo.exe --gc --minify
```

生成的文件在 `public/` 目录。

## 发布新文章

### 1. 创建文章

在 `content/posts/` 下新建 `.md` 文件，例如 `my-new-post.md`：

```markdown
---
title: "文章标题"
date: 2026-05-13
categories: ["AI芯片"]  # 可选：AI芯片/大模型/机器人/智能硬件
tags: ["标签1", "标签2"]
summary: "一句话摘要，会显示在首页卡片中"
---

正文内容...

---

**数据来源：** xxx

💬 **今日话题：** 你的问题？
```

### 2. 本地预览

```powershell
C:\Users\admin01\hugo\hugo.exe server -D
```

`-D` 参数会显示草稿文章（`draft: true`），发布时改为 `draft: false` 或删除 draft 字段。

### 3. 推送到 GitHub

```powershell
cd F:\workbuddy存储\2026-05-12-task-5\techcore-blog
git add .
git commit -m "发布新文章：xxx"
git push origin main
```

GitHub Actions 会自动构建并部署到 GitHub Pages。

## 目录结构

```
techcore-blog/
├── content/
│   ├── about.md          # 关于页面
│   └── posts/            # 文章目录
│       ├── article1.md
│       └── article2.md
├── themes/techcore/      # 自定义主题
│   ├── layouts/          # 模板文件
│   └── static/css/       # 样式文件
├── static/               # 静态资源（图片等）
├── hugo.toml             # 站点配置
└── .github/workflows/    # GitHub Pages 部署配置
```

## 配置说明

编辑 `hugo.toml`：

- `baseURL` — 网站地址，部署到 GitHub Pages 后改为实际地址
- `title` — 网站标题
- `params.description` — 网站描述，用于 SEO
- `menu` — 导航菜单配置

## 部署到 GitHub Pages

### 1. 创建 GitHub 仓库

1. 登录 GitHub，创建新仓库
2. 仓库名设为 `hobin.github.io`（与用户名一致）

### 2. 推送代码

```powershell
cd F:\workbuddy存储\2026-05-12-task-5\techcore-blog
git init
git add .
git commit -m "初始化博客"
git remote add origin https://github.com/hobin/hobin.github.io.git
git push -u origin main
```

### 3. 启用 GitHub Pages

1. 进入仓库 Settings → Pages
2. Source 选择 "GitHub Actions"
3. 等待 Actions 构建完成

### 4. 访问网站

打开 https://hobin.github.io

## 绑定自定义域名（可选）

1. 购买域名（如 techcore.cn）
2. 在域名 DNS 添加 CNAME 记录指向 `hobin.github.io`
3. 在仓库 Settings → Pages → Custom domain 填入域名
4. 勾选 "Enforce HTTPS"

## 日常维护时间

- **发布新文章：** 5-10 分钟（复制模板 → 改内容 → git push）
- **无需维护服务器：** GitHub Pages 托管，零运维
- **无需备份：** Git 仓库本身就是备份

## 成本

| 项目 | 费用 |
|------|------|
| 域名（可选） | ¥50-80/年 |
| GitHub Pages | 免费 |
| Hugo | 免费 |
| **总计** | **¥0-80/年** |
