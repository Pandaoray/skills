# skill.github.io

这是 **Skill Notes** 的源码仓库，一个介绍 Claude Code Skills 的静态博客，部署在 GitHub Pages 上。

## 目录结构

```
skill.github.io/
├── index.html          # 首页，文章列表（post card 列表）
├── posts/              # 每篇文章一个 HTML 文件
│   ├── my-god.html
│   ├── podcast-chat.html
│   ├── agents-book.html
│   └── history-session.html
└── styles/
    └── main.css        # 全站共享样式
```

## 关联仓库

- **skillHome**（`~/Code/skillHome`，GitHub: `Pandaoray/skillHome`）：skill 文件实体仓库，存放所有 SKILL.md、scripts/ 和 .zip 打包。文章里的下载链接和 GitHub 源码链接都指向这里。

## 新增文章流程

1. 在 `posts/` 下新建 `<skill-name>.html`，参考现有文章格式
2. 在 `index.html` 的文章列表里添加对应的 `post-card`（放在最前面）
3. 推送到 `main` 分支，GitHub Pages 自动部署

## 文章规范

- 标题格式：`/<skill-name>：<一句话描述>`
- 标签：2-3 个，放在文章头部 `.article-tags`
- 下载区块（`download-box`）必须同时包含两个链接：
  - **下载按钮**（`.download-btn`）：指向 skillHome 的 `.zip` 文件
  - **GitHub 链接**（`.download-btn-ghost`）：指向 skillHome 对应目录的 `tree` 页面
  - 两者包裹在 `.download-box-actions` 中
- 下载提示（`.download-hint`）：说明安装步骤和依赖

## 下载区块模板

```html
<div class="download-box">
  <div class="download-box-info">
    <div class="download-box-name"><skill-name></div>
    <div class="download-box-desc">Claude Code Skill · SKILL.md + scripts/</div>
  </div>
  <div class="download-box-actions">
    <a class="download-btn" href="https://github.com/Pandaoray/skillHome/raw/main/<skill-name>/<skill-name>.zip" download="<skill-name>.zip">下载 Skill (.zip)</a>
    <a class="download-btn-ghost" href="https://github.com/Pandaoray/skillHome/tree/main/<skill-name>" target="_blank" rel="noopener">在 GitHub 查看源码 →</a>
  </div>
</div>

<p class="download-hint">解压后将 <code><skill-name>/</code> 目录放入 <code>~/.claude/skills/</code>，重启 Claude Code 即可使用。</p>
```
