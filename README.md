# Tanoya's Blog

一个基于 GitHub Pages 的个人博客，使用纯前端方案，Markdown 编写文章，无需构建工具。

## 📁 项目结构

```
├── index.html      # 主页（自动加载文章列表）
├── post.html       # 文章详情页（渲染 Markdown）
├── posts.json      # 文章配置文件
├── posts/          # Markdown 文章目录
│   ├── hello-world.md
│   └── about-me.md
└── README.md
```

## ✏️ 如何添加新文章

### 第一步：创建 Markdown 文件

在 `posts/` 目录下创建一个 `.md` 文件，例如 `posts/my-new-post.md`：

```markdown
# 文章标题

这里是正文内容，支持完整的 Markdown 语法...
```

### 第二步：更新 posts.json

在 `posts.json` 数组中添加一条记录：

```json
{
    "title": "我的新文章",
    "file": "posts/my-new-post.md",
    "date": "2026-04-14",
    "summary": "这是文章摘要，显示在首页列表中",
    "tags": ["标签1", "标签2"]
}
```

### 第三步：提交推送

```bash
git add .
git commit -m "添加新文章：我的新文章"
git push
```

完成！文章会自动出现在首页列表中。

## 🎨 功能特性

- **纯前端**：无需 Node.js、Jekyll 等构建工具
- **Markdown 渲染**：使用 [marked.js](https://marked.js.org/) 在浏览器端渲染
- **代码高亮**：使用 [highlight.js](https://highlightjs.org/) 语法高亮
- **响应式设计**：适配手机和桌面端
- **文章标签**：支持为文章添加分类标签
- **按日期排序**：首页文章自动按日期倒序排列

## 📝 posts.json 字段说明

| 字段 | 必填 | 说明 |
|------|------|------|
| `title` | ✅ | 文章标题，显示在首页列表 |
| `file` | ✅ | Markdown 文件路径，相对于根目录 |
| `date` | ✅ | 发布日期，格式 `YYYY-MM-DD` |
| `summary` | ❌ | 文章摘要，显示在首页卡片中 |
| `tags` | ❌ | 标签数组，如 `["技术", "生活"]` |
