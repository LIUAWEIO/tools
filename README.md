# 鸽鸽工具网 · 说明文档索引

这里是 **[鸽鸽工具网](https://gegegj.com/)** 各篇说明文稿的索引，内容与网站上「博客」里的对应文章一致，方便你在 GitHub 上直接阅读或分享链接。

公开仓库 **[LIUAWEIO/tools](https://github.com/LIUAWEIO/tools)** 中，说明索引见根目录 [README.md](https://github.com/LIUAWEIO/tools/blob/master/README.md)；各篇文稿的 GitHub 地址为 `https://github.com/LIUAWEIO/tools/blob/master/<文件名>.md`（与下表「GitHub 原文」列一致）。本站源码将同名文件放在本目录 `content/github-seo-articles/` 下便于维护，构建时按文件名同步到博客。

- **想用工具**：请打开 [https://gegegj.com/](https://gegegj.com/)，在首页选择工具即可。  
- **想读长文说明**：下表「在网站上阅读」进入排版页面；「GitHub 原文」在浏览器中打开仓库里的 `.md`。

## 文档一览

| 说明主题 | 在网站上阅读 | GitHub 原文 |
|----------|----------------|-------------|
| 整站介绍与工具总览 | [打开](https://gegegj.com/blog/00-site-overview-gegegj) | [00-site-overview-gegegj.md](https://github.com/LIUAWEIO/tools/blob/master/00-site-overview-gegegj.md) |
| 房贷计算器 | [打开](https://gegegj.com/blog/01-mortgage-calculator-gegegj) | [01-mortgage-calculator-gegegj.md](https://github.com/LIUAWEIO/tools/blob/master/01-mortgage-calculator-gegegj.md) |
| 个税计算器 | [打开](https://gegegj.com/blog/02-tax-calculator-gegegj) | [02-tax-calculator-gegegj.md](https://github.com/LIUAWEIO/tools/blob/master/02-tax-calculator-gegegj.md) |
| 人民币大写 | [打开](https://gegegj.com/blog/03-rmb-uppercase-gegegj) | [03-rmb-uppercase-gegegj.md](https://github.com/LIUAWEIO/tools/blob/master/03-rmb-uppercase-gegegj.md) |
| 汇率换算 | [打开](https://gegegj.com/blog/04-exchange-rates-gegegj) | [04-exchange-rates-gegegj.md](https://github.com/LIUAWEIO/tools/blob/master/04-exchange-rates-gegegj.md) |
| 日期天数 | [打开](https://gegegj.com/blog/05-date-days-gegegj) | [05-date-days-gegegj.md](https://github.com/LIUAWEIO/tools/blob/master/05-date-days-gegegj.md) |
| 年龄计算 | [打开](https://gegegj.com/blog/06-age-calculator-gegegj) | [06-age-calculator-gegegj.md](https://github.com/LIUAWEIO/tools/blob/master/06-age-calculator-gegegj.md) |
| Unix 时间戳 | [打开](https://gegegj.com/blog/07-unix-timestamp-gegegj) | [07-unix-timestamp-gegegj.md](https://github.com/LIUAWEIO/tools/blob/master/07-unix-timestamp-gegegj.md) |
| 时区换算 | [打开](https://gegegj.com/blog/08-timezone-converter-gegegj) | [08-timezone-converter-gegegj.md](https://github.com/LIUAWEIO/tools/blob/master/08-timezone-converter-gegegj.md) |
| BMI 计算 | [打开](https://gegegj.com/blog/09-bmi-calculator-gegegj) | [09-bmi-calculator-gegegj.md](https://github.com/LIUAWEIO/tools/blob/master/09-bmi-calculator-gegegj.md) |
| 单位换算 | [打开](https://gegegj.com/blog/10-unit-converter-gegegj) | [10-unit-converter-gegegj.md](https://github.com/LIUAWEIO/tools/blob/master/10-unit-converter-gegegj.md) |
| 二维码生成 | [打开](https://gegegj.com/blog/11-qrcode-generator-gegegj) | [11-qrcode-generator-gegegj.md](https://github.com/LIUAWEIO/tools/blob/master/11-qrcode-generator-gegegj.md) |
| JSON 格式化 | [打开](https://gegegj.com/blog/12-json-formatter-gegegj) | [12-json-formatter-gegegj.md](https://github.com/LIUAWEIO/tools/blob/master/12-json-formatter-gegegj.md) |

更多教程与场景类文章见站内 [博客列表](https://gegegj.com/blog)。

## 文稿里一般写什么

每篇通常包括：**功能说明**、**可填哪些参数**、**适合什么场景**、**怎么用**、**常见问题**、**数据从哪来**（如适用）以及**免责声明**。具体小节以各篇正文为准。

---

<details>
<summary>给维护者（仓库协作者）</summary>

- **标题、摘要、关键词、canonical、更新日期** 写在同目录 [`article-meta.json`](./article-meta.json) 里（按 slug，与 `00-xxx-gegegj.md` 文件名对应），`.md` 里只保留正文，避免在 GitHub 阅读时先看到一大段 YAML。
- 带序号前缀的 `.md` 会在站点构建时写入 `src/data/seoMarkdownBlogPosts.json`，并出现在 `/blog/<文件名不含扩展名>`。
- 修改正文或元数据后，在项目根执行 `npm run build:seo-posts`（或完整 `npm run build`），将更新后的 `seoMarkdownBlogPosts.json` 与 `article-meta.json` 一并提交并部署。
- 若某篇暂时只有 `.md` 且未在 `article-meta.json` 中登记，构建脚本仍会尝试解析文件内的 `---` frontmatter（兼容旧稿）。

</details>
