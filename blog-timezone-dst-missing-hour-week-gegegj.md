# 夏令时切换那一周，会议时间为什么像「少了一小时」？

**在网站上阅读：** [https://gegegj.com/blog/timezone-dst-missing-hour-week](https://gegegj.com/blog/timezone-dst-missing-hour-week)

**相关工具：** [打开工具页](https://gegegj.com/calc/timezone)

## 夏令时不是「全世界一起拨表」

美国、加拿大、欧洲部分国家有夏令时，中国全年用北京时间（无夏令时）。美东在 3 月第二个周日 2:00 拨快至 3:00，11 月第一个周日再拨回。若你上周还按「北京 15:00 = 纽约凌晨 2:00」约例会，切换后同一纽约本地时刻对应的北京时间会差 1 小时——不是对方迟到，是心算规则过期了。

在 [时区换算](https://gegegj.com/calc/timezone) 里务必选具体日期（例如 2026-03-10 与 2026-03-17 各查一次），看纽约与北京的对应关系是否变化。发版、运维窗口建议 [UTC 与北京时间双写](https://gegegj.com/blog/timezone-release-window-utc)，减少「纽约时间 10:00」歧义。

## 日历邀请里怎么写才不容易乱

理想写法：写清 IANA 时区（如 America/New_York）或 UTC 偏移（GMT-4），并带 UTC 时间一行。只写「10:00 EST」在夏令时期间可能是错的（东部夏令时应用 EDT）。Teams、Google Calendar 会自动处理，但纯文字公告、邮件里手写时间最容易踩坑。

固定跨三地例会时段选择见 [中美欧三地](https://gegegj.com/blog/timezone-meeting-three-hubs)。系统存 Unix 时间戳时，同一戳在夏令时前后显示的多地本地字面值会变，属正常，见 [时间戳长文](https://gegegj.com/blog/longread-unix-timestamp-explained)。

## 和墨西哥、澳洲等地区的提醒

墨西哥近年调整过夏令时规则，不要沿用旧帖；澳洲南半球季节相反。工具按常见城市库展示，特殊行政区以当地政府当年公告为准。更多概念见 [时区指南](https://gegegj.com/blog/timezone-guide) 与 [民用时长文](https://gegegj.com/blog/longread-timezone-civil-time)。

## 小结

夏令时切换周：别靠上周心算；用带日期的多时区对照，公告里加 UTC。工具辅助核对，最终以日历软件邀请为准。
