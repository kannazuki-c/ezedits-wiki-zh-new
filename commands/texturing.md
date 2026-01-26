# 纹理

{% embed url="https://www.youtube.com/watch?v=S-fZlxLPUZo" %}
视频教程由 [MegRae](https://megrae.art/) 制作
{% endembed %}

***

所有子命令均在 `//eztexture` (`//ezt`) 下\
例如 `//eztexture ambient`

## `//eztexture ...`

### `ambient`

<details>

<summary>环境纹理</summary>

**`//ezt ambient <mask> <palette> [radius] [brightness] [contrast] [-w]`**

通过近似区域内方块的环境光来进行纹理处理。

* **蒙版**: 要替换的方块。
* **调色板**: 指定要使用的调色板。
* **半径** (默认值: 3): 命令评估环境差异的半径。较大的半径会考虑每次计算的更广泛区域，导致过渡更平滑。
* **亮度** (默认值: 0.0): 调整调色板开始或结束的偏差。较高的值加强调色板的开始，较低的值强调结束。
* **对比度** (默认值: 0.0): 放大或减少平滑环境场和局部变化之间的差异，增强或减弱纹理的效果。
* **-w**: 尝试用最接近的现有材料对形状方块进行纹理处理。

</details>

### `axisgradient`

<details>

<summary>轴向渐变纹理</summary>

**`//ezt axisgradient <mask> <palette> [axis] [-r] [-w]`**

使用与单个轴对齐的渐变来对区域进行纹理处理。

* **蒙版**: 要替换的方块。
* **调色板**: 指定要使用的调色板。
* **轴** (默认值: "y"): 确定应用渐变的轴 ('x'、'y' 或 'z')，指导渐变流动的方向。
* **-r**: 激活相对渐变模式，在整个列中拉伸调色板。
* **-w**: 尝试用最接近的现有材料对形状方块 (楼梯、台阶等) 进行纹理处理。

</details>

### `blend`

<details>

<summary>混合纹理</summary>

**`//ezt blend <palette> [radius] [-v] [-w]`**

混合区域内的调色板方块。

* **调色板**: 指定用于混合的调色板。
* **半径** (默认值: "0.5"): 确定混合的半径，影响混合效果在每个方块周围应用的广度。
* **-v**: 激活完全混合模式，允许混合非表面方块。
* **-w**: 尝试用最接近的现有材料对形状方块 (楼梯、台阶等) 进行纹理处理。

</details>

### `blocklight`

<details>

<summary>方块光纹理</summary>

**`//ezt blocklight <mask> <palette> [-v] [-s] [-l] [-w]`**

根据游戏内方块光等级 (不包括天空光) 对区域进行纹理处理。

* **蒙版**: 要替换的方块。
* **调色板**: 指定要使用的调色板。
* **-v**: 激活时，仅考虑方块正上方的光等级。
* **-s**: 激活时，将考虑天空光等级。
* **-l**: 激活时，防止调色板替换光源方块。
* **-w**: 尝试用最接近的现有材料对形状方块 (楼梯、台阶等) 进行纹理处理。

</details>

### `cells`

<details>

<summary>单元格纹理</summary>

**`//ezt cells <mask> <palette> <amount> [brightness] [contrast] [-s] [-r] [-w]`**

使用类似细胞的图案对区域进行纹理处理。

* **蒙版**: 要替换的方块。
* **调色板**: 指定要使用的调色板。
* **数量**: 决定纹理中细胞的数量。
* **亮度**（默认值：0.0）：调整调色板起始或末尾的偏差。较高的值加强调色板的起始部分，较低的值加强末尾。
* **对比度**（默认值：0.0）：修改细胞之间的对比度，增强图案的清晰度和分离度。
* **-s**（默认值：-1）：用于生成细胞图案的可选种子。
* **-r**（默认值：5）：设置 Voronoi 图中种子点的排斥因子，影响细胞的形状和分布。
* **-w**：尝试使用最接近的现有材料对成形方块（楼梯、台阶等）进行纹理处理。

</details>

### `curvature`

<details>

<summary>曲率纹理</summary>

**`//ezt curvature <mask> <palette> [radius] [brightness] [contrast] [-w]`**

通过近似曲率对区域进行纹理处理。

* **蒙版**: 要替换的方块。
* **调色板**: 指定要使用的调色板。
* **半径**（默认值：3）：指定计算曲率的半径，影响效果的细微程度或突出程度。
* **亮度**（默认值：0.0）：调整调色板起始或末尾的偏差。较高的值加强调色板的起始部分，较低的值强调末尾。
* **对比度**（默认值：0.0）：修改不同曲率区域之间的对比度，增强图案的清晰度和分离度。
* **-w**：尝试使用最接近的现有材料对成形方块（楼梯、台阶等）进行纹理处理。

</details>

### `flow`

<details>

<summary>流场纹理</summary>

**`//ezt flow <mask> <palette> [exposure] [iterations] [velocity] [paletteScalar] [noise] [-m] [-g] [-f] [-w]`**

在选区内的所有表面上生成流场效果。

* **蒙版**: 要替换的方块。
* **调色板**: 指定要使用的调色板。
* **曝光度**（默认值：0.6）：控制流线的整体密度，影响使用调色板的数量。
* **每条线的迭代次数**（默认值：32）：绘制每条线所采取的步数，迭代次数越多，线条越长。
* **点速度**（默认值：0.5）：点在表面上移动的速度。
* **调色板索引标量**（默认值：1.0）：缩放用于选择调色板方块的值。
* **噪声**（默认值：\[类型：Perlin]）：用于生成流场的噪声类型。
* **-m**：点动量加权，混合先前的移动方向。
* **-g**：对点应用重力，将其拉向指定方向。
* **-f**：用最低调色板方块填充间隙。
* **-w**：尝试使用最接近的现有材料对成形方块（楼梯、台阶等）进行纹理处理。

</details>

### `noise`

<details>

<summary>噪声纹理</summary>

**`//ezt noise <mask> <palette> <noise> [-z] [-s] [-w]`**

使用给定的噪声对区域进行纹理处理。

* **Mask（蒙版）**: 要替换的方块。
* **Palette（调色板）**: 指定要使用的调色板。
* **Noise（噪声）** (默认值: `Perlin(Freq:0.05)`): 设置要使用的噪声。
* **-z** (默认值: 1): 调整噪声的缩放。
* **-s** (默认值: -1): 用于生成噪声图案的可选种子值。
* **-w**: 尝试使用最接近的现有材料对塑形方块（楼梯、台阶等）进行纹理处理。

</details>

### `pointlight`

<details>

<summary>点光源纹理</summary>

**`//ezt pointlight <mask> <palette> [falloffRange] [radius] [interval] [-l] [-o] [-r] [-f] [-w]`**

根据表面相对于光源的方向对区域进行纹理处理。

* **Mask（蒙版）**: 要替换的方块。
* **Palette（调色板）**: 指定要使用的调色板。
* **Falloff Range（衰减范围）** (默认值: 0): 设置衰减范围，即光点的亮度。如果设置为 0，则使用玩家与区域中心之间的距离。
* **Radius（半径）** (默认值: 1): 指定法线近似半径，影响光边缘的柔和度。
* **Interval（间隔）** (默认值: "0,90"): 定义表面方向间隔（以度为单位），其中 0 表示直接面向光源，180 表示背离光源。此间隔内的表面将被纹理处理，任何高于或低于此间隔的表面将使用调色板的第一个或最后一个方块进行纹理处理。
* **-f**: 禁用光衰减，在整个区域应用均匀的光强度，无论与光源的距离如何。
* **-l**: 将光源位置更改为给定坐标，否则使用玩家的位置。
* **-o** (默认值: 0.0): 确定遮挡强度。值越高，阴影越"深"。预期范围为 0-1。
* **-r** (默认值: 1): 确定遮挡（阴影）的平滑半径。
* **-w**: 尝试使用最接近的现有材料对塑形方块（楼梯、台阶等）进行纹理处理。

</details>

### `shift`

<details>

<summary>移位纹理</summary>

**`//ezt shift <palette> [shift]`**

通过将调色板移位一定数量来修改区域的纹理。

* **Palette**: 指定要使用的调色板。
* **Shift** (默认值: 1): 确定调色板内移位的方块数量。

</details>

### `sunlight`

<details>

<summary>阳光纹理</summary>

**`//ezt sunlight <mask> <palette> [radius] [interval] [-l] [-o] [-r] [-w]`**

使用全局光源方向来控制调色板应用的纹理化区域。

* **Mask**: 要替换的方块。
* **Palette**: 指定要使用的调色板。
* **Radius** (默认值: 1): 定义法线近似半径，影响表面相对于阳光的方向计算。
* **Interval** (默认值: "0,180"): 定义表面方向间隔（以度为单位），其中 0 表示直接面向光源，180 表示背离光源。此间隔内的表面将被纹理化，任何在此范围内外的表面将用调色板的第一个或最后一个方块进行纹理化。
* **-l** (默认值: down): 光线照射的全局方向。
* **-o** (默认值: 0.0): 确定遮挡强度。值越高，"阴影"越深。预期范围为 0-1。
* **-r** (默认值: 1): 确定遮挡（阴影）的平滑半径。
* **-w**: 尝试用最接近的现有材料纹理化造型方块（楼梯、台阶等）。

</details>

### `advanced`

<details>

<summary>高级纹理化</summary>

**`//ezt advanced <mask> <palette> <texture> [-w]`**

更强大的 eztexture 使用界面。它可以访问所有其他 eztexture 命令，也可以混合/组合它们。这意味着您可以例如同时进行环境光和阳光纹理化。

* **Mask**: 要替换的方块。
* **Palette**: 指定要使用的调色板。
* **Texture**: 纹理规范。
* **-w**: 尝试用最接近的现有材料纹理化造型方块（楼梯、台阶等）。

**如何定义 `<texture>`?**

`<texture>` 遵循以下指定复杂对象的常见方式：`<type>(<parameter1>:<value1>,<parameter2>:<value2>)` 每种纹理类型都有自己的参数集。您可以设置任意数量的参数。如果未设置参数，将使用默认值。每个参数可以接受不同的输入。某些参数接受数字，某些接受 3D 向量，某些接受噪声参数，甚至有些接受纹理对象本身。`<texture>` 可以是任何现有的纹理模式。一些简单的例子：

* `Ambient`
* `Ambient()`
* `Ambient(Radius:2)`
* `Ambient(Radius:2,Brightness:0.2,Contrast:0.3)`
* `Flow(Noise:@@ridged(Freq:0.12))`

澄清一下：以下两个命令的效果相同。

* `//eztexture ambient #existing ##grayscale 2 0.2 0.3`
* `//eztexture advanced #existing ##grayscale Ambient(Radius:2,Brightness:0.2,Contrast:0.3)`

**组合纹理**

以下纹理具有 `Texture1`(`T1`)/`Texture2`(`T2`) 参数，接受 `<texture>` 参数本身，允许您组合纹理模式：

* `Add(T1:...,T2:...)`
* `Subtract(T1:...,T2:...)`
* `Multiply(T1:...,T2:...)`
* `Divide(T1:...,T2:...)`
* `WeightedAverage(T1:...,T2:...)`
* `Darken(T1:...,T2:...)`
* `Lighten(T1:...,T2:...)`
* `Difference(T1:...,T2:...)`
* `Screen(T1:...,T2:...)`

以下纹理具有 `Texture`(`T`) 参数，接受 `<texture>` 参数本身，允许您调整/后处理纹理：

* `Adjust(T:...,Brightness:...,Contrast:...)`
* `Invert(T:...)`
* `Blend(T:...,Radius:...)`

示例：

* `WeightedAverage(T1:Sun(),T2:Ambient())`
* `Blend(T:Flow(Noise:@@ridged(Freq:0.12)),Radius:0.7)`
* `Darken(T1:Noise(Noise:@@smoothcells(freq:0.5)),T2:Flow)`
* `Adjust(T:Pointlight,Contrast:0.5)`

请注意，`Texture`/`Texture1`/`Texture2`（`T`/`T1`/`T2`）不是可选的。您必须设置它们才能使用这些组合/调整纹理。（如果您没有设置它们，您将收到一条错误消息 `cannot be null`）。

</details>

***
