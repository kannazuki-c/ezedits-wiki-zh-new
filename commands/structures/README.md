# 结构命令

## 概述

ezEdits 提供了多种快速放置剪贴板、建筑文件和基于表达式的形状的方法，这些都归类为"结构"。

相关的命令和笔刷（在 0.12.0 版本中引入）包括：

<table data-column-title-hidden data-view="cards" data-full-width="false"><thead><tr><th>Command / Brush</th><th>Description</th></tr></thead><tbody><tr><td><a href="./#ezplace"><code>//ezplace</code> (<code>//ezpl</code>)</a></td><td>在<strong>玩家位置</strong>放置<strong>单个</strong>结构。</td></tr><tr><td><a href="./#ezscatter"><code>//ezscatter</code> (<code>//ezsc</code>)</a></td><td>在<strong>选定区域</strong>内放置<strong>多个</strong>结构。</td></tr><tr><td><a href="./#ezarray"><code>//ezarray</code> (<code>//ezar</code>)</a></td><td><strong>沿路径</strong>依次放置<strong>多个</strong>结构。</td></tr><tr><td><a href="./#ezbrush-place"><code>//ezbrush place</code> (<code>//ezbr pl</code>)</a></td><td>在每次<strong>笔刷点击的目标</strong>位置放置<strong>单个</strong>结构的笔刷。</td></tr><tr><td><a href="./#ezbrush-scatter"><code>//ezbrush scatter (//ezbr sc)</code></a></td><td>在每次<strong>笔刷点击的目标</strong>区域内放置<strong>多个</strong>结构的笔刷。</td></tr><tr><td><a href="./#ezbrush-array"><code>//ezbrush array</code> (<code>//ezbr ar</code>)</a></td><td>沿<strong>笔刷笔画</strong>放置<strong>多个</strong>结构的笔刷。</td></tr></tbody></table>

这六个命令都基于相同的底层放置方法。因此，这六个命令共享相同的语法和参数。

{% hint style="info" %}
为了完整性说明，也可以使用 ezspline 子命令 `//ezspline structure` (`//ezsp structure`) 将结构或结构阵列嵌入到成形样条中。但是，这些结构与其说是"放置"的，不如说是嵌入到样条路径中的，这意味着[对齐设置](primary+secondary-alignment.md)和[放置参数](placement-parameters.md)不适用于该命令。这就是为什么它在[样条页面](../spline/)而不是这里记录的原因。
{% endhint %}

***

## 命令

本节列出了所有结构命令的语法，并附有相应章节的链接。

***

### `//ezplace`

别名：`//ezpl`

在**玩家位置**放置**单个**结构。

`//ezplace` [`<structure>`](available-structures.md) [`[<primary>] [<secondary>]`](primary+secondary-alignment.md) [`[-s <dimensions>]`](placement-parameters.md#controlling-dimensions-s-less-than-dimensions-greater-than) [`[-o <sizeMultiplierRange>]`](placement-parameters.md#random-scaling-o-less-than-sizemultiplierrange-greater-than) [`[-c <orientationAngle>] [-k <orientationAxis>]`](placement-parameters.md#orientation-advanced-k-less-than-orientationaxis-greater-than-and-c-less-than-orientationangle-great) [`[-f <randomFlipsAxes>]`](placement-parameters.md#random-flips-f-less-than-randomflipsaxes-greater-than) [`[-r <randomRotationAxis>]`](placement-parameters.md#random-90-rotations-r-less-than-randomrotationaxis-greater-than) [`[-a]`](placement-parameters.md#place-air-a)

### `//ezbrush place`

别名：`//ezbr pl`

在每次**笔刷点击的目标位置**放置**单个**结构的笔刷。

`//ezbrush place` [`<structure>`](available-structures.md) [`[<primary>] [<secondary>]`](primary+secondary-alignment.md) [`[-s <dimensions>]`](./#controlling-dimensions-s-less-than-dimensions-greater-than) [`[-o <sizeMultiplierRange>]`](./#random-scaling-o-less-than-sizemultiplierrange-greater-than) [`[-c <orientationAngle>] [-k <orientationAxis>]`](./#orientation-advanced-k-less-than-orientationaxis-greater-than-and-c-less-than-orientationangle-great) [`[-f <randomFlipsAxes>]`](./#random-flips-f-less-than-randomflipsaxes-greater-than) [`[-r <randomRotationAxis>]`](placement-parameters.md#random-90-rotations-r-less-than-randomrotationaxis-greater-than) [`[-a]`](placement-parameters.md#place-air-a)

***

### `//ezscatter`

别名：`//ezsc`

在**选定区域**内放置**多个**结构。

`//ezscatter` [`<structure>`](available-structures.md) [`[<primary>] [<secondary>]`](primary+secondary-alignment.md) [`[-s <dimensions>]`](./#controlling-dimensions-s-less-than-dimensions-greater-than) [`[-o <sizeMultiplierRange>]`](./#random-scaling-o-less-than-sizemultiplierrange-greater-than) [`[-c <orientationAngle>] [-k <orientationAxis>]`](./#orientation-advanced-k-less-than-orientationaxis-greater-than-and-c-less-than-orientationangle-great) [`[-f <randomFlipsAxes>]`](./#random-flips-f-less-than-randomflipsaxes-greater-than) [`[-r <randomRotationAxis>]`](placement-parameters.md#random-90-rotations-r-less-than-randomrotationaxis-greater-than) [`[-h <region>]`](scatter-parameters.md#scatter-region-h-less-than-region-greater-than) [`[-d <filterDirections>] [-e <filterThreshold>]`](scatter-parameters.md#directional-filter-d-less-than-directions-greater-than-and-e-less-than-threshold-greater-than) [`[-m <maskFilter>]`](scatter-parameters.md#mask-filter-m-less-than-mask-greater-than) [`[-n <density>]`](scatter-parameters.md#density-n-less-than-density-greater-than) [`[-i <seed>]`](scatter-parameters.md#distribution-seed-i-less-than-seed-greater-than) [`[-u <iterations>]`](scatter-parameters.md#uniformity-u-less-than-iterations-greater-than) [`[-l <coverPattern>]`](scatter-parameters.md#mask-cover-block-b-less-than-pattern-greater-than) [`[-a]`](placement-parameters.md#place-air-a) [`[-t]`](scatter-parameters.md#cut-off-outside-the-selection-c)&#x20;

### `//ezbrush scatter`

别名：`//ezbr sc`

在每次**笔刷点击目标**的区域内放置**多个**结构的笔刷。

`//ezbrush scatter` [`<structure>`](available-structures.md) [`[<primary>] [<secondary>]`](primary+secondary-alignment.md) [`[-s <dimensions>]`](./#controlling-dimensions-s-less-than-dimensions-greater-than) [`[-o <sizeMultiplierRange>]`](./#random-scaling-o-less-than-sizemultiplierrange-greater-than) [`[-c <orientationAngle>] [-k <orientationAxis>]`](./#orientation-advanced-k-less-than-orientationaxis-greater-than-and-c-less-than-orientationangle-great) [`[-f <randomFlipsAxes>]`](./#random-flips-f-less-than-randomflipsaxes-greater-than) [`[-r <randomRotationAxis>]`](placement-parameters.md#random-90-rotations-r-less-than-randomrotationaxis-greater-than) [`[-h <region>]`](scatter-parameters.md#scatter-region-h-less-than-region-greater-than) [`[-d <filterDirections>] [-e <filterThreshold>]`](scatter-parameters.md#directional-filter-d-less-than-directions-greater-than-and-e-less-than-threshold-greater-than) [`[-m <maskFilter>]`](scatter-parameters.md#mask-filter-m-less-than-mask-greater-than) [`[-n <density>]`](scatter-parameters.md#density-n-less-than-density-greater-than) [`[-i <seed>]`](scatter-parameters.md#distribution-seed-i-less-than-seed-greater-than) [`[-u <iterations>]`](scatter-parameters.md#uniformity-u-less-than-iterations-greater-than) [`[-l <coverPattern>]`](scatter-parameters.md#mask-cover-block-b-less-than-pattern-greater-than) [`[-a]`](placement-parameters.md#place-air-a) [`[-t]`](scatter-parameters.md#cut-off-outside-the-selection-c)&#x20;

***

### `//ezarray`

别名：`//ezar`

沿路径**依次**放置**多个**结构。

`//ezarray` [`<structure>`](available-structures.md) [`[<primary>] [<secondary>]`](primary+secondary-alignment.md) [`[-s <dimensions>]`](placement-parameters.md#controlling-dimensions-s-less-than-dimensions-greater-than) [`[-o <sizeMultiplierRange>]`](placement-parameters.md#random-scaling-o-less-than-sizemultiplierrange-greater-than) [`[-c <orientationAngle>] [-k <orientationAxis>]`](placement-parameters.md#orientation-advanced-k-less-than-orientationaxis-greater-than-and-c-less-than-orientationangle-great) [`[-f <randomFlipsAxes>]`](placement-parameters.md#random-flips-f-less-than-randomflipsaxes-greater-than) [`[-r <randomRotationAxis>]`](placement-parameters.md#random-90-rotations-r-less-than-randomrotationaxis-greater-than) [`[-g <gap>]`](array-parameters.md#distance-g-less-than-gap-greater-than) [`[-q <radiiMultiplier>]`](array-parameters.md#progressive-scaling-q-less-than-radii-greater-than) [`[-p <kbParameters>]`](array-parameters.md#path-parameters-p-less-than-kbparameters-greater-than) [`[-n <normalMode>]`](array-parameters.md#spline-orientation-n-less-than-normalmode-greater-than) [`[-a]`](placement-parameters.md#place-air-a) [`[-b]`](array-parameters.md#snap-placements-to-surfaces-b)

### `//ezbrush array`

别名：`//ezbr ar`

沿着**笔刷笔画**放置**多个**结构的笔刷。

`//ezbrush array` [`<structure>`](available-structures.md) [`[<primary>] [<secondary>]`](primary+secondary-alignment.md) [`[-s <dimensions>]`](placement-parameters.md#controlling-dimensions-s-less-than-dimensions-greater-than) [`[-o <sizeMultiplierRange>]`](placement-parameters.md#random-scaling-o-less-than-sizemultiplierrange-greater-than) [`[-c <orientationAngle>] [-k <orientationAxis>]`](placement-parameters.md#orientation-advanced-k-less-than-orientationaxis-greater-than-and-c-less-than-orientationangle-great) [`[-f <randomFlipsAxes>]`](placement-parameters.md#random-flips-f-less-than-randomflipsaxes-greater-than) [`[-r <randomRotationAxis>]`](placement-parameters.md#random-90-rotations-r-less-than-randomrotationaxis-greater-than) [`[-g <gap>]`](array-parameters.md#distance-g-less-than-gap-greater-than) [`[-q <radiiMultiplier>]`](array-parameters.md#progressive-scaling-q-less-than-radii-greater-than) [`[-p <kbParameters>]`](array-parameters.md#path-parameters-p-less-than-kbparameters-greater-than) [`[-n <normalMode>]`](array-parameters.md#spline-orientation-n-less-than-normalmode-greater-than) [`[-a]`](placement-parameters.md#place-air-a) [`[-b]`](array-parameters.md#snap-placements-to-surfaces-b)

***

{% hint style="info" %}
服务器管理员注意：三种结构笔刷会生成 BlockDisplay 实体（仅对使用笔刷的玩家可见）以帮助可视化笔刷的[对齐方式](primary+secondary-alignment.md)。您可以在 `config.yml` 的 `visualisations` 部分完全禁用可视化实体或更改其更新频率。

此外，命令 `//ezdebug removeVisualiserEntities` 将从您的世界中移除所有由 ezEdits 生成的实体，以防它们因某种原因出现问题而未能正确消失，虽然这种情况不应该发生，但以防万一。
{% endhint %}

***

## 子页面结构

此结构 Wiki 包含多个子页面。以下是子页面概览。

{% hint style="info" %}
我们建议仔细阅读 [**Primary+Secondary Alignment**](primary+secondary-alignment.md) 页面，因为它涵盖了这些工具的基本概念之一。其余章节可以作为参考资料，用于特定任务或深入了解工具的功能。
{% endhint %}

* [**Available Structures**](available-structures.md)
  * 涵盖 [`<structure>`](available-structures.md) 参数(place/scatter/array(以及 ezspline structure)所必需)。
* [**Primary+Secondary Alignment**](primary+secondary-alignment.md)
  * 涵盖 [`[<primary>] [<secondary>]`](primary+secondary-alignment.md) 参数(可用于 place/scatter/array)以及相关标志:
    * [`[-j <snapDirections>]`](primary+secondary-alignment.md#snap-to-angles-j-less-than-anglesset-greater-than)
    * [`[-x]`](primary+secondary-alignment.md#perturb-secondary-x)
* [**Placement Parameters**](placement-parameters.md)
  * 涵盖以下标志(可用于 place/scatter/array):
    * [`[-s <dimensions>]`](placement-parameters.md#controlling-dimensions-s-less-than-dimensions-greater-than)
    * [`[-o <sizeMultiplierRange>]`](placement-parameters.md#random-scaling-o-less-than-sizemultiplierrange-greater-than)
    * [`[-c <orientationAngle>] [-k <orientationAxis>]`](placement-parameters.md#orientation-advanced-k-less-than-orientationaxis-greater-than-and-c-less-than-orientationangle-great)
    * [`[-f <randomFlipsAxes>]`](placement-parameters.md#random-flips-f-less-than-randomflipsaxes-greater-than)
    * [`[-r <randomRotationAxis>]`](placement-parameters.md#random-90-rotations-r-less-than-randomrotationaxis-greater-than)
    * [`[-a]`](placement-parameters.md#place-air-a)
* [**Scatter Parameters**](scatter-parameters.md)
  * 涵盖以下标志(仅可用于 scatter):
    * [`[-h <region>]`](scatter-parameters.md#scatter-region-h-less-than-region-greater-than)
    * [`[-d <filterDirections>] [-e <filterThreshold>]`](scatter-parameters.md#directional-filter-d-less-than-directions-greater-than-and-e-less-than-threshold-greater-than)
    * [`[-m <maskFilter>]`](scatter-parameters.md#mask-filter-m-less-than-mask-greater-than)
    * [`[-n <density>]`](scatter-parameters.md#density-n-less-than-density-greater-than)
    * [`[-i <seed>]`](scatter-parameters.md#distribution-seed-i-less-than-seed-greater-than)
    * [`[-u <iterations>]`](scatter-parameters.md#uniformity-u-less-than-iterations-greater-than)
    * [`[-l <coverPattern>]`](scatter-parameters.md#mask-cover-block-b-less-than-pattern-greater-than)
    * [`[-t]`](scatter-parameters.md#trim-outside-selection-t)
* [**Array Parameters**](array-parameters.md)
  * 涵盖以下标志(仅可用于 array):
    * [`[-g <gap>]`](array-parameters.md#distance-g-less-than-gap-greater-than)
    * [`[-q <radiiMultiplier>]`](array-parameters.md#progressive-scaling-q-less-than-radii-greater-than)
    * [`[-p <kbParameters>]`](array-parameters.md#path-parameters-p-less-than-kbparameters-greater-than)
    * [`[-n <normalMode>]`](array-parameters.md#spline-orientation-n-less-than-normalmode-greater-than)
    * [`[-b]`](array-parameters.md#snap-placements-to-surfaces-b)

<details>

<summary>以下是<em>相同</em>的标志，但按<em>字母顺序</em>排列：</summary>

* [`[-a]`](placement-parameters.md#place-air-a)
* [`[-b]`](array-parameters.md#snap-placements-to-surfaces-b)
* [`[-c <orientationAngle>]` ](placement-parameters.md#orientation-advanced-k-less-than-orientationaxis-greater-than-and-c-less-than-orientationangle-great)
* [`[-d <filterDirections>]`](scatter-parameters.md#directional-filter-d-less-than-directions-greater-than-and-e-less-than-threshold-greater-than)
* [`[-e <filterThreshold>]`](scatter-parameters.md#directional-filter-d-less-than-directions-greater-than-and-e-less-than-threshold-greater-than)
* [`[-f <randomFlipsAxes>]`](placement-parameters.md#random-flips-f-less-than-randomflipsaxes-greater-than)
* [`[-g <gap>]`](array-parameters.md#distance-g-less-than-gap-greater-than)
* [`[-h <region>]`](scatter-parameters.md#scatter-region-h-less-than-region-greater-than)
* [`[-i <seed>]`](scatter-parameters.md#distribution-seed-i-less-than-seed-greater-than)
* [`[-j <restrictedAngles>]`](primary+secondary-alignment.md#snap-to-angles-j-less-than-anglesset-greater-than)
* [`[-k <orientationAxis>]`](placement-parameters.md#orientation-advanced-k-less-than-orientationaxis-greater-than-and-c-less-than-orientationangle-great)
* [`[-l <coverPattern>]`](scatter-parameters.md#mask-cover-block-b-less-than-pattern-greater-than)
* [`[-m <maskFilter>]`](scatter-parameters.md#mask-filter-m-less-than-mask-greater-than)
* [`[-n <density>]`](scatter-parameters.md#density-n-less-than-density-greater-than)
* [`[-n <normalMode>]`](array-parameters.md#spline-orientation-n-less-than-normalmode-greater-than)
* [`[-o <sizeMultiplierRange>]`](placement-parameters.md#random-scaling-o-less-than-sizemultiplierrange-greater-than)
* [`[-p <kbParameters>]`](array-parameters.md#path-parameters-p-less-than-kbparameters-greater-than)
* [`[-q <radiiMultiplier>]`](array-parameters.md#progressive-scaling-q-less-than-radii-greater-than)
* [`[-r <randomRotationAxis>]`](placement-parameters.md#random-90-rotations-r-less-than-randomrotationaxis-greater-than)
* [`[-s <dimensions>]`](placement-parameters.md#controlling-dimensions-s-less-than-dimensions-greater-than)
* [`[-t]`](scatter-parameters.md#trim-outside-selection-t)
* [`[-u <iterations>]`](scatter-parameters.md#uniformity-u-less-than-iterations-greater-than)&#x20;
* [`[-x]`](primary+secondary-alignment.md#perturb-secondary-x)

</details>

***
