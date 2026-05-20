# JSON 里中文全变成 \u4e2d\u6587，怎么在编辑器里直接看到汉字？

**在网站上阅读：** [https://gegegj.com/blog/json-unicode-escape-chinese-display](https://gegegj.com/blog/json-unicode-escape-chinese-display)

**相关工具：** [打开工具页](https://gegegj.com/tool/json)

## 为什么会出现 \u

JSON 标准允许用 \\uXXXX 表示 Unicode 字符。很多库 JSON.stringify 默认把非 ASCII 转成 \\u 转义，文件更小、某些旧系统更稳，但人眼难读。

把整段贴进 [JSON 格式化工具](https://gegegj.com/tool/json)，点「格式化（缩进）」：先 JSON.parse 再 JSON.stringify 时，在浏览器里通常会输出可读中文（与运行环境有关）。若仍全是 \\u，检查是否只复制了字符串里的一层而未解析外层。

工具还提供压缩一行、仅校验；错误提示会标中文逗号、缺逗号等，见页面中文报错文案。

## 和乱码、双层 JSON 的区别

乱码是编码错了（UTF-8 当 GBK）；\\u4e2d 这类是合法转义，不是坏文件。控制台复制对象无效见 [console 复制](https://gegegj.com/blog/json-console-copy-object-invalid)。

接口 `data` 字段里再套一层 JSON 字符串，要分两次解析，见 [data 字段里的转义 JSON](https://gegegj.com/blog/18-json-data-field-escaped-string-gegegj)。

尾随逗号、NaN 非法见 [尾随逗号](https://gegegj.com/blog/json-trailing-comma-backend-reject)、NaN。

## 和接口、配置文件怎么协作

部分接口默认 JSON.stringify 不转中文，传 \\u 转义是传输层选择；后端若存库再读出，前端展示仍可能正常。

Git diff 里全是 \\u 转义时，本地格式化后再提交，团队约定「仓库里存可读中文」可减少 review 痛苦。

嵌套在字符串里的第二层 JSON，格式化外层后还要再解析内层，见 data 字段里的转义 JSON。

校验通过但业务字段为空，有时是键名大小写或多余 BOM，用 仅校验 先排除语法问题。

## 团队协作里的可读性约定

在 README 或接口文档写清：响应 JSON 是否转义中文、是否压缩空白；前后端联调少吵一半。

日志采集若把中文转成 \\u，检索关键词会失败；运维有时要求日志 UTF-8 明文，与 API 响应格式可以不同。

配置文件 config.json 用可读中文，diff 友好；生产环境由部署工具压缩，不必手写一行流。

Postman 保存响应时可能转义，复制到 JSON 格式化工具 再格式化，比肉眼数反斜杠快。

教学演示时，学生把中文键名也转义，要区分「键名」与「值」；键名一般保持中文或英文，不要混三层转义。

## 使用提醒

本文只讨论标题里的一个具体场景，JSON 格式化工具 在浏览器本地计算或处理，适合自查与沟通；签约、报税、诊疗、签证请以主管机构或合同为准。

涉及隐私的数据请先脱敏；公共电脑、录屏环境勿粘贴真实工资、病历、Token 或合同金额。

## 小结

看到 `\u`：先确认语法合法 → 格式化/解析 → 再处理内层字符串；团队可约定仓库是否存可读中文。

敏感配置勿上传公共环境；本地处理不上传业务数据。
