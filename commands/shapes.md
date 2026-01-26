# 形状

所有子命令都在 `//ezshapes` (`//ezsh`) 下  
例如 `//ezshapes polydome`

## `//ezshapes ...`

### `cone`

<details>

<summary>圆锥</summary>

**`//ezsh cone <pattern> <radii> <height> [rotation] [-dhos]`**

* **Pattern**: 指定方块图案。
* **Radii**: 定义圆锥的半径。第一个值用于南北方向，第二个值用于东西方向。如果圆锥旋转，这些方向可能会改变。
* **Height**: 设置圆锥的高度。
* **Rotation** (默认值: 0): 确定围绕 y 轴的旋转角度（以度为单位）。如果使用 `-o` 开关，可以与玩家的瞄准方向对齐。
* **-d**: 激活时，生成尖端朝下的圆锥。
* **-h**: 生成空心形状。
* **-o**: 使用时，考虑玩家的瞄准方向来旋转圆锥。
* **-s**: 使用时，玩家的选区将移动到大致覆盖该形状的位置

</details>

### `polydome`

<details>

<summary>多边形穹顶</summary>

**`//ezsh polydome <pattern> <sides> <radius> <height> [-vs]`**

* **Pattern**: 指定方块图案。
* **Sides**: 定义多边形穹顶的边数。
* **Radius**: 设置多边形穹顶的半径。
* **Height** (默认值: 1): 确定穹顶的高度。
* **-v**: 指定顶点图案，改变多边形穹顶顶点处的外观。
* **-s**: 使用时，玩家的选区将移动到大致覆盖该形状的位置

</details>

### `polygon`

<details>

<summary>多边形</summary>

**`//ezsh polygon <pattern> <sides> <radius> <height> [direction] [-s]`** 

* **Pattern**: 指定方块图案。
* **Sides**: 定义多边形的边数。
* **Radius**: 设置多边形的半径。
* **Height** (默认值: 1): 确定多边形的高度。
* **Direction** (默认值: 玩家瞄准方向): 指定放置的方向，可以包括对角线方向。
* **-s**: 使用时，玩家的选区将移动到大致覆盖该形状的位置

</details>

### `square`

<details>

<summary>正方形</summary>

**`//ezsh square <pattern> <radius> <height> [-fws]`**

* **Pattern**: 指定方块图案。
* **Radius**: 设置正方形的半径。
* **Height** (默认值: 1): 确定正方形的高度。
* **-f**: 激活时，仅生成正方形的面。
* **-w**: 使用时，仅生成正方形的墙壁。
* **-s**: 使用时，玩家的选区将移动到大致覆盖该形状的位置

</details>

### `tetrahedron`

<details>

<summary>四面体</summary>

**`//ezsh tetrahedron <pattern> <radius> [rotation] [-hos]`**

* **Pattern**: 指定方块图案。
* **Radius**: 设置四面体的大小。
* **Rotation** (默认值: 0): 确定围绕 y 轴的旋转角度（以度为单位）。如果使用 -o 开关，可以与玩家的瞄准方向对齐。
* **-h**: 生成空心形状。
* **-o**: 使用时，考虑玩家的瞄准方向来旋转四面体。
* **-s**: 使用时，玩家的选区将移动到大致覆盖该形状的位置

</details>

### `torus`

<details>

<summary>圆环</summary>

**`//ezsh torus <pattern> <major_radius> <minor_radius> <cross_section> [-hos]`**

* **Pattern**: 指定方块图案。
* **Major Radius**: 设置圆环的大半径。
* **Minor Radius**: 设置圆环的小半径。
* **Cross Section**: 确定圆环的截面形状：
  * `CIRCLE`
  * `DIAMOND`
  * `ROUNDED_SQUARE`
  * `SQUARE`

* **-h**: 生成空心形状。
* **-o**: 使用时，圆环的旋转与玩家的瞄准方向对齐
* **-s**: 使用时，玩家的选区将移动到大致覆盖该形状的位置

</details>
