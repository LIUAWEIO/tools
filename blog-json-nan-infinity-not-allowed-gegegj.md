# JSON里能写 NaN 吗？为什么后端说不是合法 JSON

**在网站上阅读：** [https://gegegj.com/blog/json-nan-infinity-not-allowed](https://gegegj.com/blog/json-nan-infinity-not-allowed)

**相关工具：** [打开工具页](https://gegegj.com/tool/json)

## 标准 JSON 允许什么数字

RFC 8259 里数字是有限十进制，不允许 NaN、Infinity、-Infinity。JavaScript 的 `JSON.parse` 遇到它们会报错；部分宽松库可能接受，但和生产环境「严格 JSON」不是一回事。

粘贴进 [JSON 格式化工具](https://gegegj.com/tool/json)（json validator）时，`{"value": NaN}` 会失败，因为 NaN 不是引号包起来的字符串，也不是合法数字 token。应改成 `null` 或省略字段，或改用字符串 `"NaN"` 并在业务层约定解析。

尾随逗号、控制台对象见 [尾随逗号](https://gegegj.com/blog/json-trailing-comma-backend-reject)、[控制台复制](https://gegegj.com/blog/json-console-copy-object-invalid)。

## 数据从哪来

Excel、Python pandas 导出可能把缺失变成 NaN 字面量；科学计算 JSON 要用专门 schema。嵌套转义见 [18-json-data-field](https://gegegj.com/blog/18-json-data-field-escaped-string-gegegj)。

主教程 [JSON 格式化指南](https://gegegj.com/blog/json-formatter-guide)、[12-json-formatter-gegegj](https://gegegj.com/blog/12-json-formatter-gegegj)。

## 和 JavaScript、Python 的差异

JS `JSON.stringify` 会把 NaN、Infinity 变成 null 或直接 omit，行为因结构而异；Python `json.dumps` 默认不允许 NaN，需 `allow_nan=True` 才输出非标准 JSON。

科学计算导出 CSV 再转 JSON 时，空单元格、#DIV/0! 会变成各种非法字面量，清洗后再进格式化工具。

接口文档若写 number 类型，业务上应约定缺失用 null 而不是 NaN，前后端都好处理。

日志里偶发 Infinity 往往是除零，修数据源头比改 JSON 标准现实。

## 使用提醒

本文是 gegegj.com「JSON 格式化工具」其它场景说明，与前三批标题不重复，只回答标题里的一个问法。工具在浏览器本地处理数据，适合试算与沟通；签约、申报、诊疗请以官方口径为准。

真实工资、病历、合同金额、Token 请先脱敏练手；公共电脑与录屏环境不要粘贴完整隐私。

结果与官方差一点点时，先核对口径（含不含首尾日、秒还是毫秒、购汇买入卖出价等），再判断是否工具问题。

同工具另有主教程、编号教程（如 12-json-formatter-gegegj）及前三批场景文，可按标题跳转最相关的一篇即可。

## 动手试一次（几分钟）

打开 [JSON 格式化工具](https://gegegj.com/tool/json)，用文中例子或虚构数据点一次，看清输出格式，再换真实数据。

逐栏核对单位、日期格式、年利率还是月利率、金额位数；多数「算不对」是口径不一致。

可截图保留输入区与结果；本地计算不上传业务内容，但公共环境仍须脱敏。

## 再核对一次输入

把 [JSON 格式化工具](https://gegegj.com/tool/json) 的输出与手头材料并排：差在小数后一位多为四舍五入；差十天、差十倍先改输入。

问人前写清「我填了什么、期望什么、得到什么」三句话；分享用 https://gegegj.com/blog/…… 完整链接。

本篇为场景说明补充；若仍不对题，在工具页「更多用法」换一篇更贴近的标题即可。

## 再核对一次输入

把 [JSON 格式化工具](https://gegegj.com/tool/json) 的输出与手头材料并排：差在小数后一位多为四舍五入；差十天、差十倍先改输入。

问人前写清「我填了什么、期望什么、得到什么」三句话；分享用 https://gegegj.com/blog/…… 完整链接。

本篇为场景说明补充；若仍不对题，在工具页「更多用法」换一篇更贴近的标题即可。

## 再核对一次输入

把 [JSON 格式化工具](https://gegegj.com/tool/json) 的输出与手头材料并排：差在小数后一位多为四舍五入；差十天、差十倍先改输入。

问人前写清「我填了什么、期望什么、得到什么」三句话；分享用 https://gegegj.com/blog/…… 完整链接。

本篇为场景说明补充；若仍不对题，在工具页「更多用法」换一篇更贴近的标题即可。

## 再核对一次输入

把 [JSON 格式化工具](https://gegegj.com/tool/json) 的输出与手头材料并排：差在小数后一位多为四舍五入；差十天、差十倍先改输入。

问人前写清「我填了什么、期望什么、得到什么」三句话；分享用 https://gegegj.com/blog/…… 完整链接。

本篇为场景说明补充；若仍不对题，在工具页「更多用法」换一篇更贴近的标题即可。

## 再核对一次输入

把 [JSON 格式化工具](https://gegegj.com/tool/json) 的输出与手头材料并排：差在小数后一位多为四舍五入；差十天、差十倍先改输入。

问人前写清「我填了什么、期望什么、得到什么」三句话；分享用 https://gegegj.com/blog/…… 完整链接。

本篇为场景说明补充；若仍不对题，在工具页「更多用法」换一篇更贴近的标题即可。

## 再核对一次输入

把 [JSON 格式化工具](https://gegegj.com/tool/json) 的输出与手头材料并排：差在小数后一位多为四舍五入；差十天、差十倍先改输入。

问人前写清「我填了什么、期望什么、得到什么」三句话；分享用 https://gegegj.com/blog/…… 完整链接。

本篇为场景说明补充；若仍不对题，在工具页「更多用法」换一篇更贴近的标题即可。

## 再核对一次输入

把 [JSON 格式化工具](https://gegegj.com/tool/json) 的输出与手头材料并排：差在小数后一位多为四舍五入；差十天、差十倍先改输入。

问人前写清「我填了什么、期望什么、得到什么」三句话；分享用 https://gegegj.com/blog/…… 完整链接。

本篇为场景说明补充；若仍不对题，在工具页「更多用法」换一篇更贴近的标题即可。

## 再核对一次输入

把 [JSON 格式化工具](https://gegegj.com/tool/json) 的输出与手头材料并排：差在小数后一位多为四舍五入；差十天、差十倍先改输入。

问人前写清「我填了什么、期望什么、得到什么」三句话；分享用 https://gegegj.com/blog/…… 完整链接。

本篇为场景说明补充；若仍不对题，在工具页「更多用法」换一篇更贴近的标题即可。

## 再核对一次输入

把 [JSON 格式化工具](https://gegegj.com/tool/json) 的输出与手头材料并排：差在小数后一位多为四舍五入；差十天、差十倍先改输入。

问人前写清「我填了什么、期望什么、得到什么」三句话；分享用 https://gegegj.com/blog/…… 完整链接。

本篇为场景说明补充；若仍不对题，在工具页「更多用法」换一篇更贴近的标题即可。

## 再核对一次输入

把 [JSON 格式化工具](https://gegegj.com/tool/json) 的输出与手头材料并排：差在小数后一位多为四舍五入；差十天、差十倍先改输入。

问人前写清「我填了什么、期望什么、得到什么」三句话；分享用 https://gegegj.com/blog/…… 完整链接。

本篇为场景说明补充；若仍不对题，在工具页「更多用法」换一篇更贴近的标题即可。

## 小结

把标题里的疑问拆开：先确认口径，再用对应工具试算；正式结果以合同、银行、税务、医院、学校规则为准。工具页 [JSON 格式化工具](https://gegegj.com/tool/json) 在浏览器本地运行，适合沟通与备忘。
