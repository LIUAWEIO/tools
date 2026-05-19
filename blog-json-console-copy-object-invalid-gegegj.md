# 浏览器控制台复制的对象，粘贴进 JSON 格式化为什么报错？

**在网站上阅读：** [https://gegegj.com/blog/json-console-copy-object-invalid](https://gegegj.com/blog/json-console-copy-object-invalid)

**相关工具：** [打开工具页](https://gegegj.com/tool/json)

## 两种「看起来像 JSON」的复制来源

在 Chrome DevTools 里 `console.log(response)` 后，从预览树复制或 `copy(data)`，剪贴板里往往是 JavaScript 对象字面量：键名可以不加引号（`{a:1}`）、可以用单引号字符串、可以有 `undefined`、`function(){}`、`new Date()`、尾随逗号。RFC 8259 标准 JSON 只允许双引号键名、双引号字符串、数字、true/false/null、对象与数组，且不能有上述 JS 专属内容。

因此粘贴进 [JSON 格式化工具](https://gegegj.com/tool/json)（json formatter / json validator）时，常见报错是 Unexpected token、property name must be double-quoted、或鸽鸽工具网中文提示「键名必须使用双引号包裹」。这不是工具坏了，而是格式族谱不对。

正确拿 JSON 的方式：① Network 面板选中请求，切到 Response，复制 Raw 原文；② 在控制台执行 `copy(JSON.stringify(obj, null, 2))` 再粘贴；③ Postman 用 Raw 而非 Preview 树拖拽。

## 对照例子：哪些粘贴会失败

失败示例：`{name: '张三', age: 18,}`（单引号、无引号键、尾随逗号）。失败：`{ok: true, data: undefined}`（undefined）。失败：直接粘 `[object Object]` 或函数 toString 结果。

通过示例：`{"name":"张三","age":18}`。通过后点「格式化（缩进）」可折叠查看；只要语法可点「仅校验」。若响应是 `{"data":"{\"id\":1}"}` 字符串套 JSON，需分两层解析，见 [data 带反斜杠](https://gegegj.com/blog/18-json-data-field-escaped-string-gegegj)。

`.env`、K8s 里一行 JSON 启动失败，见 [一行配置校验](https://gegegj.com/blog/json-env-one-line-config-validate)。Git 冲突残留 `<<<<` 见 [合并冲突](https://gegegj.com/blog/json-config-merge-conflict-tips)。超大日志先 截取。

## 和 Postman、前端调试习惯

Postman 的 Pretty 视图友好，但复制时要确认复制的是 JSON 文本。axios 打印的 config.data 若是对象，控制台复制同样不是 JSON。需要给后端传 JSON 时，用 `JSON.stringify` 生成 body，Content-Type 设 application/json。

时间字段若是毫秒时间戳，格式化通过后可用 Unix 时间戳换算 对照；勿把 Excel 序列号当时间戳，见鸽鸽工具网时间戳类文章。语法边界见 JSON 长文、JSON 指南、JSON 教程。

## 隐私与工具边界

解析在浏览器本地完成，不上传业务内容；含 Token、手机号、订单号请先脱敏。工具不做 JSON Schema 校验、不转 CSV、不支持 JSON5；只做语法解析、美化、压缩与中文报错。

## 小结

控制台对象 ≠ JSON：先 `JSON.stringify` 或抄 Response 原文，再用 JSON 格式化工具 做 json validator。报错先看是不是 JS 字面量、HTML 错误页、冲突标记三类误判之一。
