# 日志里的时间戳和界面时间差 8 小时？先看 UTC 再看本地

**在网站上阅读：** [https://gegegj.com/blog/timestamp-log-timezone-pitfalls](https://gegegj.com/blog/timestamp-log-timezone-pitfalls)

**相关工具：** [打开工具页](https://gegegj.com/calc/timestamp)

## 排查顺序

确认 10 位秒与 13 位毫秒；再用工具同时看 UTC 与本地，避免只盯一个字符串。

基础说明见 [Unix 时间戳换算指南](https://gegegj.com/blog/timestamp-guide)。

## 和时区工具配合

若要把「某一绝对时刻」转成多地会议时间，可继续用 [时区换算](https://gegegj.com/calc/timezone)。
