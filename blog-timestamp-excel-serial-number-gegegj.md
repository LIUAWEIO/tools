# Excel 里一串四万多是不是时间戳？和 Unix 秒怎么对上号

**在网站上阅读：** [https://gegegj.com/blog/timestamp-excel-serial-number](https://gegegj.com/blog/timestamp-excel-serial-number)

**相关工具：** [打开工具页](https://gegegj.com/calc/timestamp)

## 四万多多半是 Excel 序列，不是 Unix 秒

Excel 把日期存成从 1899-12-30（Windows 默认）起的天数，带小数表示时间。例如 44927 可能对应 2023 年某天的日期单元格。Unix 时间戳是从 1970-01-01 UTC 起的秒或毫秒，10 位秒常见在 1.6～1.7×10⁹，13 位毫秒更大。把 44927 贴进 [Unix 时间戳换算](https://gegegj.com/calc/timestamp) 会得到荒谬年份，说明族谱错了。

从 CSV 导出接口数据，先看清列名和样例：created_at 是 1716100000 还是 44927。秒毫秒见 [10位13位](https://gegegj.com/blog/timestamp-api-contract-ms)；空值与零见 [NULL与0](https://gegegj.com/blog/timestamp-null-zero-sentinel)。

## 和日志、JSON 字段一起排

日志 JSON 里时间可能是 ISO 字符串、毫秒整数或秒整数。整段可 JSON 格式化 展开。差 8 小时见 [日志时区](https://gegegj.com/blog/timestamp-log-timezone-pitfalls)。系统说明见 时间戳长文。

## 小结

Excel 序列 ≠ Unix 时间戳；先认格式再选工具。Excel 内转换用 DATEVALUE 等函数，Unix 字段用鸽鸽工具网时间戳页。
