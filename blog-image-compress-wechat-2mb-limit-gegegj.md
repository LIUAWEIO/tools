# 公众号插图总提示超过 2MB，横图竖图压缩有什么差别？

**在网站上阅读：** [https://gegegj.com/blog/image-compress-wechat-2mb-limit](https://gegegj.com/blog/image-compress-wechat-2mb-limit)

**相关工具：** [打开工具页](https://gegegj.com/tool/image-compress)

## 2MB 卡的是文件体积，不是「看起来不大」

微信公众号正文插图常见约 2MB 单张上限（以平台当前规则为准）。横图 宽 2000px、JPEG 质量 90%，即使用眼不大，文件也可能 3～5MB；竖屏长图 宽 1080、高 6000px 的推文长图，像素总量巨大，只拉低质量而不缩尺寸，往往仍超限。

在 [图片压缩工具](https://gegegj.com/tool/image-compress) 批量上传，看每张压缩前后 KB/MB。JPG、WebP 适合照片；要透明底保留 PNG。仍超 2MB 时，应在 Figma、PS 或系统画图里把长边压到 1500～1920px 再上传压缩，而不是把质量滑到 10% 导致文字糊掉。

## 横图与竖图策略不同

横图（头图、配图）：优先限制宽度 900～1280px，再压缩。竖图（长图、海报切片）：按阅读宽度 1080px 切分段落，每段单独压，比一张 8000px 高图一次压更易过限也更易加载。

邮件附件、工单上传见 [附件超限](https://gegegj.com/blog/image-compress-attachment-and-listing)；电商主图列表慢也可先压再传。文内小码用 二维码生成器 导出适中 PNG，别嵌 3000px 大图。详见 [压缩指南](https://gegegj.com/blog/image-compress-guide) 与 [图片压缩教程](https://gegegj.com/blog/13-image-compress-gegegj)。

## 隐私与画质平衡

压缩在浏览器本地完成，不上传原图到服务器；涉密物料仍注意周围环境。批量多图可用 ZIP 下载，适合运营一次性整理素材。

## 小结

公众号出图：先缩边长、再选格式、再本地压一遍；横图控宽、长图分段。上传前预览，比发布后裂图再改稿省事。
