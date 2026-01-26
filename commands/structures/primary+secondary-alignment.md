# 主要+次要对齐

对齐定义了结构放置时的方向。

## 说明

每个结构都有一个固有的"向上"方向和一个固有的"向前"方向。默认情况下,结构放置时其向上方向朝向上方(+y),其向前方向朝向前方(+x)。

最重要的是,现在你可以通过定义结构的向上方向和向前方向应该朝向何处来控制结构的放置方式。

我们让用户使用两个方向来定义对齐:

{% hint style="info" %}
`<primary>` 方向定义放置的 +y 方向。

`<secondary>` 方向与主要方向一起暗示放置的 +x 方向。

注意:主要方向和次要方向不能是同一个方向。
{% endhint %}

<details>

<summary>使用示例进行更深入的解释:</summary>

假设这是我们想要放置的建筑,例如将其作为我们当前的 WorldEdit 剪贴板。

<img src="../../.gitbook/assets/AlignmentGuide_example1.png" alt="" data-size="original">

作为参考,红色光束朝向正 x 方向(东),蓝色光束朝向正 z 方向(南),绿色光束朝向正 y 方向(上)。

我们现在想使用任何 ezEdits 结构命令以各种方向放置它。为此,我们可以定义一个 `<primary>` 和 `<secondary>` 方向。让我们通过几个示例来了解这些参数的分配以及发生了什么:

让我们将 `<primary>` 设置为 `up`,将 `<secondary>` 设置为 `east`(你可以使用 [Constant](primary+secondary-alignment.md#constant) 模式来实现)(这些方向是默认方向):

<img src="../../.gitbook/assets/AlignmentGuide_example1.png" alt="" data-size="original">

我们的形状完全按照我们复制时的方向粘贴。上方仍然是上方,右侧仍然是右侧,依此类推。

现在,考虑以下三个示例:

1. **`<primary>`** 设置为 **`south`**,`<secondary>` 保持为 `east`:

<img src="../../.gitbook/assets/AlignmentGuide_example2.png" alt="" data-size="original">

注意,当我们复制时原本_"向上"_的方向,即我们例子中的绿色光束,现在指向我们设置主要方向的方向:_南_。同时,原本_向东_的方向仍然是_东_。蓝色光束作为这次 90° 旋转的结果向下指。

2. **`<primary>`** 设置为向量 **`(0,1,1)`**,即"对角"向上和向南的方向,`<secondary>` 设置为 `east`:

<img src="../../.gitbook/assets/AlignmentGuide_example3.png" alt="" data-size="original">

再次注意,当我们复制时原本_"向上"_的方向,即我们例子中的绿色光束,现在指向我们设置主要方向的方向:_对角向上和向南_。

3. **`<primary>`** 设置为向量 **`(1,1,0)`**,即对角向上和**向东**的方向,而 `<secondary>` 设置为 `east`:

<img src="../../.gitbook/assets/AlignmentGuide_example4.png" alt="" data-size="original">

绿色光束正确地沿着主要方向指向,对角向上和向东。当我们 //copy 剪贴板时指向_上方_的任何东西总是与主要方向设置的方向对齐!

但现在,即使次要方向设置为_东_,红色光束也不再直接指向东方(而是对角向下和向东)。这是预期的行为。

想象一下如果它指向东方：那么绿色和红色光束将呈45°角，而不是原来的90°角。我们的结构将会变形/弯曲/剪切。

我们决定实现的方案是：（当我们将结构的+y方向与给定的主方向对齐时）不是将结构的+x方向与给定的次方向对齐，而是选择与给定次方向最相似但仍然垂直于主方向的方向。

因此，如果主方向和次方向不是完全垂直的，如上例所示，次方向会被替换为最相似但仍然垂直的向量！

仅供参考，这里有一个小GIF，展示了在设定主方向后，剩余的垂直次方向：

<img src="../../.gitbook/assets/AlignmentGuide_example5.gif" alt="" data-size="original">

再举一个最终示例：

**`<primary>`** 设置为向量 **`(-1,2,-1)`**，即一个向上和西北方向的方向，而 **`<secondary>`** 设置为 **`west`**：

<img src="../../.gitbook/assets/AlignmentGuide_example6.png" alt="" data-size="original">

如你所见，绿色光束，或者说我们复制时建筑中原本向上的方向，现在指向我们指定的 `西北+2*向上` 方向，而红色光束，或者说我们复制时原本向东的方向，现在尽可能指向 `西方`，同时仍然垂直于主方向。

所有这些都独立于你当前的剪贴板。这里是另一个结构在其原始方向下的样子，以及按照前一个示例对齐后的放置效果。

<img src="../../.gitbook/assets/AlignmentGuide_example7.png" alt="" data-size="original"> <img src="../../.gitbook/assets/AlignmentGuide_example8.png" alt="" data-size="original">

你能看出为什么将主方向设置为 `(-1,2-1)` 并将次方向设置为 `west` 会导致树叶像那样定向吗？

***

顺便说一下，使用的命令是

`//ezbrush place Clipboard Constant(Direction:(-1,2,-1)) Constant(Direction:west)`

或者，如果你喜欢缩写，

`//ezbr pl Cl C(D:(-1,2,-1)) C(D:west)`

通过这个主方向+次方向系统，我们希望你能够在任何场景下轻松快速地为每个结构放置构建所需的3D方向。

</details>

## 概述

主方向和副方向可以设置为以下任意一种：

<table data-view="cards" data-full-width="false"><thead><tr><th>名称</th><th>缩写</th><th>描述</th></tr></thead><tbody><tr><td><a href="primary+secondary-alignment.md#constant"><strong><code>Constant</code></strong></a></td><td><strong><code>C</code></strong></td><td>为所有放置显式设置一个恒定方向。</td></tr><tr><td><a href="primary+secondary-alignment.md#random"><strong><code>Random</code></strong></a></td><td><strong><code>R</code></strong></td><td>每次放置使用随机方向。</td></tr><tr><td><a href="primary+secondary-alignment.md#noise"><strong><code>Noise</code></strong></a></td><td><strong><code>N</code></strong></td><td>基于在放置位置评估噪声函数得出的方向。</td></tr><tr><td><a href="primary+secondary-alignment.md#aim"><strong><code>Aim</code></strong></a></td><td><strong><code>A</code></strong></td><td>你的玩家瞄准方向。</td></tr><tr><td><a href="primary+secondary-alignment.md#playerrelative"><strong><code>PlayerRelative</code></strong></a></td><td><strong><code>P</code></strong></td><td>从放置位置指向当前玩家位置的方向。</td></tr><tr><td><a href="primary+secondary-alignment.md#surfacenormal"><strong><code>SurfaceNormal</code></strong></a></td><td><strong><code>S</code></strong></td><td>放置位置所在区域的近似表面法线。</td></tr><tr><td><a href="primary+secondary-alignment.md#viewdiff"><strong><code>ViewDiff</code></strong></a></td><td><strong><code>V</code></strong></td><td>使用两次点击定义一个方向。仅适用于笔刷。</td></tr><tr><td><a href="primary+secondary-alignment.md#tangential"><strong><code>Tangential</code></strong></a></td><td><strong><code>T</code></strong></td><td>路径的切线方向。仅适用于阵列。</td></tr><tr><td><a href="primary+secondary-alignment.md#orthogonal"><strong><code>Orthogonal</code></strong></a></td><td><strong><code>O</code></strong></td><td>路径的正交方向。仅适用于阵列。</td></tr></tbody></table>

## 设置

***

### Constant

为所有放置明确设置一个恒定方向。

语法：<mark style="color:orange;">**`Constant`**</mark> 或 <mark style="color:orange;">**`Constant(Direction:<direction>)`**</mark>

缩写：<mark style="color:orange;">**`C`**</mark> 或 <mark style="color:orange;">**`C(D:<direction>)`**</mark>

如果你没有指定 `<direction>`，那么：

* 如果你设置的是 `<primary>`，默认方向是 **+y**。
* 如果你设置的是 `<secondary>`，默认方向是 **+x**。

有多种方式可以定义方向。可以使用坐标轴、基本方位、向量表示法，或者玩家相对方向如前、左、右等。专业提示：你还可以使用简单的算术运算符将方向相加，例如 `east-z+(0,0.5,0)`。专业提示²：在末尾加上 `=` 可以在输入时评估你的方向表达式。

<details>

<summary><mark style="color:blue;">示例</mark></summary>

`//ezsc Clipboard C(D:(0,2,0)) C(D:east)`

<img src="../../.gitbook/assets/ConstantAlignment_example1.png" alt="" data-size="original">

`//ezsc Clipboard C(D:(-1,2,-1)) C(D:east)`

<img src="../../.gitbook/assets/ConstantAlignment_example2.png" alt="" data-size="original">

`//ezsc Clipboard C(D:(-1,2,-1)) C(D:-aim)`

<img src="../../.gitbook/assets/ConstantAlignment_example3.png" alt="" data-size="original">

</details>

***

### Random

为每次放置使用随机方向。

语法：<mark style="color:orange;">**`Random`**</mark>

缩写：<mark style="color:orange;">**`R`**</mark>

<details>

<summary><mark style="color:blue;">示例</mark></summary>

`//ezsc Clipboard Constant Random`

* 仅将 `<secondary>` 设置为 Random，primary 保持向上
* 注意我们结构的向上方向（绿色光束）保持向上（primary 设置为向上），但每次放置都围绕 primary（在本例中为 y 轴）随机旋转，因为 secondary 是随机的。

<img src="../../.gitbook/assets/RandomAlignment_demo1.png" alt="" data-size="original">

`//ezsc Clipboard Random Constant`

* 仅将 `<primary>` 设置为 Random，secondary 保持指向东方。
* 地形替换为玻璃以便更好地观察。
* 注意绿色光束现在朝向各个方向，但红色光束在所有放置中大致都指向东方。

<img src="../../.gitbook/assets/RandomAlignment_demo2.png" alt="" data-size="original">

`//ezsc Clipboard Random Random`

* 将两者都设置为 Random

<img src="../../.gitbook/assets/RandomAlignment_demo3.png" alt="" data-size="original">

</details>

***

### Noise

基于在放置位置评估噪声函数的方向。

语法：<mark style="color:orange;">**`Noise`**</mark> 或 <mark style="color:orange;">**`Noise(Noise:<noise>)`**</mark>

缩写：<mark style="color:orange;">**`N`**</mark> 或 <mark style="color:orange;">**`N(N:<noise>)`**</mark>

默认的 `<noise>` 是 `Perlin(Freq:0.01)`。

<details>

<summary><mark style="color:blue;">示例</mark></summary>

`//ezsc Clipboard Constant Noise`

* 俯视截图
* `<primary>` 仍然保持向上，只有 `<secondary>` 设置为 Noise。
* 默认的 Noise 是 Perlin Noise。

<img src="../../.gitbook/assets/NoiseAlignment_example2.png" alt="" data-size="original">

`//ezsc Clipboard Constant Noise(N:Vor(Freq:0.02,DistReturn:cell))`

* 与上述场景相同，但使用了 [Cellular Noise](https://en.wikipedia.org/wiki/Voronoi_diagram#/media/File:Coloured_Voronoi_3D_slice.svg)。
* 你可以看到每个单元格都有自己的随机方向。

<img src="../../.gitbook/assets/NoiseAlignment_example1.png" alt="" data-size="original">

</details>

***

### Aim

你的玩家瞄准方向。

语法：<mark style="color:orange;">**`Aim`**</mark>

缩写：<mark style="color:orange;">**`A`**</mark>

注意：对于笔刷，`Constant(Direction:aim)` 将使用你在绑定笔刷时的玩家瞄准方向，而 `Aim` 将在每次笔刷操作时使用玩家的瞄准方向。

<details>

<summary><mark style="color:blue;">示例</mark></summary>

`//ezsc Clipboard Aim Constant`

* 如果我们将 `<primary>` 设置为 `Aim`，那么我们结构的向上方向（示例中的绿色光束）将与我们当前玩家的瞄准方向对齐。
* 图片中包含了我的玩家模型作为参考。那是我执行命令时所看的方向。_瞄准方向在 F3+B 中以细蓝线可视化_

<img src="../../.gitbook/assets/AimAlignment_demo1.png" alt="" data-size="original"><img src="../../.gitbook/assets/AimAlignment_demo2.png" alt="" data-size="original">

</details>

***

### PlayerRelative

从放置位置指向当前玩家位置的方向。

语法：<mark style="color:orange;">**`PlayerRelative`**</mark>

缩写：<mark style="color:orange;">**`P`**</mark>

<details>

<summary><mark style="color:blue;">示例</mark></summary>

`//ezsc Clipboard PlayerRelative Constant`

* 如果你将 `<primary>` 设置为 `PlayerRelative`，那么每个结构的放置方式将使其向上方向指向你的玩家位置。
* 如果你仔细看，可以在图片中看到我的玩家模型。那是我执行命令的位置。

<img src="../../.gitbook/assets/PlayerRelative_demo1.png" alt="" data-size="original"><img src="../../.gitbook/assets/PlayerRelative_demo2.png" alt="" data-size="original">

`//ezbr place Shape(S:Cone,P:diamond_block) PlayerRelative Constant -s 12,36,12`

<img src="../../.gitbook/assets/PlayerRelative_demo3.gif" alt="" data-size="original">

</details>

***

### SurfaceNormal

放置位置区域的近似表面法线。

语法：<mark style="color:orange;">**`SurfaceNormal`**</mark>

缩写：<mark style="color:orange;">**`S`**</mark>

[法线](https://en.wikipedia.org/wiki/Normal_\(geometry\))是指垂直于所讨论地形的方向。

<details>

<summary><mark style="color:blue;">示例</mark></summary>

`//ezbr place Shape(P:57,S:Cone) SurfaceNormal Constant -s 12,36,12`

你可以看到我们的游戏内对齐可视化工具会根据你持有笔刷时所看的地形部分动态调整自身方向。

<img src="../../.gitbook/assets/SurfaceNormal_demo1.gif" alt="" data-size="original">

</details>

***

### ViewDiff

使用两次点击定义一个方向。仅适用于笔刷。

语法：<mark style="color:orange;">**`ViewDiff`**</mark>

缩写：<mark style="color:orange;">**`V`**</mark>

每次放置需要一次右键点击和一次左键点击。第一次右键点击在目标方块处设置放置位置。然后在其他地方左键点击定义一个方向：从你的第一次（右键）点击目标位置到你的第二次（左键）点击位置。

<details>

<summary><mark style="color:blue;">示例</mark></summary>

`//ezbr place Clipboard SurfaceNormal ViewDiff`

这里我将主方向设置为 SurfaceNormal，并通过 ViewDiff 模式用第二次点击控制次方向。注意我的手部动作。你可以看到我在右键和左键之间交替点击。右键点击设置放置位置，左键点击设置 ViewDiff 方向。我们的游戏内对齐可视化工具会根据你的移动和操作动态更新。

<img src="../../.gitbook/assets/output.gif" alt="" data-size="original">

`//ezbr place Shape(S:Torus(Thickness:0.4),P:57) PlayerRelative ViewDiff -s 20,20,30 -k x -c 90`

这个圆环形状需要更多参数，所以这个例子比平常长一些。但需要注意的重点是，主方向设置为 PlayerRelative，意味着圆环的顶部始终面向玩家，次方向设置为 ViewDiff，意味着最终方向由第二次点击决定。在这里，每次右键点击后，我交替在放置位置的上方和左/右方左键点击，以创建一个连接的链条。

<img src="../../.gitbook/assets/output (1).gif" alt="" data-size="original">

</details>

***

### Tangential

路径的切线方向。仅适用于阵列。

语法：<mark style="color:orange;">**`Tangential`**</mark>

缩写：<mark style="color:orange;">**`T`**</mark>

<details>

<summary><mark style="color:blue;">示例</mark></summary>

`//ezarray Clipboard Tangential Constant -g 11 -o 2`

_Tangential_ 方向指向放置位置处样条路径的切线方向。如果你将主方向设置为 _Tangential_，形状的顶部会像这样沿着样条指向。

<img src="../../.gitbook/assets/TangentialAlignment_example1.png" alt="" data-size="original">

</details>

***

### Orthogonal

路径的正交方向。仅适用于阵列。

语法：<mark style="color:orange;">**`Orthogonal`**</mark> 或 <mark style="color:orange;">**`Orthogonal(Angle:<angle>)`**</mark>

缩写：<mark style="color:orange;">**`O`**</mark> 或 <mark style="color:orange;">**`O(A:<angle>)`**</mark>

角度以度为单位给出，定义正交方向的初始方向，其中 0° 和 360° 朝上，90° 和 270° 朝左和右，180° 朝下（至少在样条的第一部分是这样。如果法线模式设置为 CONSISTENT（默认设置），它可能会沿着路径进一步扭曲）。

<details>

<summary><mark style="color:blue;">示例</mark></summary>

`//ezarray Clipboard Orthogonal Constant`

_Orthogonal_ 方向指向放置位置处垂直于样条路径的方向。如果你将主方向设置为 _Orthogonal_，形状的顶部将指向垂直于样条路径的方向，如下所示。

<img src="../../.gitbook/assets/OrthogonalAlignment_example1.png" alt="" data-size="original">

这是一个展示 `<angle>` 参数的 GIF：

<img src="../../.gitbook/assets/StructuresAlignmentsOrthogonal_example.gif" alt="" data-size="original">

`//ezarray Clipboard Orthogonal Constant -n HORIZONTAL`

[-n 标志](array-parameters.md#spline-orientation-n-less-than-normalmode-greater-than)对正交方向有直接影响。

<img src="../../.gitbook/assets/OrthogonalAlignment_example2.png" alt="" data-size="original">

</details>

***

## 参数

以下标志调整对齐方式的计算方式。

***

### 对齐到特定方向：<mark style="color:orange;">`[-j <snapDirections>]`</mark>

此参数允许你将选定的对齐方向限制为指定的子集。例如，对齐到/仅允许基本方向，即 90° 旋转。

可用选项：

* <mark style="color:orange;">**`MULTIPLES_90`**</mark>
  * 仅允许 90° 的倍数，即所有轴对齐方向。
* <mark style="color:orange;">**`MULTIPLES_45`**</mark>
  * 仅允许 45° 的倍数，即轴对齐方向和所有完美对角线。
* <mark style="color:orange;">**`MULTIPLES_22_5`**</mark>
  * 仅允许 22.5° 的倍数。
* <mark style="color:orange;">**`MULTIPLES_15`**</mark>
  * 仅允许 15° 的倍数。
* <mark style="color:orange;">**`DIAGONALS_1_1`**</mark>
  * 仅允许轴对齐方向和完美的"1:1"对角线。
* <mark style="color:orange;">**`DIAGONALS_2_1`**</mark>
  * 仅允许 <mark style="color:orange;">`DIAGONALS_1_1`</mark> 方向和任何"2:1"对角线。
* <mark style="color:orange;">**`DIAGONALS_3_1`**</mark>
  * 仅允许 <mark style="color:orange;">`DIAGONALS_2_1`</mark> 方向和任何"3:1"对角线。
* <mark style="color:orange;">**`DIAGONALS_4_1`**</mark>
  * 仅允许 <mark style="color:orange;">`DIAGONALS_3_1`</mark> 方向和任何"4:1"对角线。
* <mark style="color:orange;">**`DIAGONALS_5_1`**</mark>
  * 仅允许 <mark style="color:orange;">`DIAGONALS_4_1`</mark> 方向和任何"5:1"对角线。

<details>

<summary><mark style="color:blue;">示例</mark></summary>

`//ezbrush Cl Constant ViewDiff -j MULTIPLES_45`

<img src="../../.gitbook/assets/AlignmentSnapToAngles_example.gif" alt="" data-size="original">

</details>

***

### 扰动次要方向：<mark style="color:orange;">\[-x]</mark>

在我们的主要+次要系统中，如果两个向量共线（即它们在同一条线上），放置将失败。

通过启用此标志，ezEdits 会尝试通过轻微扰动次要方向来规避这种情况。