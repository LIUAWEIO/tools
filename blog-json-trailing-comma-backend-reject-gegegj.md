# JSON 最后多了一个逗号，为什么在线格式化直接报错？

**在网站上阅读：** [https://gegegj.com/blog/json-trailing-comma-backend-reject](https://gegegj.com/blog/json-trailing-comma-backend-reject)

**相关工具：** [打开工具页](https://gegegj.com/tool/json)

## 「我本地能跑」常常是两种 JSON

RFC 8259 标准 JSON 在对象或数组最后一个元素后面不能再有逗号：`{"a":1,}`、`[1,2,]` 都是非法。VS Code、部分 JavaScript 引擎、JSON5 允许尾随逗号，所以开发者手写配置觉得「没问题」，一交给 `JSON.parse`、Python `json.loads`、Go `json.Unmarshal` 或 [JSON 格式化工具](https://gegegj.com/tool/json)（json validator）就报 Unexpected token。

上线前把待发布配置粘贴进工具，点「仅校验」或「格式化」；报错行号附近看是否多逗号、少引号、单引号键名。控制台复制的对象不是 JSON，见 [控制台对象](https://gegegj.com/blog/json-console-copy-object-invalid)。

## 真实例子

失败：`{"host":"api.example.com","port":443,}`。通过：`{"host":"api.example.com","port":443}`。数组同理：`[1,2,3,]` 非法。

合并冲突残留、HTML 错误页误粘，见 [合并冲突](https://gegegj.com/blog/json-config-merge-conflict-tips)、[一行 env](https://gegegj.com/blog/json-env-one-line-config-validate)。嵌套字符串里的 JSON 若包在 data 字符串里，见 [data 字段里的转义 JSON](https://gegegj.com/blog/18-json-data-field-escaped-string-gegegj)。

## 团队习惯

CI 里加 json lint；提交前用工具过一遍。不要用「能跑」的 JS 对象字面量代替配置文件，除非明确用 JSON5 且全链路支持。

## 和队友对齐的规范写法

在仓库加 `.editorconfig` 或 Prettier 默认 JSON 严格模式，保存时去掉尾随逗号。不要把 `jsonc` 注释习惯带进生产配置。

从 Stack Overflow 复制的对象要带双引号键名；Python 字典打印结果不能当 JSON 提交。

接口返回 `application/json` 却 body 是 HTML 错误页时，格式化工具报错位置在开头，先查 HTTP 状态码。

大文件先校验再格式化，避免浏览器卡顿，见日志截取 workflow 文。

团队 Code Review 把「配置 JSON 能否 parse」当检查项，比上线后回滚便宜。

## 从 YAML 转 JSON 时

在线 YAML 转 JSON 工具也可能输出尾随逗号或 null 风格差异，转完仍要用鸽鸽工具网 JSON 工具校验再提交。

Kubernetes ConfigMap 里嵌 JSON 字符串时，外层 YAML 引号与内层 JSON 引号要层层转义，报错行号常指向外层。

数据库 JSON 字段存的是字符串还是对象，取出来可能多一层引号，见 data 字段转义专题。

Apifox、Swagger 导出的示例有时是 JSON Schema 不是实例 JSON，别整段粘进格式化框。

## 使用提醒

本文围绕「JSON 格式化工具」的一个常见问题展开，工具在浏览器本地计算，适合试算与沟通；正式办事仍以银行、税务、医院、合同文本为准。

涉及隐私的数据请先脱敏；公共电脑、录屏环境勿粘贴真实工资、病历、Token 或合同金额。

## 动手做一遍（约五分钟）

打开 JSON 格式化工具，先用文中例子或虚构小数据点一次按钮，确认输出长什么样，再换成你的真实数字。第一次只求跑通，不必纠结差一两元、差一天。

把输入项逐栏核对：单位是否选错、日期是否按「年-月-日」、利率是「年利率」还是「月利率」、金额有没有多写零。九成「算不对」其实是口径不一致，不是公式神秘。

若页面有「复制结果」或表格输出，可粘贴到备忘录与官方材料并排；截图时尽量带上输入区，方便过几天回看自己当时用的参数。

计算在浏览器本地完成，适合个人快速试算；涉及合同、税务申报、医疗、放贷等，请保留书面凭证并咨询对应机构。公共电脑、录屏直播环境请勿粘贴未脱敏的证件号、卡号、Token、完整病历。

## 小结

标准 JSON 禁止尾随逗号；用 JSON 格式化工具 上线前校验。宽松语法只在明确支持的链路使用。
