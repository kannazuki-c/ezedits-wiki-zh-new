# 变形

变形命令将给定区域的内容变形为新的形状和形式。

所有子命令都在 `//ezdeform` (`//ezd`) 下\
例如 `//ezdeform hexagonalize`

***

## 子命令列表

***

#### ![](../../.gitbook/assets/ezdeform_hexagonalize_xrot.gif)

### `//ezdeform`` `<mark style="color:orange;">`hexagonalize`</mark>

<details>

<summary><mark style="color:blue;">六边形化</mark></summary>

**`//ezdeform hexagonalize [`**<mark style="color:orange;">**`size`**</mark>**`] [`**<mark style="color:orange;">**`air_gap`**</mark>**`] [`**<mark style="color:orange;">**`x_rotation`**</mark>**`] [`**<mark style="color:orange;">**`z_rotation`**</mark>**`] [`**<mark style="color:orange;">**`offset_angle`**</mark>**`] [`**<mark style="color:orange;">**`-w <profile>`**</mark>**`]`**

将区域变形为六边形柱体。

* <mark style="color:orange;">**Size**</mark>（默认值：12）：设置六边形的大小。

![](../../.gitbook/assets/ezdeform_hexagonalize_size.gif)

* <mark style="color:orange;">**Air Gap**</mark>（默认值：0.0）：定义柱体之间的空气间隙宽度。

![](../../.gitbook/assets/ezdeform_hexagonalize_airgap.gif)

* <mark style="color:orange;">**X Rotation**</mark>（默认值：0.0）：设置柱体沿X轴的旋转角度，单位为度。

![](../../.gitbook/assets/ezdeform_hexagonalize_xrot.gif)

* <mark style="color:orange;">**Z Rotation**</mark>（默认值：0.0）：设置柱体沿Z轴的旋转角度，单位为度。

![](../../.gitbook/assets/ezdeform_hexagonalize_zrot.gif)

* <mark style="color:orange;">**Offset Angle**</mark>（默认值：60.0）：调整偏移角度，控制形状（范围：0-90度）。

![](../../.gitbook/assets/ezdeform_hexagonalize_shape.gif)

* <mark style="color:orange;">**-w**</mark>：参见 [Smoothblocks](../../smoothblocks/smoothblocks.md)。

</details>

***

#### ![](../../.gitbook/assets/ezdeform_noise.gif)

### `//ezdeform`` `<mark style="color:orange;">`noise`</mark>

<details>

<summary><mark style="color:blue;">噪声</mark></summary>

**`//ezdeform noise <`**<mark style="color:orange;">**`noise`**</mark>**`> [`**<mark style="color:orange;">**`strength`**</mark>**`] [`**<mark style="color:orange;">**`-z <zoom>`**</mark>**`] [`**<mark style="color:orange;">**`-s <seed>`**</mark>**`] [`**<mark style="color:orange;">**`-w <profile>`**</mark>**`]`**

根据给定的噪声场变形区域。

* <mark style="color:orange;">**Noise**</mark>：指定用于变形的噪声类型。

- <mark style="color:orange;">**Strength**</mark>（默认值：2.0）：设置噪声效果的强度。

![](../../.gitbook/assets/ezdeform_noise_strength.gif)

* <mark style="color:orange;">**Zoom**</mark>（默认值：1）：确定噪声的缩放比例。

![](../../.gitbook/assets/ezdeform_noise_frequency.gif)

* <mark style="color:orange;">**-s \<seed>**</mark>（默认值：-1）：噪声图案的可选种子。
* <mark style="color:orange;">**-h**</mark>：使用时，仅水平变形区域。

![](../../.gitbook/assets/ezdeform_noise_hflag.gif)

* <mark style="color:orange;">**-v**</mark>：使用时，仅垂直变形区域。

![](../../.gitbook/assets/ezdeform_noise_vflag.gif)

* <mark style="color:orange;">**-w**</mark>：参见 [Smoothblocks](../../smoothblocks/smoothblocks.md)。

</details>

***

#### ![](../../.gitbook/assets/ezdeform_rotate_angle.gif)

### `//ezdeform`` `<mark style="color:orange;">`rotate`</mark>

<details>

<summary><mark style="color:blue;">旋转</mark></summary>

**`//ezdeform rotate <`**<mark style="color:orange;">**`angle`**</mark>**`> [`**<mark style="color:orange;">**`-o`**</mark>**`] [`**<mark style="color:orange;">**`-w <profile>`**</mark>**`]`**

顺时针旋转区域，旋转中心为选区的中心（或使用 -o 时为玩家头部位置），旋转轴由玩家的视线方向定义。

* <mark style="color:orange;">**Angle**</mark>：设置旋转角度，单位为度。

![](../../.gitbook/assets/ezdeform_rotate_angle.gif)

* <mark style="color:orange;">**-o**</mark>：使用时，将玩家位置作为旋转中心，而不是选区的中心。
* <mark style="color:orange;">**-w**</mark>：参见 [Smoothblocks](../../smoothblocks/smoothblocks.md)。

</details>

***

#### ![](../../.gitbook/assets/ezdeform_voronoialize_airgap.gif)

### `//ezdeform`` `<mark style="color:orange;">`voronoialize`</mark>

<details>

<summary><mark style="color:blue;">Voronoi化</mark></summary>

**`//ezdeform voronoialize [`**<mark style="color:orange;">**`size`**</mark>**`] [`**<mark style="color:orange;">**`air_gap`**</mark>**`] [`**<mark style="color:orange;">**`-s <seed>`**</mark>**`] [`**<mark style="color:orange;">**`-w <profile>`**</mark>**`]`**

将区域变形为随机分布的Voronoi单元。

* <mark style="color:orange;">**Size**</mark>（默认值：12）：确定Voronoi单元的大小。

![](../../.gitbook/assets/ezdeform_voronoialize_size.gif)

* <mark style="color:orange;">**空隙**</mark>（默认值：0.0）：指定单元格之间的空气间隙宽度。

![](../../.gitbook/assets/ezdeform_voronoialize_airgap.gif)

* <mark style="color:orange;">**-s \<seed>**</mark>（默认值：-1）：用于生成图案的可选种子。
* <mark style="color:orange;">**-w \<profile>**</mark>：见 [平滑方块](../../smoothblocks/smoothblocks.md)。

</details>

***

#### ![](../../.gitbook/assets/ezdeform_voronoialize2_airgap.gif)

### `//ezdeform`` `<mark style="color:orange;">`voronoialize2`</mark>

<details>

<summary><mark style="color:blue;">替代Voronoi化</mark></summary>

**`//ezdeform voronoialize2 <`**<mark style="color:orange;">**`amount`**</mark>**`> [`**<mark style="color:orange;">**`air_gap`**</mark>**`] [`**<mark style="color:orange;">**`-s <seed>`**</mark>**`] [`**<mark style="color:orange;">**`-r <uniformity>`**</mark>**`] [`**<mark style="color:orange;">**`-n <normalOffset>`**</mark>**`] [`**<mark style="color:orange;">**`-w <profile>`**</mark>**`]`**

将区域变形为沿表面形状分布的Voronoi单元格。与第一个voronoialize相比，可能更准确地保留原始形状。

* <mark style="color:orange;">**数量**</mark>：指定voronoi图案中的单元格数量。较小的数量自然导致更大的单元格，反之亦然。

![](../../.gitbook/assets/ezdeform_voronoialize2_amount.gif)

* <mark style="color:orange;">**空隙**</mark>（默认值：0.0）：确定单元格之间的空气间隙宽度。

![](../../.gitbook/assets/ezdeform_voronoialize2_airgap.gif)

* <mark style="color:orange;">**-s \<seed>**</mark>（默认值：-1）：用于生成图案的可选种子。`-1` 将随机生成种子。
* <mark style="color:orange;">**-r \<uniformity>**</mark>（默认值：15）：设置voronoi种子点排斥迭代次数。0表示完全随机。15次迭代会产生更均匀/规则的外观。

![](../../.gitbook/assets/ezdeform_voronoialize2_repulsion.gif)

* <mark style="color:orange;">**-n \<normalOffset>**</mark>（默认值：5）：技术参数。调整单元格种子进入形状的深度。较大/较厚的形状可以从较大的值中受益。较薄的形状如果生成出现问题，应使用较小的值。
* <mark style="color:orange;">**-w \<profile>**</mark>：见 [平滑方块](../../smoothblocks/smoothblocks.md)。

</details>

***

#### ![](../../.gitbook/assets/ezdeform_voxelize_scales.gif)

### `//ezdeform`` `<mark style="color:orange;">`voxelize`</mark>

<details>

<summary><mark style="color:blue;">体素化</mark></summary>

**`//ezdeform voxelize <`**<mark style="color:orange;">**`scales`**</mark>**`> <`**<mark style="color:orange;">**`gap`**</mark>**`> <`**<mark style="color:orange;">**`distortion`**</mark>**`> [`**<mark style="color:orange;">**`-i <primary>`**</mark>**`] [`**<mark style="color:orange;">**`-j <secondary>`**</mark>**`] [`**<mark style="color:orange;">**`-s <seed>`**</mark>**`] [`**<mark style="color:orange;">**`-hv`**</mark>**`] [`**<mark style="color:orange;">**`-w <profile>`**</mark>**`]`**

将区域变形为更大的立方体形状。

* <mark style="color:orange;">**缩放**</mark>（默认值：3）：设置立方体的缩放大小。

![](../../.gitbook/assets/ezdeform_voxelize_scales.gif)

你可以放置三个逗号分隔的值来为每个轴定义维度。\
![](../../.gitbook/assets/ezdeform_voxelize_scales3.gif)

* <mark style="color:orange;">**间隙**</mark>（默认值：0.0）：定义体素之间的空气间隙宽度。

![](../../.gitbook/assets/ezdeform_voxelize_airgap.gif)

* <mark style="color:orange;">**扭曲**</mark>（默认值：0.0）：调整随机网格扭曲的强度（范围：0-1）。

- <mark style="color:orange;">**-s \<seed>**</mark>（默认值：-1）：扭曲的可选种子。

![](../../.gitbook/assets/ezdeform_voxelize_distortion.gif)

* <mark style="color:orange;">**-i \<primary>**</mark>（默认值：y）：指定网格的y轴方向。

![](../../.gitbook/assets/ezdeform_voxelize_primary.gif)

* <mark style="color:orange;">**-j \<secondary>**</mark>（默认值：-x）：指定网格的x轴方向。

![](../../.gitbook/assets/ezdeform_voxelize_secondary.gif)

* <mark style="color:orange;">**-h**</mark>：使用时，仅水平体素化。

![](../../.gitbook/assets/ezdeform_voxelize_hflag1.gif) ![](../../.gitbook/assets/ezdeform_voxelize_hflag2.gif)

* <mark style="color:orange;">**-v**</mark>：使用时，仅垂直体素化。

![](../../.gitbook/assets/ezdeform_voxelize_vflag1.gif) ![](../../.gitbook/assets/ezdeform_voxelize_vflag2.gif)

* <mark style="color:orange;">**-w**</mark>：见 [平滑方块](../../smoothblocks/smoothblocks.md)。

</details>

***
