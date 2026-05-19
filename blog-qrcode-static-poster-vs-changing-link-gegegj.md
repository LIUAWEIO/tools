# 活动链接老在变，已经印出去的二维码要不要全部重印？

**在网站上阅读：** [https://gegegj.com/blog/qrcode-static-poster-vs-changing-link](https://gegegj.com/blog/qrcode-static-poster-vs-changing-link)

**相关工具：** [打开工具页](https://gegegj.com/tool/qrcode)

## 印出去的图案，不会自己「长」出新网址

常见二维码（QR）把一段文本——多半是 https 链接——编成黑白模块。印刷后图案固定，扫出来永远是当初那段字。运营在后台把活动从 `/spring` 改到 `/summer`，旧海报上的码仍指向 spring，除非当初印的是短链域名，由短链服务在云端改跳转目标。

举例：直接印 `https://gegegj.com/event/2025-spring`，改路径必须重印。印 `https://t.example/abc`，在短链后台把 abc 目标改成新页，同一张码可继续用——但依赖第三方服务可用性与备案政策。新码用 [二维码生成器](https://gegegj.com/tool/qrcode) 生成，务必手机实地扫一遍再批量印刷。

## 什么时候值得重印，什么时候用短链

线下量小、改一次活动：重印成本可能更低，还能换设计。量大、灯箱、门店立牌：上线短链+固定入口码更常见。注意短链过期、账号欠费、域名被封等风险，活动结束可保留跳转说明页而非 404。

印刷留白与分辨率见 [印刷留白](https://gegegj.com/blog/qrcode-print-bleed-safe-area)；Wi-Fi、电子名片内容宜短，见 [Wi-Fi 与 vCard](https://gegegj.com/blog/qrcode-wifi-and-vcard)。条码物料另见 [二维码长文](https://gegegj.com/blog/longread-qr-and-barcode-symbols) 与 生成器教程。

## 和图片体积、落地页体验

海报高清大图可先 压缩图片 再拼版，避免扫码区被裁切或文件过大传不上印刷厂系统。落地页若返回 JSON 配置给前端渲染，整理样例可用 JSON 格式化工具 校验后再上线。

## 小结

链接常换：短链固定入口，或接受重印；静态码不会随后台自动更新。出码后实地扫码测试，比只看预览可靠。
