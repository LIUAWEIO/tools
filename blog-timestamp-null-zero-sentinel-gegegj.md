# 数据库里是空值还是 0，和日志里的 Unix 时间戳怎么分清？

**在网站上阅读：** [https://gegegj.com/blog/timestamp-null-zero-sentinel](https://gegegj.com/blog/timestamp-null-zero-sentinel)

**相关工具：** [打开工具页](https://gegegj.com/calc/timestamp)

## NULL、0 和 0000-00-00 不是一回事

MySQL 里 `created_at` 为 NULL：业务上表示「未发生」；拿去 [Unix 时间戳换算](https://gegegj.com/calc/timestamp) 没有意义。值为 0（整型时间戳）：表示 1970-01-01 00:00:00 UTC，北京时间常见显示为 08:00:00，有人误以为是「没写入」——其实是写了哨兵零。值为 `0000-00-00 00:00:00`：历史占位，部分驱动读成无效日期，和 epoch 无关。

日志里 `time: 1716100000` 这类 10 位数，先确认是秒还是毫秒：13 位多半是毫秒，见 [10 位还是 13 位](https://gegegj.com/blog/timestamp-api-contract-ms)。例如 1716100000 秒对应 2024 年 5 月中旬左右（以换算结果为准），若你期望是 2025 年，可能是字段用错单位或时区看错。

## 排障顺序：先类型，再换算，再时区

导出 CSV 时空值有时变成空字符串、有时变成 0，要在数据字典里写清。接口 JSON 里 `"createdAt": null` 与 `"createdAt": 0` 语义完全不同；整条日志可贴 JSON 格式化工具 展开（大文件先 [截取片段](https://gegegj.com/blog/json-log-snippet-workflow)）。

换算结果与界面差 8 小时，多半是 UTC 与本地混淆，见 [日志差 8 小时](https://gegegj.com/blog/timestamp-log-timezone-pitfalls)。跨国对比用 时区换算。更系统的说明见 时间戳。

## 和 Excel、JavaScript 的边界

Excel 日期序列号不是 Unix 时间戳，别直接粘贴进本工具。JS 里 `new Date(0)` 显示 1970 年，和业务「未设置」要代码层区分。生产环境以接口文档、数据库字段类型（INT/BIGINT/DATETIME）为准。

## 小结

看到奇怪时间：先问是空、哨兵零还是有效 epoch；再选 10/13 位；最后核对 UTC。工具适合联调与读日志，不修改数据库数据。
