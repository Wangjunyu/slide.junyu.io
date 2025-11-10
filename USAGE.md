# Slide.junyu.io 使用指南

## 环境配置

项目已安装 reveal-md，可以将 Markdown 文件转换为精美的幻灯片。

## 快速开始

### 1. 创建新幻灯片

创建一个新的 `.md` 文件，例如 `my-presentation.md`：

```markdown
---
title: 我的演示
theme: black
---

# 第一页标题

内容

---

# 第二页标题

更多内容
```

### 2. 预览幻灯片

#### 方式一：预览所有 Markdown 文件
```bash
npm run preview
```
然后访问：`http://服务器IP:1948/`

会看到所有 `.md` 文件的列表，点击进入即可预览。

#### 方式二：预览单个文件
```bash
npm run preview:single my-presentation.md
```

### 3. 生成静态 HTML

#### 生成所有幻灯片
```bash
npm run build
```
生成的文件在 `_site/` 目录

#### 生成单个幻灯片
```bash
npm run build:single my-presentation.md
```

## 重要说明

### 端口配置
- 预览服务默认使用 **1948** 端口
- 绑定到 `0.0.0.0`，允许外部访问
- **请确保云服务器安全组已开放 1948 端口**

### Markdown 语法

- `---` (三个短横线) 分隔横向幻灯片
- `----` (四个短横线) 分隔垂直幻灯片
- 支持标准 Markdown 语法

### YAML Front Matter

在 Markdown 文件开头可以配置：

```markdown
---
title: 演示标题
theme: black  # 主题: black, white, league, beige, sky, night, serif, simple, solarized
transition: slide  # 过渡效果: none, fade, slide, convex, concave, zoom
slideNumber: true  # 显示页码
---
```

## 工作流程

1. **编辑** → 修改 `.md` 文件
2. **预览** → `npm run preview` 实时查看效果
3. **生成** → `npm run build` 生成 HTML
4. **发布** → 提交到 GitHub，自动部署到 https://slide.junyu.io

## 常见问题

### Q: 如何修改端口？
A: 编辑 `package.json` 中的 `--port 1948` 参数

### Q: 预览时看不到效果？
A: 检查：
1. 服务器安全组是否开放端口
2. 防火墙是否允许
3. 文件保存后是否刷新浏览器

### Q: 如何停止预览服务？
A: 按 `Ctrl + C`

## 参考资源

- [reveal-md 官方文档](https://github.com/webpro/reveal-md)
- [Reveal.js 文档](https://revealjs.com/)
