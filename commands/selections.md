# 选区

## 选区命令

### `//selload`

<details>

<summary>加载选区</summary>

**`//selload [selection] [-h]`**

*`//ezsel load` 的替代命令*

`//selload` 命令从玩家已保存的选区列表中检索之前保存的选区。

* Selection: 之前保存的选区。
* **-h**: 加载时将选区移动到玩家位置

</details>

### `//next`

<details>
<summary>选区移位</summary>

**`//next <direction> <gap>`**

`//next` 命令将您当前的选区按其自身大小在指定方向上移动。

* **Direction**（默认值：玩家视线方向）: 指定要移动选区的方向。如果未提供，则默认为玩家的视线方向。
* **Gap**（默认值：0）: 可选参数，用于在当前选区位置和移动后的位置之间添加额外间隔。

</details>

### `//selhere`

<details>

<summary>将选区移动到玩家位置</summary>

**`//selhere [selectionPosition]`**

**`别名: //seltome`**

`//selhere` 命令将您当前的选区移动到您的位置。

* **SelectionPosition**（默认值：POS1）: 指定选区中的哪个点要移动到玩家位置。所有其他点将相对移动。
  * POS1 - 选区的"Pos1"，或凸选区/多边形选区的第一个点。
  * POS2 - 选区的"Pos2"，或凸选区/多边形选区的最后一个点。
  * CENTER - 选区的中心点

</details>

### `//ezselinvert`

<details>

<summary>反转选区</summary>

**`//ezselinvert`**

**`别名: //selinvert`**

`//ezselinvert` 命令反转您当前选区中的点的顺序。\
这在凸选区中最为明显，因为对于长方体选区，pos1 和 pos2 只会简单地交换位置，而凸选区将反转每个点的顺序。

</details>

### `//delpos2`

<details>

<summary>删除最后一个位置</summary>

**`//delpos2`**

**`别名: //-2`**

`//delpos2` 命令移除凸选区和多边形选区的最后一个次要选区点。

</details>

### `//encapsulate`

<details>
<summary>在选区中封装方块</summary>

**`//encapsulate <mask>`**

**`别名: //enc`**

`//encapsulate` 命令获取您现有的选区，并将其更改为包含与给定蒙版匹配的方块的最小长方体选区。

* **Mask**: 要封装的方块

</details>

### `//encapsulatenear`

<details>
<summary>在新选区中封装附近的方块</summary>

**`//encapsulatenear <radius> <mask>`**

**`别名: //encnear`**

`//encapsulatenear` 命令创建一个新选区，为包含半径内与给定蒙版匹配的方块的最小长方体选区。

* **Radius**: 用于搜索匹配方块的长方体半径
* **Mask**: 要封装的方块

</details>

## 选区管理命令

所有子命令都在 `//ezselection`（`//ezsel`）下\
例如 `//ezsel list`

### `list [-g]`

列出用户所有已保存的选区。点击选区名称可加载。\
使用 `-g` 按类型分组选区。

### `load <selection>`

从玩家已保存的选区列表中检索之前保存的选区。

### `save <selectionName> [-f]`

使用给定名称保存用户当前的选区。\
使用 `-f` 覆盖现有的已保存选区。

### `delete <selectionName>`

删除具有给定名称的用户选区。