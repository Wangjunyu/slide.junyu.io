# AI 操作指南

## 项目说明
这是一个基于 reveal-md 的幻灯片项目，域名：https://slide.junyu.io

## 创建新幻灯片

### 1. 创建 Markdown 文件
```markdown
---
title: 幻灯片标题
separator: ---
verticalSeparator: ----
theme: black
revealOptions:
  transition: 'slide'
  slideNumber: true
---

# 第一页标题
内容

---

# 第二页标题
内容

----

## 第二页的子页面
使用 ---- 创建垂直子页面
```

### 2. 生成 HTML
```bash
npx reveal-md your-file.md --static _site
cp _site/your-file.html ./
```

### 3. 提交到 GitHub
```bash
git add .
git commit -m "Add new slide: 标题"
git push origin main
```

## 重要规则

### 排版
- **居中显示**：一级标题（#）、流程列表、纯文字页面
- **左对齐**：二级标题（##）下有内容的页面，使用 `<div style="text-align: left;">` 包裹

### 文件管理
- Markdown 源文件和 HTML 都放根目录
- 图片放 `images/` 目录
- `node_modules/`、`_site/`、`.spec-workflow/` 已在 .gitignore

### Git 操作
- 远程仓库使用 SSH：`git@github.com:Wangjunyu/slide.junyu.io.git`
- SSH 密钥路径：`~/.ssh/id_ed25519`
- index.html 会自动更新，记得一起提交

## 常用命令

```bash
# 生成幻灯片
npx reveal-md file.md --static _site

# 复制到根目录
cp _site/file.html ./

# 提交推送
git add . && git commit -m "message" && git push origin main
```
