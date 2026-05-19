# HTTP 响应头里的 Date 是 GMT，怎么和 Unix 时间戳对上？

**在网站上阅读：** [https://gegegj.com/blog/timestamp-http-date-header-to-unix](https://gegegj.com/blog/timestamp-http-date-header-to-unix)

**相关工具：** [打开工具页](https://gegegj.com/calc/timestamp)

## Date 头长什么样

常见形如 `Sun, 21 May 2026 10:30:00 GMT`，表示服务器认为的当前时刻（GMT/UTC），不是北京时间。抓包工具和浏览器开发者工具 Network 里都能看到。

要转成 Unix 秒或毫秒：先按 UTC 理解该时刻，再在 [Unix 时间戳换算](https://gegegj.com/calc/timestamp) 输入对应时间或粘贴转换结果。若工具支持 ISO 8601，也可先写成 `2026-05-21T10:30:00Z` 再转。

和 `Date.now()` 毫秒区别见 [除以1000](https://gegegj.com/blog/timestamp-date-now-divide-1000)；日志差八小时见 [日志时区](https://gegegj.com/blog/timestamp-log-timezone-pitfalls)。

## 别和 Last-Modified、Expires 混

Last-Modified 是资源修改时间，Expires 是缓存过期时间，含义都不是「现在」。Age 头是缓存已存时长，更不是时间戳。

## 抓包时常见时间字段

除 Date 头外，还有 Age、Expires、Last-Modified，含义不同，别都当「当前时间」去转时间戳。

CDN 日志可能用毫秒、秒、或 ISO 字符串混排，先统一再入库，否则检索会乱序。

把北京时间字符串当 UTC 解析会固定差八小时，见日志时区专题；HTTP Date 本身是 GMT。

保存原始头字符串再转换，便于和厂商工单对照，不要只存转换后的数字。

## 使用提醒

本文围绕「Unix 时间戳换算」的一个常见问题展开，工具在浏览器本地处理数据，适合试算与沟通；签约、申报、诊疗请以官方口径为准。

涉及隐私的数据请先脱敏；公共电脑、录屏环境勿粘贴真实工资、病历、Token 或合同金额。

## 小结

把标题里的疑问拆开：先确认口径，再用对应工具试算；正式结果以合同、银行、税务、医院、学校规则为准。工具页 Unix 时间戳换算 在浏览器本地运行，适合沟通与备忘。
