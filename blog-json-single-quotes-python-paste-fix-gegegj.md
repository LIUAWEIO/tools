# 从 Python 复制过来的 JSON 报错，单引号是不是不行？

**在网站上阅读：** [https://gegegj.com/blog/json-single-quotes-python-paste-fix](https://gegegj.com/blog/json-single-quotes-python-paste-fix)

**相关工具：** [打开工具页](https://gegegj.com/tool/json)

## Python 打印的不是 JSON

Python 里 dict 打印常是单引号键值，键名有时无引号；None、True、False 也不是 JSON 的 null、true、false。直接贴进接口或 [JSON 格式化工具](https://gegegj.com/tool/json) 会报「键名须双引号」「非法字符」等，页面会用中文提示标出行列。

正确做法：在 Python 用 json.dumps(obj, ensure_ascii=False) 得到双引号字符串；或粘贴后分段手工替换（键名多时要小心）。

JavaScript 对象字面量也常有单引号、尾逗号，同样不是标准 JSON，见 [尾随逗号](https://gegegj.com/blog/json-trailing-comma-backend-reject)。

## 工具里怎么操作

先点「仅校验」看是否语法通过；再「格式化（缩进）」折叠查看；「压缩为一行」适合写进请求体。左右编辑器支持折叠大对象，比记事本找字段快。

中文显示成 \\u 转义见 [Unicode 中文](https://gegegj.com/blog/json-unicode-escape-chinese-display)；嵌套字符串见 [data 字段里的转义 JSON](https://gegegj.com/blog/18-json-data-field-escaped-string-gegegj)。

；控制台复制对象见 console 复制。

## 从日志里抠 JSON 的洁癖

Python repr 输出单引号、None/True/False，不是 JSON；用 json.dumps 或在线工具前先替换为双引号、null/true/false。

JSON 里键名可无引号？标准 JSON 不允许；部分 JS 引擎宽松解析，别当作可提交给后端的格式。

尾随逗号、注释在 JSON 标准里非法，见 尾随逗号；用「仅校验」先排语法。

大段粘贴前可先压缩一行确认结构，再格式化；嵌套见 data 字段里的转义 JSON。

## 工具按钮怎么用

粘贴后先点「仅校验」，红字提示常含行号；中文逗号、冒号会被中文报错提示标出，见页面说明。

通过校验再「格式化（缩进）」折叠查看；大对象用折叠 gutter 找字段，比肉眼扫一行快。

输出侧可复制给同事；敏感配置脱敏后再粘贴，本地处理不上传。

与 Unicode 中文、NaN 对照排错。

讲通用流程，本篇管 Python 单引号。

## 使用提醒

本文只讨论标题里的一个具体场景，JSON 格式化工具 在浏览器本地计算或处理，适合自查与沟通；签约、报税、诊疗、签证请以主管机构或合同为准。

涉及隐私的数据请先脱敏；公共电脑、录屏环境勿粘贴真实工资、病历、Token 或合同金额。

## 小结

单引号 JSON 不合法：用 json.dumps 或改双引号 + null/true/false 后再校验。敏感配置本地处理，勿粘贴含密钥内容到公共环境。

通过校验再提交后端，减少 400 排错时间。
