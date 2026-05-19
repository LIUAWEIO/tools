# 二维码和条形码：信息越多，点越密，扫码越挑环境

**在网站上阅读：** [https://gegegj.com/blog/longread-qr-and-barcode-symbols](https://gegegj.com/blog/longread-qr-and-barcode-symbols)

**相关工具：** [打开工具页](https://gegegj.com/tool/qrcode)

## 二维矩阵 versus 一条宽窄条

二维码在平面铺黑白模块，能塞纠错冗余；一维条码多在一条线上用条空宽度编码，常见于货架 SKU。

内容变长，矩阵必然更密；容错档位开得高，同样会更密，这是「抗脏」和「好扫」之间的硬权衡。

## 屏幕、铜版纸、金属牌：材质决定最小安全尺寸

发光屏和漫反射纸对对比度要求不同；圆角裁切、渐变底、贴层反光都会吃掉安全边。

## 活动报名、资产标签、店内 Wi-Fi：先问「是不是非要塞长文」

能短链就不要长 URL；长配置可先 [JSON 格式化工具](https://gegegj.com/tool/json) 做 json 在线解析，再决定适不适合进码。

## 生成器帮您对齐尺寸和批量导出

手工画码不现实；统一边长、批量 PNG，设计和印刷对文件更轻松。

## 「好看」过头时，转化率先掉

Logo 过大、留白不足、分辨率勉强及格，现场补救通常是重印而不是调亮度。

## NFC 分流一部分场景，可视码不会消失

弱网、小商户、一次性物料仍依赖「看得见摸得着」的码；协议再新，线下物料仍要实测。

## 读完可以先做的一件事

用 [二维码生成器](https://gegegj.com/tool/qrcode) 导出测试版，在目标光线和最旧那台手机上各扫三次；实操见 [二维码生成器教程](https://gegegj.com/blog/qrcode-generator-guide)。
