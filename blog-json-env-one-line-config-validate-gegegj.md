# 配置文件里一行 JSON 启动就报错，怎么先本地验语法？

**在网站上阅读：** [https://gegegj.com/blog/json-env-one-line-config-validate](https://gegegj.com/blog/json-env-one-line-config-validate)

**相关工具：** [打开工具页](https://gegegj.com/tool/json)

## 一行 JSON 往往是「最难读」的那种

Kubernetes ConfigMap、CI 变量、`.env` 里塞 `FEATURE_FLAGS={"a":1,"b":2}`，编辑器不换行，少一个 `}` 服务就起不来。错误日志里常见 `Unexpected token` 或 `Unexpected end of JSON input`，盯着一行肉眼找括号很累。

把整段贴进 [JSON 格式化工具](https://gegegj.com/tool/json)（json formatter / json validator），点「仅校验语法」。鸽鸽工具网用浏览器本地 `JSON.parse`，给出中文原因与行列提示；中文逗号、单引号键名、尾随逗号会标出。通过后再点「格式化（缩进）」折叠查看，比 IDE 临时装插件快，适合没有本地 jq 的环境。

## 案例：尾随逗号与转义字符串

非法示例：`{"enabled": true,}` —— 对象最后一个属性后多了逗号。工具会提示类似「对象属性值后缺少逗号或结束大括号」。合法应去掉逗号。

另一常见：`{"data": "{\"id\":1}"}` 外层合法，但业务数据在字符串里又套了一层 JSON，要复制 `data` 的值再解析一次，见 [data 带反斜杠怎么展开](https://gegegj.com/blog/18-json-data-field-escaped-string-gegegj)。别把 HTML 错误页、Git 冲突标记 `<<<<` 当 JSON 解析，见 [合并冲突后校验](https://gegegj.com/blog/json-config-merge-conflict-tips)。

## 和日志、时间戳、部署流程怎么衔接

超大日志不要整文件粘贴，先 [截取片段](https://gegegj.com/blog/json-log-snippet-workflow)。字段里若有 `createdAt: 1716100000`，用 [时间戳换算](https://gegegj.com/calc/timestamp) 对照人类时间。语法与业务是两件事：JSON 合法不代表字段名符合接口文档。

含 API Key、数据库密码的配置请先脱敏再粘贴；公共网络慎用任何在线框。更多能力见 [JSON 指南](https://gegegj.com/blog/json-formatter-guide)、[JSON 教程](https://gegegj.com/blog/12-json-formatter-gegegj) 与 [JSON 长文](https://gegegj.com/blog/longread-json-data-on-the-wire)。不支持 JSON5、Schema 校验、转 CSV。

## 小结

部署前习惯：粘贴→仅校验→（通过）格式化→改错→再校验。一行配置并不简单；本地中文报错能省掉半数「其实是少逗号」的加班时间。
