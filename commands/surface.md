# 表面

所有子命令都在 `//ezsurface` (`//ezsu`) 下\
例如 `//ezsurface rockify`

## `//ezsurface ...`

### `fuzzify`

<details>

<summary>模糊化表面</summary>

**`//ezsu fuzzify <radius> [smooth_radius] [smooth_iterations] [-c] [-e] [-m] [-t] [-w <profile>]`**

使用白噪声使表面显得更加模糊。

* **半径**: 浮点值，确定距表面的最大距离，在此范围内可进行修改。
* **平滑半径** (默认值: 0): 指定平滑操作的半径。
* **平滑迭代次数** (默认值: 0): 确定平滑操作应用的次数。
* **-c**: 限制修改仅挖掘地形。
* **-e**: 限制操作仅向外扩展地形。
* **-m**: 应用蒙版以仅修改与指定条件匹配的表面。\
  由于需要匹配表面的复杂性，此选项可能会显著降低处理速度。
* **-t**: 尝试保留该区域的拓扑结构。
* **-w**: 参见 [Smoothblocks](../smoothblocks/smoothblocks.md)。

</details>

### `rockify`

<details>

<summary>岩石化表面</summary>

**`//ezsu rockify <radius> [size] [oct] [smooth_radius] [smooth_iterations] [-c] [-e] [-m] [-t] [-w <profile>]`**

使用 Perlin 噪声使表面看起来岩石化。

* **半径**: 浮点值，确定距表面的最大距离，在此范围内可进行修改。
* **噪声大小** (默认值: 10): 控制所用噪声的规模。
* **噪声八度** (默认值: 1): 设置应用的噪声层数。
* **平滑半径** (默认值: 1): 指定平滑操作的半径。
* **平滑迭代次数** (默认值: 4): 确定平滑操作应用的次数。
* **-c**: 限制修改仅挖掘地形。
* **-e**: 限制操作仅向外扩展地形。
* **-m**: 应用蒙版以仅修改与指定条件匹配的表面。\
  由于需要匹配表面的复杂性，此选项可能会显著降低处理速度。
* **-t**: 尝试保留该区域的拓扑结构。
* **-w**: 参见 [Smoothblocks](../smoothblocks/smoothblocks.md)。

</details>

### `voronoify`

<details>

<summary>Voronoi 化表面</summary>

**`//ezsu voronoify <radius> [cell_size] [smooth_radius] [smooth_iterations] [-c] [-e] [-m] [-t] [-w <profile>]`**

使用 Voronoi 噪声来变形表面。

* **半径**: 浮点值，确定距表面的最大距离，在此范围内可进行修改。
* **单元格大小** (默认值: 12): 确定 Voronoi 图案中每个单元格的平均大小，影响纹理的规模。
* **平滑半径** (默认值: 0): 指定平滑操作的半径。
* **平滑迭代次数** (默认值: 0): 确定平滑操作应用的次数。
* **-c**: 限制修改仅挖掘地形。
* **-e**: 限制操作仅向外扩展地形。
* **-m**: 应用蒙版以仅修改与指定条件匹配的表面。\
  由于需要匹配表面的复杂性，此选项可能会显著降低处理速度。
* **-t**: 尝试保留该区域的拓扑结构。
* **-w**: 参见 [Smoothblocks](../smoothblocks/smoothblocks.md)。

</details>

### `noisify`

<details>

<summary>噪声化表面</summary>

**`//ezsu noisify <radius> <noise> [scale] [smooth_radius] [smooth_iterations] [-c] [-e] [-m] [-t] [-w <profile>]`**

使用噪声预设来变形表面。

* **半径**: 浮点值，确定距表面的最大距离，在此范围内可进行修改。
* **噪声**: 指定用于修改的噪声。
* **规模** (默认值: 1): 调整噪声的规模。
* **平滑半径** (默认值: 1): 指定平滑操作的半径。
* **平滑迭代次数** (默认值: 4): 确定平滑操作应用的次数。
* **-c**: 限制修改仅挖掘地形。
* **-e**: 限制操作仅向外扩展地形。
* **-m**: 应用蒙版以仅修改与指定条件匹配的表面。\
  由于需要匹配表面的复杂性，此选项可能会显著降低处理速度。
* **-t**: 尝试保留该区域的拓扑结构。
* **-w**: 参见 [Smoothblocks](../smoothblocks/smoothblocks.md)。

</details>