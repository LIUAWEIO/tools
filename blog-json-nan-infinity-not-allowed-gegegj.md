# JSON里能写 NaN 吗？为什么后端说不是合法 JSON

**在网站上阅读：** [https://gegegj.com/blog/json-nan-infinity-not-allowed](https://gegegj.com/blog/json-nan-infinity-not-allowed)

**相关工具：** [打开工具页](https://gegegj.com/tool/json)

## 标准 JSON 允许什么数字

RFC 8259 里数字是有限十进制，不允许 NaN、Infinity、-Infinity。JavaScript 的 `JSON.parse` 遇到它们会报错；部分宽松库可能接受，但和生产环境「严格 JSON」不是一回事。

粘贴进 [JSON 格式化工具](https://gegegj.com/tool/json)（json validator）时，`{"value": NaN}` 会失败，因为 NaN 不是引号包起来的字符串，也不是合法数字 token。应改成 `null` 或省略字段，或改用字符串 `"NaN"` 并在业务层约定解析。

尾随逗号、控制台对象见 [尾随逗号](https://gegegj.com/blog/json-trailing-comma-backend-reject)、[控制台复制](https://gegegj.com/blog/json-console-copy-object-invalid)。

## 数据从哪来

Excel、Python pandas 导出可能把缺失变成 NaN 字面量；科学计算 JSON 要用专门 schema。嵌套转义见 [data 字段里的转义 JSON](https://gegegj.com/blog/18-json-data-field-escaped-string-gegegj)。

## 和 JavaScript、Python 的差异

JS `JSON.stringify` 会把 NaN、Infinity 变成 null 或直接 omit，行为因结构而异；Python `json.dumps` 默认不允许 NaN，需 `allow_nan=True` 才输出非标准 JSON。

科学计算导出 CSV 再转 JSON 时，空单元格、#DIV/0! 会变成各种非法字面量，清洗后再进格式化工具。

接口文档若写 number 类型，业务上应约定缺失用 null 而不是 NaN，前后端都好处理。

日志里偶发 Infinity 往往是除零，修数据源头比改 JSON 标准现实。

## 使用提醒

本文围绕「JSON 格式化工具」的一个常见问题展开，工具在浏览器本地处理数据，适合试算与沟通；签约、申报、诊疗请以官方口径为准。

涉及隐私的数据请先脱敏；公共电脑、录屏环境勿粘贴真实工资、病历、Token 或合同金额。

## 小结

把标题里的疑问拆开：先确认口径，再用对应工具试算；正式结果以合同、银行、税务、医院、学校规则为准。工具页 JSON 格式化工具 在浏览器本地运行，适合沟通与备忘。
