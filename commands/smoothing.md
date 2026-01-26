# 平滑

### `//ezsmooth`

<details>

<summary>平滑</summary>

**`//ezsmooth <radii> <iterations> <bias> [-w <profile>]`**

**`别名: //ezsm`**

`//ezsmooth` 命令使用三维平滑算法平滑所选区域的边缘和表面。

* **Radii（半径）**: 平滑半径或多个半径，可以是单个值或三个逗号分隔的值，分别对应东/西、上/下和北/南方向。此参数控制平滑效果的范围。
* **Iterations（迭代次数）**: 平滑操作执行的次数。迭代次数越多，结果越平滑，但处理时间也会增加。
* **Bias（偏差）**: 一个介于 -1.0 和 1.0 之间的值，用于调整平滑效果的扩展或收缩。正值会扩展平滑区域，负值会收缩它。
* **-w**: 见 [平滑方块](../smoothblocks/smoothblocks.md)。

</details>

### `//ezinflate`

<details>

<summary>膨胀</summary>

**`//ezinflate <radii> [-w <profile>]`**

**`别名: //inflate`**

`//ezinflate` 命令将所选区域内的方块体积按指定数量扩展，有效地"膨胀"建筑。

* **Radii（半径）**: 指定扩展距离，可以是单个值或三个逗号分隔的值，分别对应东/西、上/下和北/南方向。此值决定了新膨胀表面与原始表面的距离。
* **-w**: 见 [平滑方块](../smoothblocks/smoothblocks.md)。

</details>

### `//ezdeflate`

<details>

<summary>收缩</summary>

**`//ezdeflate <radii> [-w <profile>]`**

**`别名: //deflate`**

`//ezdeflate` 命令将所选区域内的方块体积按指定数量收缩，有效地"收缩"建筑。

* **Radii（半径）**: 指定扩展距离，可以是单个值或三个逗号分隔的值，分别对应东/西、上/下和北/南方向。此值决定了从原始表面向内移除方块的距离。
* **-w**: 见 [平滑方块](../smoothblocks/smoothblocks.md)。

</details>

### `//ezsmoothblocks`（v0.15.0 及以上版本）

<details>

<summary>平滑方块</summary>

**`//ezsmoothblocks <profile> <radius> <bias>`**

**`别名: //ezsb`**

`//ezsmoothblocks` 命令通过放置台阶、楼梯和墙来修改所选区域，创建更加平滑的表面。

* **Profile（配置文件）**: 决定使用的造型方块集合。见 [#profiles](../smoothblocks/smoothblocks.md#profiles "mention")。

* **Radius（半径）**: 指定平滑半径（以方块为单位）。此值决定了在平滑过程中考虑的每个方块周围的区域。值越大，平滑越激进。

* **Bias（偏差）**: 一个介于 -1.0 和 1.0 之间的值，用于调整平滑效果，决定放置或移除多少方块。正值会导致放置的方块多于移除的方块，负值会移除更多方块。
* **-w**: 见 [平滑方块](../smoothblocks/smoothblocks.md)。

</details>

#### `//ezsmoothblocks`（v0.14.0 及更早版本）

<details>

<summary>平滑方块（旧版）</summary>

**`//ezsmoothblocks <radius> <iterations> <bias> [-s] [-t] [-w]`**

**`别名: //smoothblocks`**

`//ezsmoothblocks` 命令通过放置台阶、楼梯和墙来修改所选区域，创建更加平滑的表面。

* **Radius（半径）**: 指定平滑半径（以方块为单位）。此值决定了在平滑过程中考虑的每个方块周围的区域。
* **Iterations（迭代次数）**: 平滑操作执行的次数。迭代次数越多，结果越平滑，但处理时间也会增加。
* **Bias（偏差）**: 一个介于 -1.0 和 1.0 之间的值，用于调整平滑效果的扩展或收缩。正值倾向于扩展平滑区域，负值倾向于收缩它，可以控制最终外观。
* **-s**: 限制平滑过程仅使用台阶。
* **-t**: 排除墙不进行平滑处理。
* **-w**: 使用备用方块集合。

</details>

***
