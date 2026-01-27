# 噪声详解

噪声对于从未深入了解过它的人来说可能是一个复杂的话题，但用最简单的术语来说，噪声是一种从某些输入（通常是 X、Y、Z 坐标）获取值的方法。

你最熟悉噪声的地方可能是 Minecraft 的地形生成。在世界的每个点上，多个噪声函数组合在一起，以确定是否应该放置方块，如果是，应该放置哪个方块。

这基本上就是我们在 ezEdits 中所做的，使用噪声来生成形状、地形和纹理。

在插件中，你会发现几种噪声类型，每种都有不同的特征，其中 Cellular 特别提供了许多可以自定义的额外参数。

使用噪声的众多功能包括：

* `//eznoisegen ...` - _Noisegen 命令_
* `#eznoisemask` - _蒙版_
* `//ezbrush gradient ...` - _笔刷_

_ezEdits 中的噪声基于 FastNoiseLite 的修改版本，因此我们强烈推荐使用此网站来实验噪声参数：_ [_http://auburn.github.io/FastNoiseLite/_](http://auburn.github.io/FastNoiseLite/)

## 噪声参数

每个参数和许多值也有简写形式，例如用 "ft" 代替 "FractalType" 或用 "Si" 代替 "OpenSimplex2"。只要可能，简写形式将显示在括号中。\
<mark style="color:red;">`红色 = 参数`</mark> <mark style="color:purple;">`紫色 = 值`</mark>

### 噪声类型

<details>

<summary>设置噪声类型<br></summary>

设置要使用的噪声类型。这是任何噪声的起点，格式为 `Noise()`，例如 `Perlin()`，所有其他参数将放在括号之间。

* <mark style="color:purple;">`Perlin (Pe)`</mark>
* <mark style="color:purple;">`OpenSimplex2 (Si)`</mark>
* <mark style="color:purple;">`OpenSimplex2S (Sm)`</mark>
* <mark style="color:purple;">`Value (Va)`</mark>
* <mark style="color:purple;">`ValueCubic (VC)`</mark>
* <mark style="color:purple;">`White (Wh)`</mark>
* <mark style="color:purple;">`Cellular (Ce)`</mark>
* <mark style="color:purple;">`Shard (Sh)`</mark>

</details>

### 基本噪声参数

<details>

<summary>基本噪声参数</summary>

* <mark style="color:red;">`Seed (s)`</mark>\
  设置噪声的种子值。-1 或无值将产生随机噪声种子。
* <mark style="color:red;">`Frequency (f)`</mark>\
  设置噪声的频率。较高的频率将导致更陡峭的噪声,较低的值将导致更平滑的噪声。
* <mark style="color:red;">`Inverted (i)`</mark>\
  是否反转噪声值。默认为 false。
  * <mark style="color:purple;">`True`</mark>
  * <mark style="color:purple;">`False`</mark>
* <mark style="color:red;">`ValueMapping (m)`</mark>\
  是否忽略或覆盖值映射。默认情况下,噪声采样映射在 0 和 1 之间。
  * <mark style="color:purple;">`Default (Def)`</mark>
  * <mark style="color:purple;">`None (No)`</mark>
  * <mark style="color:purple;">`Override (OR)`</mark>\
    **如果被覆盖:**
    * <mark style="color:red;">`LowerBound (l)`</mark>
    * <mark style="color:red;">`UpperBound (u)`</mark>
* <mark style="color:red;">`XScaling (x)`</mark>\
  可用于拉伸或压缩 X 轴。
* <mark style="color:red;">`YScaling (y)`</mark>\
  使用 3D 噪声时,可用于拉伸或压缩 Y 轴。
* <mark style="color:red;">`ZScaling (z)`</mark>\
  可用于拉伸或压缩 Z 轴。

</details>

### Cellular Noise Parameters

<details>

<summary><strong>Additional Cellular Noise Parameters</strong></summary>

* <mark style="color:red;">`CellularJitterModifier (cJ)`</mark>\

通常为 `0..1.0`\

控制细胞噪声节点的随机抖动或分布,0 表示完美网格,1 表示最大"随机",不重叠。大于 1 的值将开始与相邻节点重叠。

* <mark style="color:red;">`CellularDistanceFunction (cD)`</mark>\

控制用于确定每个点到其节点的距离值的数学方法。

* <mark style="color:purple;">`Euclidean (e)`</mark>

* <mark style="color:purple;">`EuclideanSq (sq)`</mark>

* <mark style="color:purple;">`Manhattan (man)`</mark>

* <mark style="color:purple;">`Hybrid (h)`</mark>

* <mark style="color:purple;">`Minkovski1 (m1)`</mark>

* <mark style="color:purple;">`Minkowvki4 (m4)`</mark>

* <mark style="color:purple;">`Minkowski99 (m99)`</mark>

* <mark style="color:purple;">`Rounded (r)`</mark>

* <mark style="color:red;">`CellularReturnType (cR)`</mark>\

控制距离值在返回前如何被修改。\

所有 Distance2\* 值指的是第二近的节点而不是最近的节点。

* <mark style="color:purple;">`CellValue (cell)`</mark>

* <mark style="color:purple;">`Distance (1)`</mark>

* <mark style="color:purple;">`DistanceSquared (sq)`</mark>

* <mark style="color:purple;">`DistanceInverse (inv)`</mark>

* <mark style="color:purple;">`DistanceLog (log)`</mark>

* <mark style="color:purple;">`DistanceExp (exp)`</mark>

* <mark style="color:purple;">`Distance2 (2)`</mark>

* <mark style="color:purple;">`Distance2Add (2add)`</mark>

* <mark style="color:purple;">`Distance2Add (2sub)`</mark>

* <mark style="color:purple;">`Distance2Add (2mul)`</mark>

* <mark style="color:purple;">`Distance2Add (2div)`</mark>

* <mark style="color:purple;">`Distance2Sq (2sq)`</mark>

* <mark style="color:purple;">`Distance2Inv (2inv)`</mark>

* <mark style="color:purple;">`Distance2Log (2log)`</mark>

* <mark style="color:purple;">`Distance2Exp (2exp)`</mark>

* <mark style="color:purple;">`Edge (e)`</mark>

* <mark style="color:purple;">`Rounded (r)`</mark>

* <mark style="color:purple;">`NoiseLookup (n)`</mark>\

**额外的噪声查找参数:**

* <mark style="color:red;">`CellularNoiseLookup (cN)`</mark>\

当使用 NoiseLookup 返回类型时,这控制要叠加在细胞噪声上的底层噪声。

* <mark style="color:purple;">`Perlin (Pe)`</mark>

* <mark style="color:purple;">`OpenSimplex2 (Si)`</mark>

* <mark style="color:purple;">`OpenSimplex2S (Sm)`</mark>

* <mark style="color:purple;">`Value (Va)`</mark>

* <mark style="color:purple;">`ValueCubic (VC)`</mark>

* <mark style="color:purple;">`White (Wh)`</mark>

* <mark style="color:purple;">`Cellular (Ce)`</mark>

* <mark style="color:red;">`CellularNoiseLookupFrequency (cF)`</mark>\

控制底层噪声的频率。

</details>

### Shard 噪声参数

<details>

<summary>额外的 Shard 噪声参数</summary>

* <mark style="color:red;">`Sharpness (h)`</mark>\
  通常为 `0..1.0`\
  控制 Shard 噪声的图案锐度。较高的值在图案内有更明确的边缘,而较低的值会显得更模糊。

</details>

### 分形噪声参数

<details>

<summary>分形噪声参数</summary>

* <mark style="color:red;">`FractalType (fT)`</mark>\
  设置要使用的分形噪声类型。
  * <mark style="color:purple;">`None (N)`</mark>
  * <mark style="color:purple;">`FBm (F)`</mark>
  * <mark style="color:purple;">`Ridged (R)`</mark>
  * <mark style="color:purple;">`PingPong (P)`</mark>\
    **额外的 PingPong 分形参数：**
    * <mark style="color:red;">`PingPongStrength (fP)`</mark>

**如果选择了 `None` 以外的分形类型：**

* <mark style="color:red;">`Octaves (fO)`</mark>\
  设置要使用的分形噪声层数。
* <mark style="color:red;">`Lacunarity (fL)`</mark>\
  设置每个分形层的缩放比例。值 >1 将有效增加每层的频率，值 <1 将有效降低每层的频率。
* <mark style="color:red;">`Gain (fG)`</mark>\
  设置每个分形层的相对强度。值 <1 将使每层强度递减，值 >1 将使每层强度递增。
* <mark style="color:red;">`WeightedStrength (fW)`</mark>\
  设置每层强度对噪声值的响应度。

</details>

### Domain Warp Parameters

<details>

<summary>Domain Warp Parameters</summary>

* <mark style="color:red;">`DomainWarpType (wT)`</mark>\
  设置要使用的域扭曲类型。
  * <mark style="color:purple;">`None (N)`</mark>
  * <mark style="color:purple;">`BasicGrid (G)`</mark>
  * <mark style="color:purple;">`OpenSimplex2 (S)`</mark>
  * <mark style="color:purple;">`OpenSimplex2Reduced (R)`</mark>
  * <mark style="color:purple;">`Flow (F)`</mark>
  * <mark style="color:purple;">`Turbulence (T)`</mark>

**如果选择了 `None` 以外的域扭曲类型：**

* <mark style="color:red;">`DomainWarpFreq (wF)`</mark>\
  设置域扭曲的频率。
* <mark style="color:red;">`DomainWarpOct (wO)`</mark>\
  设置域扭曲的层数。
* <mark style="color:red;">`DomainWarpGain (wG)`</mark>\
  设置每个域扭曲层的相对强度。
* <mark style="color:red;">`DomainWarpAmp (wA)`</mark>\
  设置域扭曲的整体振幅(强度)。
* <mark style="color:red;">`DomainWarpFrac (wC)`</mark>\
  设置要使用的域扭曲特定分形类型。
  * <mark style="color:purple;">`None (N)`</mark>
  * <mark style="color:purple;">`DomainWarpIndependent (I)`</mark>
  * <mark style="color:purple;">`DomainWarpProgressive (P)`</mark>
* <mark style="color:red;">`DomainWarpLacunarity (wl)`</mark>\
  设置每个域扭曲层的缩放比例。

</details>

## 示例

**`Value(Seed:123,Frequency:0.04)`**

<figure><img src="../.gitbook/assets/2024-01-10_20.38.35.png" alt=""><figcaption></figcaption></figure>

**`Cellular(cellularDistanceFunction:Euclidean,cellularReturnType:NoiseLookup,cellularNoiseLookup:Perlin,cellularNoiseLookupFrequency:0.2,Frequency:0.1)`**

_使用所有缩写的相同噪声:_ **`Ce(cD:e,cR:n,cN:Pe,cF:.2,F:.1)`**

<figure><img src="../.gitbook/assets/2024-01-10_20.41.26.png" alt=""><figcaption></figcaption></figure>