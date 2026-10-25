LONGYI YAN — 个人作品集网站

1. 文件结构
index.html：首页，PDF 第 1、3 页
fineart.html：Fine Art，PDF 第 4–20 页
rubika.html：Rubika Exchange，PDF 第 21–53 页
suichu.html：Sui Chu Unique Realm，PDF 第 54–61 页
cv.html：简历，PDF 第 2 页
assets/images/：从原 PDF 提取的图片，可直接预览，也可替换成自己的高清原图
image-map.csv：图片对应 PDF 页码、文件名、原图尺寸
PDF 第 62 页是结束封底，未重复放入内容页。

2. 本地使用
解压完整文件夹后双击 index.html。无需 npm、框架、网络字体或构建。
必须保留 assets 文件夹。不能只上传五个 HTML 而遗漏图片。

3. 替换图片
在 HTML 中搜索“图片替换位置”，对应注释紧挨 SVG 的 <image> 元素。
方案 A：保持相同文件名、格式及比例，覆盖 assets/images 中相应图片。
方案 B：修改该元素的 xlink:href，例如 assets/images/my-painting.jpg。
每张图片的原始像素尺寸见 image-map.csv。为完整还原，建议使用相同宽高比。
注意：有些原 PDF 页本身已经是整页合成图，这些页面的图片替换槽对应整张排版图，
不是其中的单幅作品。替换时应提供完整排版图；图中已有文字无法单独编辑。
其他页面的图片槽与原 PDF 内的独立图片对应，遮罩和变换保留不变。

4. 文字与版式
使用内联 SVG 保留原 PDF 的字形、线条、裁切、叠图和位置；没有把整个网站作为 PDF 嵌入。
五个文件都是标准 HTML，导航、页面索引和页脚为普通可编辑 HTML。
为避免缺失字体和乱码，原排版文字使用 SVG 字形轮廓，不能像段落文字一样直接改写。
需要重写项目介绍时，可在 figure 前后添加普通 HTML 段落；若要修改原页文字，
应在源排版文件中修改后替换相应图形，或进一步将该页面重做为语义化 HTML。
CV 页另提供可复制的纯文字版本。PDF 自带的拼写和内容差异原样保留。
保留横版比例，小屏会整体缩小，可用浏览器缩放查看细节；不是重新排列的移动端设计。
站点无 JavaScript、追踪器、外部 CDN 或第三方依赖。
原 PDF 的联系方式被保留，请发布前确认这些信息可公开。

5. 发布到 GitHub Pages
创建仓库，将五个 HTML、assets、image-map.csv 和 .nojekyll 上传到仓库根目录。
进入 Settings → Pages → Build and deployment：
Source 选择 Deploy from a branch；Branch 选择 main；文件夹选择 / (root)，保存。
等待 GitHub 部署完成，再打开 Pages 显示的网站地址。
如果仓库名为 用户名.github.io，网址为 https://用户名.github.io/；
普通仓库则为 https://用户名.github.io/仓库名/。
文件名区分大小写；请使用本包内的小写名称。
本次提供源代码和部署说明，未登录或修改你的 GitHub 账号。
