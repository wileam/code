title: iphone6屏幕揭秘
date: 2014-09-14 19:47:52
category:
tags:
- translate
- mobile
---

iPhone6发布了，纳尼？又是一个新尺寸，苦逼前端工又要加班了呢。看到一篇很好的关于iPhone 6 屏幕显示的[文章](http://www.paintcodeapp.com/news/iphone-6-screens-demystified)，于是翻译了一下。

访问：http://wileam.com/iphone-6-screen-cn/ 查看。

图较多，而且大多是svg矢量图，在博客里排版比较麻烦，于是单独做了上面这个站点。这里是翻译原文的中英文对照，欢迎批评指正。

<!-- more -->

---

# iPhone 6 Screens Demystified
# iPhone 6 屏幕揭秘

Few days ago, Apple introduced iPhone 6 Plus. The new iPhone substantially changes the way graphics are rendered on screen. We've made an infographic to demystify this.
几天前，Apple发布了iPhone 6 Plus. 新的iPhone大幅改变了图像在屏幕上渲染的方式。我们做了一个图表进行详细分析。

## Point
## 点

At the beginning, coordinates of all drawings are specified in points.
最初，所有图像的坐标都是用点的方式确定的。

Points are abstract units, they only make sense in this mathematical coordinate space.
点是绝对单位，他们只在数学的坐标空间里有意义。

In the original iPhone, points corresponded perfectly to actual pixels on screen, but this is no longer true.
在最初的iPhone上，点和实际屏幕的像素是完全一致的，但现在不再是这样了。

## Rendered Pixels
## 渲染像素

Point-based drawings are rendered into pixels. This process is known as rasterization.
以点为基础的图像渲染成为像素，这个过程就是光栅化（rasterization）。

Point coordinates are multiplied by scale factor to get pixel coordinates. Higher scale factors result in higher level of detail.
点坐标乘以一定的比例系数得到相应的像素坐标。更高的比例系数可以得到更好的细节呈现。

Typical scale factors are 1×, 2× and 3×.
典型的比例系数有1倍，2倍和3倍。

## Physical Pixels
## 物理像素

iPhone 6 Plus has screen with lower pixel resolution than the image rendered in previous step.
iPhone 6 Plus的屏幕像素分辨率比之前步骤渲染的图像分辨率低。

Before the image can be displayed on the screen, it must be downsampled (resized) to lower pixel resolution.
在图像显示在屏幕之前，图像必须重新调整大小到更低的像素分辨率。

## Physical Device
## 物理设备

The last step is to show the computed pixels on the physical screen.
最后一步是将计算的像素显示在物理屏幕上。

Every screen has pixels-per-inch (PPI) characteristic. This number tells you how many pixels fit into one inch and thus how large the pixels appear in the real world.
每一个屏幕都有一个每英寸像素(PPI)的特性。这个数字告诉你一英寸显示多少像素，也就是一像素在真实世界里显示的大小。

## Points
## 点

The content is defined mathematically using point coordinates.
内容是按照数学上的点坐标来定义的。

## Rendered Pixels
## 渲染像素

Content is rendered to pixels using scale factor. This process is called rasterization.
内容用比例系数渲染成像素，这个过程叫做光栅化（rasterization）。

## Physical Pixels
## 物理像素

iPhone 6 Plus downsamples the rendered image before displaying it on screen.
iPhone 6 Plus 在显示在屏幕上之前缩小了已渲染的图像。

## Physical Device

Rasterized drawings are displayed on the physical devices.
光栅化之后的图像显示在物理设备上。

## Line rendering
## 一根线的渲染

To demonstrate different rendering of pixels on various devices, we compare how 1-point wide line is rendered on
为了说明多种设备的不同像素渲染情况，我们比较了一个一像素宽的线是怎样渲染的：

- Original iPhone - without retina display. Scaling factor is 1.
- iPhone 5 - with Retina display, scaling factor is 2.
- iPhone 6 Plus - with Retina display HD. Scaling factor is 3 and the image is afterwards downscaled from rendered 2208 × 1242 pixels to 1920 × 1080 pixels.


- 最初的iPhone - 没有高清屏，比例系数是1。
- iPhone 5 - 有高清屏，比例系数是2。
- iPhone 6 Plus - 超高清屏（Retina display HD）。比例系数是3，并且图像会先渲染为2208 × 1242像素然后缩小为1920 × 1080像素。

The downscaling ratio is 1920 / 2208 = 1080 / 1242 = 20 / 23. That means every 23 pixels from the original render have to be mapped to 20 physical pixels. In other words the image is scaled down to approximately 87% of its original size.
缩小的比例是1920 / 2208 = 1080 / 1242 = 20 / 23. 这意味着最初渲染的每23像素会分布到20物理像素中。换句话说图像会缩小为大约原尺寸的87%。