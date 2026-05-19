# JSON：接口和配置共用的「窄语法」，宽一点就不是它了

**在网站上阅读：** [https://gegegj.com/blog/longread-json-data-on-the-wire](https://gegegj.com/blog/longread-json-data-on-the-wire)

**相关工具：** [打开工具页](https://gegegj.com/tool/json)

## `{}` 与 `[]` 背后，是「键值 + 有序列表」两种积木

键必须是双引号字符串，值可以是字符串、数字、布尔、null、嵌套对象或数组；这套窄语法让不同语言都能解析。

它不是任意 JavaScript 字面量：注释、单引号、尾随逗号在标准 JSON 里都不合法，从控制台拷对象时要先过一遍清洗。

## 网络面板、curl、ConfigMap：同一语法，三种密度

浏览器里常见 Preview 树和原始 Response 文本；日志里可能是一行长串；K8s 片段常嵌在 YAML 多行字符串里。

## 联调、比对、合并冲突后：先让机器说「哪一行坏了」

缩进和折叠让层级一眼可见；中文错误提示能把目光锁到行附近。需要和时间对表时，可配合 [时间戳](https://gegegj.com/calc/timestamp) 看日志字段。

## 格式化页不是数据库，也不是密钥保险箱

脱敏后再粘贴；大文件先截取片段，避免浏览器卡死。

## 语法级错误会卡整条流水线

解析失败可能让服务 500、部署挂掉、客户端缓存异常；示例里误粘密钥则是另一类事故。

## 二进制协议多了，JSON 仍是「人类可读默认值」

gRPC、Protobuf 在性能链路上更常见，但文档、示例、排障记录仍大量用 JSON；JSON Schema 一类规范会继续补「人机共读」的缺口。

## 读完可以先做的一件事

从网络面板复制一条响应，丢进 [JSON 格式化工具](https://gegegj.com/tool/json) 做 json viewer 式折叠阅读，再试着故意删掉一个逗号看 json validator 是否报错；深入见 [JSON 格式化工具指南](https://gegegj.com/blog/json-formatter-guide)。
