# 发邮件附图，压缩质量 85 和 70 差很多吗？一般设多少？

**在网站上阅读：** [https://gegegj.com/blog/image-compress-quality-85-or-70-email](https://gegegj.com/blog/image-compress-quality-85-or-70-email)

**相关工具：** [打开工具页](https://gegegj.com/tool/image-compress)

## 质量数字不是「清晰度百分比」

JPG 的 quality 是量化表取舍，85 与 70 的体积差往往比肉眼差别大：文字截图 85 已够，照片复杂区域 70 可能出现色块。

在 [图片压缩工具](https://gegegj.com/tool/image-compress) 同一张图各导出 85、70，对比文件大小和 100% 放大后的边缘；邮件限 10MB 时先限宽（如长边 1920）再调质量。

PNG 透明图别强行压 JPG，见 [透明底变黑](https://gegegj.com/blog/image-compress-png-transparent-background-black)。

## 和微信、附件场景

微信 2MB 限制见 [微信 2MB](https://gegegj.com/blog/image-compress-wechat-2mb-limit)；压完变大见 [体积变大](https://gegegj.com/blog/image-compress-file-size-increased-after)。

邮件附件与上架见 附件超限；。

## 不同场景的起手值

邮件附件限 10MB、原图 8MB：先试质量 80–85，仍超限再降到 70 或缩边长；截图类 PNG 转 JPG 往往比硬压 PNG 有效。

透明图标、Logo 优先 PNG，别为省体积压成满屏噪点；透明变黑见 PNG 透明底。

压完反而变大见 体积变大，多半是原图已高度压缩或格式选错。

微信 2MB 限制见 微信 2MB，和邮箱策略分开试。

## 批量发图时的顺序

先统一长边像素（如 1600px），再批量质量 85；顺序反了可能每张都模糊且仍超大。

多张图打 ZIP 发邮件，收件人手机解压后查看，单张仍建议控制在两三兆以内，避免邮箱拒收。

截图带文字，优先 PNG 或高质量 JPG；照片类再 aggressive 压到 70。

合同扫描件别压到字迹糊掉，法务可能拒收；见 附件与上架。

对比时把原图与压缩图并排 100% 放大看笔画，别只看缩略图觉得「差不多」。

## 使用提醒

本文只讨论标题里的一个具体场景，图片压缩工具 在浏览器本地计算或处理，适合自查与沟通；签约、报税、诊疗、签证请以主管机构或合同为准。

涉及隐私的数据请先脱敏；公共电脑、录屏环境勿粘贴真实工资、病历、Token 或合同金额。

## 小结

邮件附图起手：缩边长 → 质量 80–85 → 仍大再 70 或换 JPG；截图优先 PNG/适度 JPG。

正式印刷、医疗影像勿用网页压缩替代专业流程。
