# 二维码能扫出来，点开却说链接过期，是码坏了吗？

**在网站上阅读：** [https://gegegj.com/blog/qrcode-scans-but-link-expired](https://gegegj.com/blog/qrcode-scans-but-link-expired)

**相关工具：** [打开工具页](https://gegegj.com/tool/qrcode)

## 扫得出 ≠ 链接永远有效

二维码只是把网址或文本编成黑白块。手机能识别说明图形、纠错、静区基本合格。点开404、提示过期、跳转登录页，多半是短链服务、活动下线、域名证书或后台配置问题。

用 [二维码生成器](https://gegegj.com/tool/qrcode) 生成时尽量用稳定域名；活动型链接要设有效期并在海报写清截止日期。扫不出见 [模糊光线](https://gegegj.com/blog/qrcode-scan-fail-blur-size-light)；印了就不能改链接见 [静态海报](https://gegegj.com/blog/qrcode-static-poster-vs-changing-link)。

## 排查顺序

换手机、换网络试；后台看短链点击日志；确认 HTTPS 证书未过期。中心 logo 过大见 [logo留白](https://gegegj.com/blog/qrcode-logo-center-quiet-zone)。

## 运营和技术的分工

技术：码图完好、纠错足够、静区足够。运营：短链有效期、落地页下架、活动下线。扫得出但404多半是后者。

活动结束改贴「已结束」新码，比在原海报上手写说明更靠谱；静态海报专题讨论链接常变。

测试用生产短链前，先扫内网或 staging，避免印出去才发现域名未备案。

用户投诉「扫不了」时，先让对方换手机、换光线，再查后台点击日志是否有记录。

## 使用提醒

本文围绕「二维码生成器」的一个常见问题展开，工具在浏览器本地处理数据，适合试算与沟通；签约、申报、诊疗请以官方口径为准。

涉及隐私的数据请先脱敏；公共电脑、录屏环境勿粘贴真实工资、病历、Token 或合同金额。

## 小结

把标题里的疑问拆开：先确认口径，再用对应工具试算；正式结果以合同、银行、税务、医院、学校规则为准。在浏览器本地运行，适合沟通与备忘。
