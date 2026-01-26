---
description: //ezspline 命令的文档
---

# 样条

{% embed url="https://youtu.be/dJXsPTB5NhU" %}
由 [eztaK](https://linktr.ee/eztak) 制作的视频教程
{% endembed %}

ezEdits 提供了一个广泛的界面，用于在 3D 空间中沿着一条一维插值路径放置和嵌入各种形状和结构。

路径由 WorldEdit 的凸选区（`//sel convex`）定义。使用长方体选区时，样条将是从 pos1 到 pos2 的直线。

所有子命令都在 <mark style="color:orange;">**`//ezspline`**</mark> 下\
其缩写/别名是 <mark style="color:orange;">**`//ezsp`**</mark>

***

## 子页面概览

* [**通用参数**](common-parameters.md)
  * 涵盖所有可用于**所有** `ezspline` 子命令的参数和标志。这些是：
    * [`<radii>`](common-parameters.md#radii)
    * [`[-p <kbParameters>]`](common-parameters.md#kb-parameters)
    * [`[-q <quality>]`](common-parameters.md#quality)
    * [`[-r <startingRoll>]`](common-parameters.md#roll)
    * [`[-s <stretchFactor>]`](common-parameters.md#stretch)
    * [`[-t <twistAngle>]`](common-parameters.md#twist)
    * [`[-n <normalMode>]`](common-parameters.md#normal-mode)
    * [`[-e <endMode>]`](common-parameters.md#end-style-e)
    * [`[-w <smoothblocks>]`](common-parameters.md#help-page)
* [**2D 样条形状**](2d-spline-shapes.md)
  * 涵盖 `//ezsp` 2d 子命令：
    * [`//ezsp 2d Circle (Ci) (//ezsp basic)`](2d-spline-shapes.md#circle)
    * [`//ezsp 2d Square (Sq)`](2d-spline-shapes.md#square)
    * [`//ezsp 2d Diamond (Di)`](2d-spline-shapes.md#diamond)
    * [`//ezsp 2d RoundedSquare (RS)`](2d-spline-shapes.md#rounded-square)
    * [`//ezsp 2d SuperCircle (SC)`](2d-spline-shapes.md#super-circle)
    * [`//ezsp 2d CirclesCircle (CC) (//ezsp rope)`](2d-spline-shapes.md#circles-circle)
    * [`//ezsp 2d Polygon (Po)`](2d-spline-shapes.md#polygon)
    * [`//ezsp 2d Rectangle (Re)`](2d-spline-shapes.md#rectangle)
    * [`//ezsp 2d Star (St)`](2d-spline-shapes.md#star)
    * [`//ezsp 2d Flower (Fl)`](2d-spline-shapes.md#flower)
* [**3D 样条形状**](3d-spline-shapes.md)
  * 涵盖以下子命令：
    * [`//ezsp 3d Beads`](3d-spline-shapes.md#beads)
    * [`//ezsp 3d Chainlink`](3d-spline-shapes.md#chainlink)
    * [`//ezsp 3d Cubes`](3d-spline-shapes.md#cubes)
    * [`//ezsp 3d Fishnet`](3d-spline-shapes.md#fishnet)
    * [`//ezsp 3d Oscillate`](3d-spline-shapes.md#oscillate)
    * [`//ezsp 3d Rings`](3d-spline-shapes.md#rings)
    * [`//ezsp 3d Scales`](3d-spline-shapes.md#scales)
    * [`//ezsp 3d Noodles`](3d-spline-shapes.md#noodles)
* [**高级样条形状**](advanced-spline-shapes.md)
  * 涵盖以下子命令：
    * [`//ezsp noise`](advanced-spline-shapes.md#noise)
    * [`//ezsp expression`](advanced-spline-shapes.md#expression)
    * [`//ezsp structure`](advanced-spline-shapes.md#structure)
