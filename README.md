# github-seo-articles 目录说明

本目录存放与 **[鸽鸽工具网](https://gegegj.com/)** 对应的推广与说明类 Markdown 文稿。构建时由仓库脚本 `npm run build:seo-posts`（见 `scripts/build-seo-blog-posts.mjs`）解析为 `src/data/seoMarkdownBlogPosts.json`，并在站内以博客形式发布（路径形如 `https://gegegj.com/blog/<文件名不含 .md>`）。

## 文件命名约定

- 使用前缀序号 + 主题 + 后缀：`00-site-overview-gegegj.md`、`01-mortgage-calculator-gegegj.md` …  
- 仅处理**文件名以两位数字开头**的 `.md` 文件；本目录下的 `README.md` 不会进入构建产物。

## 单篇 frontmatter（YAML）

每篇文首建议包含：

| 字段 | 说明 |
|------|------|
| `title` | 文章标题，亦用于站内 SEO 标题 |
| `description` | 摘要，用于 `meta description` 与列表摘要 |
| `keywords` | 英文逗号分隔关键词 |
| `canonical` | 可选；若指向某工具页（如 `https://gegegj.com/calc/tax`），构建结果会带 `relatedToolPath` 便于内链 |
| `updated` | 日期 `YYYY-MM-DD`，用于 `publishedAt` / `modifiedAt` |

## 文稿目录

| 文件 | 标题 | 站内博客 |
|------|------|----------|
| [00-site-overview-gegegj.md](./00-site-overview-gegegj.md) | 鸽鸽工具网｜免费在线房贷·个税·汇率·时间戳·JSON·二维码工具合集（免注册） | [/blog/00-site-overview-gegegj](https://gegegj.com/blog/00-site-overview-gegegj) |
| [01-mortgage-calculator-gegegj.md](./01-mortgage-calculator-gegegj.md) | 在线房贷计算器｜月供、总利息、等额本息与等额本金试算｜鸽鸽工具网 | [/blog/01-mortgage-calculator-gegegj](https://gegegj.com/blog/01-mortgage-calculator-gegegj) |
| [02-tax-calculator-gegegj.md](./02-tax-calculator-gegegj.md) | 个税计算器在线｜工资薪金、五险一金、专项附加扣除与年终奖估算｜鸽鸽工具网 | [/blog/02-tax-calculator-gegegj](https://gegegj.com/blog/02-tax-calculator-gegegj) |
| [03-rmb-uppercase-gegegj.md](./03-rmb-uppercase-gegegj.md) | 人民币大写转换器在线｜数字金额转中文大写（合同发票）｜鸽鸽工具网 | [/blog/03-rmb-uppercase-gegegj](https://gegegj.com/blog/03-rmb-uppercase-gegegj) |
| [04-exchange-rates-gegegj.md](./04-exchange-rates-gegegj.md) | 汇率换算器在线｜人民币对美元欧元日元及常用外币｜鸽鸽工具网 | [/blog/04-exchange-rates-gegegj](https://gegegj.com/blog/04-exchange-rates-gegegj) |
| [05-date-days-gegegj.md](./05-date-days-gegegj.md) | 日期天数计算器在线｜两日期间隔几天、工期与合同周期｜鸽鸽工具网 | [/blog/05-date-days-gegegj](https://gegegj.com/blog/05-date-days-gegegj) |
| [06-age-calculator-gegegj.md](./06-age-calculator-gegegj.md) | 年龄计算器在线｜周岁、虚岁与截止日（基准日）｜鸽鸽工具网 | [/blog/06-age-calculator-gegegj](https://gegegj.com/blog/06-age-calculator-gegegj) |
| [07-unix-timestamp-gegegj.md](./07-unix-timestamp-gegegj.md) | Unix 时间戳在线换算｜10 位秒 13 位毫秒与日期、UTC、ISO 8601｜鸽鸽工具网 | [/blog/07-unix-timestamp-gegegj](https://gegegj.com/blog/07-unix-timestamp-gegegj) |
| [08-timezone-converter-gegegj.md](./08-timezone-converter-gegegj.md) | 时区换算在线｜北京时间、UTC、纽约伦敦等多地同一时刻对照｜鸽鸽工具网 | [/blog/08-timezone-converter-gegegj](https://gegegj.com/blog/08-timezone-converter-gegegj) |
| [09-bmi-calculator-gegegj.md](./09-bmi-calculator-gegegj.md) | BMI 计算器在线｜体质指数与身高体重区间参考｜鸽鸽工具网 | [/blog/09-bmi-calculator-gegegj](https://gegegj.com/blog/09-bmi-calculator-gegegj) |
| [10-unit-converter-gegegj.md](./10-unit-converter-gegegj.md) | 单位换算在线｜长度重量温度（米英尺英寸、公斤磅、摄氏华氏）｜鸽鸽工具网 | [/blog/10-unit-converter-gegegj](https://gegegj.com/blog/10-unit-converter-gegegj) |
| [11-qrcode-generator-gegegj.md](./11-qrcode-generator-gegegj.md) | 二维码生成器在线｜网址文本、中间 Logo、PNG 本地下载｜鸽鸽工具网 | [/blog/11-qrcode-generator-gegegj](https://gegegj.com/blog/11-qrcode-generator-gegegj) |
| [12-json-formatter-gegegj.md](./12-json-formatter-gegegj.md) | JSON 格式化在线｜美化、压缩、语法校验与中文报错｜鸽鸽工具网 | [/blog/12-json-formatter-gegegj](https://gegegj.com/blog/12-json-formatter-gegegj) |

## 修改后如何同步到站点

1. 编辑本目录下对应 `.md`。  
2. 在项目根执行：`npm run build:seo-posts`（或完整 `npm run build`，`prebuild` 会包含该步骤）。  
3. 将更新后的 `src/data/seoMarkdownBlogPosts.json` 一并提交并部署。

## 仓库路径（GitHub）

源码目录：<https://github.com/LIUAWEIO/tools/tree/master/content/github-seo-articles>
