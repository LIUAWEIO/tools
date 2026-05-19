# 远程同事说「明天上午开个会」，我先该问清哪个时区？

**在网站上阅读：** [https://gegegj.com/blog/timezone-remote-which-city-first](https://gegegj.com/blog/timezone-remote-which-city-first)

**相关工具：** [打开工具页](https://gegegj.com/calc/timezone)

## 「明天上午」在谁那里都是上午

你在北京，同事在洛杉矶，他说「明天上午 10 点」若指本地 10 点，你这边可能是深夜。正确顺序：① 对方城市或 IANA 时区；② 具体日期（考虑国际日期线）；③ 是否夏令时。然后在 [时区换算](https://gegegj.com/calc/timezone) 选日期，对照北京、UTC 与对方城市，把结果写进邀请：「北京时间 ×月×日 23:00（洛杉矶 ×月×日 08:00，PST/PDT）」。

发版公告可 [UTC双写](https://gegegj.com/blog/timezone-release-window-utc)；三地选时段见 [中美欧](https://gegegj.com/blog/timezone-meeting-three-hubs)；夏令时周见 [夏令时](https://gegegj.com/blog/timezone-dst-missing-hour-week)。

## 模板一句话，减少来回

「请确认会议是按你本地时区还是北京时间？我按你给的时区在工具里对一下发邀请。」固定团队可维护一张常用城市对照表。更多见 时区指南。

## 小结

远程约时：先城市与时区，再日期，再本地时刻；工具把相对时间钉成绝对时刻，日历邀请里写 UTC 最稳。
