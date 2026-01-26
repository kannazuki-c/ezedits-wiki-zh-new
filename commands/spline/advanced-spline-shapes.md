# 高级样条形状

以下 `//ezspline` 子命令提供了三种非常强大但更复杂的样条形状，具有几乎无限的可定制性。

***

#### ![](../../.gitbook/assets/SplinesNoise.png)

### `//ezspline` <mark style="color:orange;">`noise`</mark> <a href="#noise" id="noise"></a>

<details>

<summary><mark style="color:blue;">噪声样条</mark></summary>

**`//ezsp noise`** <mark style="color:orange;">**`<palette>`**</mark> [**`<radii>`**](common-parameters.md#radii) <mark style="color:orange;">**`[noise]`**</mark> <mark style="color:orange;">**`[depth]`**</mark> [**`[-s <stretch>]`**](common-parameters.md#stretch-s-less-than-stretchfactor-greater-than) [**`[-t <angle>]`**](common-parameters.md#twist) [**`[-p <kbParameters>]`**](common-parameters.md#kb-parameters) [**`[-q <quality>]`**](common-parameters.md#quality) [**`[-n <normalMode>]`**](common-parameters.md#normal-mode) [**`[-h]`**](common-parameters.md#help-page)

沿选定位置生成基于噪声的样条。

* <mark style="color:orange;">**`<Palette>`**</mark>:
  * 指定样条应由哪些方块构成。
* <mark style="color:orange;">**`[noise]`**</mark> (默认值: "Perlin(Freq:2,z:0.5)"):
  * 应沿样条路径嵌入的噪声。
* <mark style="color:orange;">**`[depth]`**</mark> (默认值: 0.7):
  * 噪声应切入圆柱形样条的深度。深度接近 0 时接近原始圆柱形样条,0.5 表示噪声可能达到半径深度的一半,1.0 表示完整半径,到达中心。大于 1.0 将导致断续的外观。
* <mark style="color:orange;">**`[-i <expression>]`**</mark> (默认值: "`r=sqrt(x*x+y*y);t=(r-1)/d+1;f=r>1?1:(4*r*(r-1))^2;g=f*t+(1-f)*n;p=max((r-1)/min(d,1)+1,.001);(g>t)*p`"):
  * 面向技术宅的高级参数。如果上面的内容看起来很吓人,请忽略。
  * 此表达式实现了噪声以特定相对 `<depth>` 切入圆柱的功能。[推导过程](https://www.desmos.com/calculator/qw8fro1npf)。如果你 _**真的**_ 想要,可以在这里使用不同的表达式来获得不同的结果。如果你不需要自定义噪声,只需使用 `//ezspline expression` 即可。
  * 输入参数为 _`x,y,z,n,d`_,其中 _`x,y,z`_ 的赋值方式与 [//ezspline expression](advanced-spline-shapes.md#expression-spline) 中相同,_`n`_ 是给定 `<noise>` 在坐标 _`x,y,z`_ 处的评估值,_`d`_ 是给定的 `<depth>` 参数。
  * 另一个可选表达式可以是:
    * `r=sqrt(x*x+y*y);(r<1&&n>0.5)*max(n,0.01)`: 如果你只想将噪声限制在圆柱形状内

_其余参数在_ [_通用参数_](common-parameters.md) _子页面中说明。_

示例:

`//ezspline noise ##Grayscale 10`

<img src="../../.gitbook/assets/SplinesNoise.png" alt="" data-size="original">

</details>

<details>

<summary><mark style="color:blue;">演示</mark></summary>

![](../../.gitbook/assets/SplinesNoise_example2.png)

只是我快速组合的一小组噪声命令,展示噪声样条的功能。\~eztaK

`//ezspline noise -##Magma 5,25 Ce(F:1.5,fO:1,cR:sub,M:OR,U:-.6) 0.6 -t 90`

![](../../.gitbook/assets/SplinesNoise_example3.png)

`//ezspline noise ##GrayWarm(3:11),251:8*15 25,10,25 Ce(F:1.6,fO:1,cD:r,cR:r,M:OR,L:-1.1,U:-.2) 0.4`

![](../../.gitbook/assets/SplinesNoise_example4.png)

`//ezspline noise -w Panes light_gray_stained_glass 20,15,25 Ce(f:1.4,z:.3,m:or,l:-1,u:-0.5) 3 -t 600 -i t=0.2;r=sqrt(x*x+y*y);m=1-abs(2*r-t-1)/abs(t-1);n<m&&r<1`

![](../../.gitbook/assets/SplinesNoise_example5.png)

`//ezspline noise ##Brown 20,12 Ce(f:4,cr:sub,cj:.8,m:or,u:-.5,l:-1.3) 0.2 -s 6 -t 20`

![](../../.gitbook/assets/SplinesNoise_example6.png)

`//ezspline noise -##GlowBlue(6:16) 20,12 Ce(f:2,cr:sub,m:or,u:-.55,l:-0.551,z:0.1) 0.9 -t 200`

![](../../.gitbook/assets/SplinesNoise_example7.png)

`//ezspline noise -w Slabs ##GrayCold(4:11),waxed_weathered_cut_copper 20 Ce(f:1.5,cr:sub,m:or,u:-0.85,l:-.5,y:0.3) -n UPRIGHT -i (x*x+n+y*y<1&&y<0)*(y+0.97)`

![](../../.gitbook/assets/SplinesNoise_example8.png)

</details>

***

#### ![](../../.gitbook/assets/SplinesExpression.png)

### `//ezspline` <mark style="color:orange;">`expression`</mark> <a href="#expression" id="expression"></a>

<details>

<summary><mark style="color:blue;">表达式样条</mark></summary>

**`//ezsp expression`** <mark style="color:orange;">`<palette>`</mark> [**`<radii>`**](common-parameters.md#radii)[**`[-s <stretch>]`**](common-parameters.md#stretch-s-less-than-stretchfactor-greater-than) [**`[-t <angle>]`**](common-parameters.md#twist) [**`[-p <kbParameters>]`**](common-parameters.md#kb-parameters) [**`[-q <quality>]`**](common-parameters.md#quality) [**`[-n <normalMode>]`**](common-parameters.md#normal-mode) <mark style="color:orange;">**`[-z] [-o]`**</mark> [**`[-h]`**](common-parameters.md#help-page) <mark style="color:orange;">**`<expression...>`**</mark>

沿选定位置生成由给定 WorldEdit 表达式塑形的样条。

* <mark style="color:orange;">**`<Palette>`**</mark>:
  * 指定方块调色板。
* <mark style="color:orange;">**`[-z]`**</mark>:
  * 不设置此标志时,z 轴的域为 0 到样条长度除以半径。您可以设置此标志来归一化沿样条路径的 z 轴到 \[-1,1] 域。
* <mark style="color:orange;">**`[-o]`**</mark>:
  * 默认情况下,表达式输出将 >0..1 映射到调色板。使用此标志可将输出映射到整数。
* <mark style="color:orange;">**`<expression...>`**</mark>:
  * [WorldEdit 表达式](https://worldedit.enginehub.org/en/latest/usage/other/expressions/)。输入变量为
    * -1 ≤ _`x`_ ≤ 1
    * -1 ≤ _`y`_ ≤ 1
    * 0 ≤ _`z`_ ≤ L,其中 L 是样条长度除以其半径。
    * 或 -1 ≤ _`z`_ ≤ 1,如果您使用 `-z` 标志。
  * 输出为归一化的调色板索引 (0,1] 或如果使用 -o 标志则为 (0,P],其中 P 是调色板中的方块数量。注意 <=0 表示不放置任何方块。

_其余参数在_ [_通用参数_](common-parameters.md) _子页面中说明。_

示例:

`//ezspline expression clay 10 -t 90 R=0.2;r=0.1;w=0.7;s=0.5;sqrt((abs(x)-w)^2+y^2)<R||sqrt(((z+1)%s-r)^2+y^2)<r&&abs(x)<w`

表达式由 [imhols](https://twitter.com/imhols1) 提供

<img src="../../.gitbook/assets/SplinesExpression.png" alt="" data-size="original">

</details>

***

#### ![](../../.gitbook/assets/SplinesStructure_example1.png)

### `//ezspline` <mark style="color:orange;">`structure`</mark> <a href="#structure" id="structure"></a>

<details>

<summary><mark style="color:blue;">结构样条</mark></summary>

**`//ezsp structure`** <mark style="color:orange;">**`<structure>`**</mark> [**`[radii]`**](common-parameters.md#radii)[**`[-s <stretch>]`**](common-parameters.md#stretch-s-less-than-stretchfactor-greater-than) [**`[-t <angle>]`**](common-parameters.md#twist) [**`[-p <kbParameters>]`**](common-parameters.md#kb-parameters) [**`[-q <quality>]`**](common-parameters.md#quality) [**`[-n <normalMode>]`**](common-parameters.md#normal-mode) <mark style="color:orange;">**`[-z]`**</mark> [**`[-h]`**](common-parameters.md#help-page)

沿选定凸选区定义的路径嵌入结构。

* <mark style="color:orange;">**`<structure>`**</mark>:
  * 沿路径嵌入的形状/剪贴板/建筑文件。参见 [available-structures.md](../placement/available-structures.md "mention")。
* <mark style="color:orange;">**`[-z]`**</mark>:
  * 归一化 Z 轴,这将导致恰好一个结构在整个路径长度上被拉伸。

结构将以其 Z 方向朝向路径放置。多个实例将一个接一个地重复,次数取决于其边界框能容纳多少次,除非你使用 `-z`,在这种情况下,结构的一个实例将在整个路径长度上被拉伸。

特别是对于 `//ezsp structure`,如果省略 [`[radii]`](common-parameters.md#radii) 参数,我们将自动计算结构以其原始/固有大小生成时的半径。

_其余参数在_ [_Common Parameters_](common-parameters.md) _子页面中概述。_

**示例**:

`//ezsp structure TS(P:##GlowPurple,S:Heart,T:=(z+y)*.4+.5) 12`

<img src="../../.gitbook/assets/SplinesStructure_example1.png" alt="" data-size="original">

</details>

***