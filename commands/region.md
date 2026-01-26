# 区域

在您选定的区域内操作的杂项命令集合。

### `//ezvines`

<details>

<summary>藤蔓</summary>

**`//ezvines <mask> <pattern> [percentage] [min_length] [max_length]`**

**`别名: //vines`**

* **蒙版**: 指定要悬挂"藤蔓"的方块匹配蒙版。
* **图案**: 决定放置方块的图案。
* **百分比** (默认: 10%): 设置悬挂藤蔓的方块百分比。
* **最小长度** (默认: 2): 指定藤蔓的最小长度。
* **最大长度** (默认: 5): 定义藤蔓的最大长度。

<img src="../.gitbook/assets/ezvines_mask.gif" alt="" data-size="original"> **`<mask>`**

<img src="../.gitbook/assets/ezvines_percentage.gif" alt="" data-size="original"> **`[percentage]`**

<img src="../.gitbook/assets/ezvines_length.gif" alt="" data-size="original"> **`[min_length] [max_length]`**

</details>

### `//ezmoss`

<details>

<summary>苔藓</summary>

**`//ezmoss <pattern> [amount] [smooth_radii] [smooth_iterations]`**

**`别名: //moss`**

* **图案**: 决定用于苔藓的方块图案。
* **数量** (默认: 2.0): 指定放置的苔藓数量。允许使用十进制值，数值在某种程度上是任意的。
* **平滑半径** (默认: 1): 设置苔藓放置的平滑半径。可以是一个半径或三个逗号分隔的半径，顺序为东/西、上/下、北/南。
* **平滑迭代** (默认: 5): 定义要应用的平滑迭代次数。

<img src="../.gitbook/assets/ezmoss_amount.gif" alt="" data-size="original"> **`[amount]`**

<img src="../.gitbook/assets/ezmoss_radius.gif" alt="" data-size="original"> **`[smooth_radii]`**

<img src="../.gitbook/assets/ezmoss_radii.gif" alt="" data-size="original"> **`[smooth_radii]`**

<img src="../.gitbook/assets/ezmoss_iterations.gif" alt="" data-size="original"> **`[smooth_iterations]`**

</details>

### `//ezslabmerge`

<details>

<summary>平板合并</summary>

**`//ezslabmerge <mask> [-b] [-t]`**

**`别名: //slabmerge`**

* **蒙版**: 指定蒙版以选择区域内要影响的方块。
* **-b**: 使用时，也会将下半平板转换为完整方块。
* **-t**: 使用时，也会将上半平板转换为完整方块。

</details>

### `//ezstatecyle`

<details>

<summary>状态循环</summary>

**`//ezstatecycle <mask> <state>`**

**`别名: //statecycle`**

* **蒙版**: 指定蒙版以选择区域内要影响的方块。
* **状态**: 标识要为选区中每个方块循环的方块状态值。

</details>
