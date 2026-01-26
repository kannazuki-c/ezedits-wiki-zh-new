# 放置

## 概述

ezEdits 提供了多种方式来快速准确地放置剪贴板、原理图和基于表达式的形状，我们将其称为"结构"。

相关命令和笔刷（在版本 0.12.0 中引入）如下：

<table data-card-size="large" data-view="cards" data-full-width="false"><thead><tr><th>命令 / 笔刷</th><th>缩写</th><th>描述</th><th>语法</th><th>参数</th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><mark style="color:orange;"><strong><code>//ezplace</code></strong></mark></td><td><mark style="color:orange;"><strong><code>//ezpl</code></strong></mark></td><td>在<strong>玩家位置</strong>放置<strong>单个</strong>结构。</td><td><code>//ezplace</code> <a href="available-structures.md"><code>&#x3C;structure></code></a> <a href="primary+secondary-alignment.md"><code>[&#x3C;primary>][&#x3C;secondary>]</code></a></td><td>接受<a data-mention href="placement-parameters.md">放置参数</a>。</td><td></td></tr><tr><td><mark style="color:orange;"><strong><code>//ezbrush place</code></strong></mark></td><td><mark style="color:orange;"><strong><code>//ezbr pl</code></strong></mark></td><td>笔刷，在每个<strong>笔刷点击的目标处</strong>放置<strong>单个</strong>结构。</td><td><code>//ezbrush place</code> <a href="available-structures.md"><code>&#x3C;structure></code></a> <a href="primary+secondary-alignment.md"><code>[&#x3C;primary>] [&#x3C;secondary>]</code></a></td><td>接受<a data-mention href="placement-parameters.md">放置参数</a>。</td><td></td></tr><tr><td><mark style="color:orange;"><strong><code>//ezscatter</code></strong></mark></td><td><mark style="color:orange;"><strong><code>//ezsc</code></strong></mark></td><td>在<strong>已选中的区域内</strong>放置<strong>多个</strong>结构。</td><td><code>//ezscatter</code><a href="available-structures.md"><code>&#x3C;structure></code></a> <a href="primary+secondary-alignment.md"><code>[&#x3C;primary>] [&#x3C;secondary>]</code></a></td><td>接受<a data-mention href="placement-parameters.md">放置参数</a>和<a data-mention href="scatter-parameters.md">散布参数</a>。</td><td></td></tr><tr><td><mark style="color:orange;"><strong><code>//ezbrush scatter</code></strong></mark></td><td><mark style="color:orange;"><strong><code>//ezbr sc</code></strong></mark></td><td>笔刷，在每个<strong>笔刷点击的目标区域内</strong>放置<strong>多个</strong>结构。</td><td><code>//ezbrush scatter</code><a href="available-structures.md"><code>&#x3C;structure></code></a> <a href="primary+secondary-alignment.md"><code>[&#x3C;primary>] [&#x3C;secondary>]</code></a></td><td>接受<a data-mention href="placement-parameters.md">放置参数</a>和<a data-mention href="scatter-parameters.md">散布参数</a>。</td><td></td></tr><tr><td><mark style="color:orange;"><strong><code>//ezarray</code></strong></mark></td><td><mark style="color:orange;"><strong><code>//ezar</code></strong></mark></td><td>沿<strong>路径</strong>依次放置<strong>多个</strong>结构。</td><td><code>//ezarray</code><a href="available-structures.md"><code>&#x3C;structure></code></a> <a href="primary+secondary-alignment.md"><code>[&#x3C;primary>][&#x3C;secondary>]</code></a></td><td>接受<a data-mention href="placement-parameters.md">放置参数</a>和<a data-mention href="array-parameters.md">阵列参数</a>。</td><td></td></tr><tr><td><mark style="color:orange;"><strong><code>//ezbrush array</code></strong></mark></td><td><mark style="color:orange;"><strong><code>//ezbr ar</code></strong></mark></td><td>笔刷，沿<strong>笔刷笔画</strong>放置<strong>多个</strong>结构。</td><td><code>//ezbrush array</code><a href="available-structures.md"><code>&#x3C;structure></code></a> <a href="primary+secondary-alignment.md"><code>[&#x3C;primary>] [&#x3C;secondary>]</code></a></td><td>接受<a data-mention href="placement-parameters.md">放置参数</a>和<a data-mention href="array-parameters.md">阵列参数</a>。</td><td></td></tr></tbody></table>

所有六个命令都基于相同的底层放置方法。因此，所有六个命令共享相同的语法和参数。

{% hint style="info" %}
为了完整起见，还可以使用 ezspline 子命令 `//ezspline structure`（`//ezsp structure`）将结构或结构阵列嵌入到形状样条中。但是，结构不是被"放置"，而是被嵌入到样条路径中，这意味着[对齐设置](primary+secondary-alignment.md)和[放置参数](placement-parameters.md)不适用于该命令。因此它被记录在[样条页面](../spline/)上。
{% endhint %}

***

## 子页面结构

此放置wiki有多个子页面。下面你可以找到子页面的概览。

{% hint style="info" %}
我们建议更仔细地阅读[**主要+次要对齐**](primary+secondary-alignment.md)页面，因为它涵盖了工具的基本概念之一。其余章节可以作为参考资料，对于特定任务或深入了解工具功能很有用。
{% endhint %}

* [**可用结构**](available-structures.md)
  * 涵盖[`<structure>`](available-structures.md)参数（place/scatter/array（和ezspline结构）必需）。
* [**主要+次要对齐**](primary+secondary-alignment.md)
  * 涵盖[`[<primary>] [<secondary>]`](primary+secondary-alignment.md)参数（可用于place/scatter/array）和相应的标志：
    * [`[-j <snapDirections>]`](primary+secondary-alignment.md#snap-to-angles-j)
    * [`[-x]`](primary+secondary-alignment.md#perturb-secondary-x)
* [**放置参数**](placement-parameters.md)
  * 涵盖以下标志（可用于place/scatter/array）：
    * [`[-s <dimensions>]`](placement-parameters.md#dimensions-s)
    * [`[-o <sizeMultiplierRange>]`](placement-parameters.md#random-scaling-o)
    * [`[-c <orientationAngle>] [-k <orientationAxis>]`](placement-parameters.md#orientation-c-k)
    * [`[-f <randomFlipsAxes>]`](placement-parameters.md#random-flips-f)
    * [`[-r <randomRotationAxis>]`](placement-parameters.md#random-rotations-r)
    * [`[-a]`](placement-parameters.md#place-air-a)
* [**散布参数**](scatter-parameters.md)
  * 涵盖以下标志（仅适用于scatter）：
    * [`[-h <region>]`](scatter-parameters.md#scatter-region-h)
    * [`[-d <filterDirections>] [-e <filterThreshold>]`](scatter-parameters.md#directional-filter-d-e)
    * [`[-m <maskFilter>]`](scatter-parameters.md#mask-filter-m)
    * [`[-n <density>]`](scatter-parameters.md#density-n)
    * [`[-i <seed>]`](scatter-parameters.md#distribution-seed-i)
    * [`[-u <iterations>]`](scatter-parameters.md#uniformity-u)
    * [`[-l <coverPattern>]`](scatter-parameters.md#mask-cover-pattern-l)
    * [`[-t]`](scatter-parameters.md#trim-outside-selection-t)
* [**阵列参数**](array-parameters.md)
  * 涵盖以下标志（仅适用于array）：
    * [`[-g <gap>]`](array-parameters.md#distance-g)
    * [`[-y <maxOffset>]`](array-parameters.md#max-vertical-offset-y)
    * [`[-q <radiiMultiplier>]`](array-parameters.md#progressive-scaling-q)
    * [`[-p <kbParameters>]`](array-parameters.md#path-parameters-p)
    * [`[-n <normalMode>]`](array-parameters.md#spline-orientation-n)
    * [`[-b]`](array-parameters.md#snap-to-surfaces-b)

### 附加参数

* 可用于place/scatter/array：
  * [`[-w <smoothblocks>]`](../../smoothblocks/smoothblocks.md)&#x20;

<details>

<summary>这里是<em>相同的</em>标志<em>再次</em>出现，但按字母顺序排列：</summary>

* [`[-a]`](placement-parameters.md#place-air-a)
* [`[-b]`](array-parameters.md#snap-to-surfaces-b)
* [`[-c <orientationAngle>]`](placement-parameters.md#orientation-c-k)
* [`[-d <filterDirections>]`](scatter-parameters.md#directional-filter-d-e)
* [`[-e <filterThreshold>]`](scatter-parameters.md#directional-filter-d-e)
* [`[-f <randomFlipsAxes>]`](placement-parameters.md#random-flips-f)
* [`[-g <gap>]`](array-parameters.md#distance-g)
* [`[-h <region>]`](scatter-parameters.md#scatter-region-h)
* [`[-i <seed>]`](scatter-parameters.md#distribution-seed-i)
* [`[-j <restrictedAngles>]`](primary+secondary-alignment.md#snap-to-angles-j)
* [`[-k <orientationAxis>]`](placement-parameters.md#orientation-c-k)
* [`[-l <coverPattern>]`](scatter-parameters.md#mask-cover-pattern-l)
* [`[-m <maskFilter>]`](scatter-parameters.md#mask-filter-m)
* [`[-n <density>]`](scatter-parameters.md#density-n)
* [`[-n <normalMode>]`](array-parameters.md#spline-orientation-n)
* [`[-o <sizeMultiplierRange>]`](placement-parameters.md#random-scaling-o)
* [`[-p <kbParameters>]`](array-parameters.md#path-parameters-p)
* [`[-q <radiiMultiplier>]`](array-parameters.md#progressive-scaling-q)
* [`[-r <randomRotationAxis>]`](placement-parameters.md#random-rotations-r)
* [`[-s <dimensions>]`](placement-parameters.md#dimensions-s)
* [`[-t]`](scatter-parameters.md#trim-outside-selection-t)
* [`[-u <iterations>]`](scatter-parameters.md#uniformity-u)
* [`[-w <smoothblocks>]`](../../smoothblocks/smoothblocks.md)&#x20;
* [`[-x]`](primary+secondary-alignment.md#perturb-secondary-x)
* [`[-y <maxOffset>]`](array-parameters.md#max-vertical-offset-y)

</details>

***

{% hint style="warning" %}
服务器管理员注意：三个放置笔刷生成BlockDisplay实体（仅对使用其笔刷的玩家可见）以帮助可视化笔刷的[对齐](primary+secondary-alignment.md)。你可以在`config.yml`的`visualisations`下完全禁用可视化实体或更改其更新频率。

此外，命令`//ezdebug removeVisualiserEntities`将删除ezEdits在你的世界中生成的任何实体，以防它们出现bug且未被正确移除，这本不应该发生，但既然这样了。
{% endhint %}

***
