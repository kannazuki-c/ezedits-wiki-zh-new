# 调色板命令

所有子命令都在 `//ezpalette` (`//ezp`) 下\
例如 `//ezpalette list`

## `//ezpalette ...`

### `fetch <fetchMode> <paletteName> [length] [-d <direction>] [-f]`

<details>

<summary>获取调色板</summary>

使用给定名称保存用户定义的调色板。

* **获取模式**：从何处获取调色板方块：
  * **`WORLD`**
    * 从玩家所在位置获取方块
  * **`SELECTION`**
    * 从玩家的选区获取方块
    * 选区大小必须为 1x1xN，其中 N 是所需的调色板长度
  * **`HOTBAR`**
    * 从玩家的快捷栏获取方块
    * 忽略物品并使用默认方块属性
* **长度**（默认：0）：要获取多少个方块。长度为 0（默认）将获取方块直到遇到空气。
* **-d**（默认：me）：获取的方向。默认为用户面向的方向。
* **-f**：激活时，覆盖同名的现有调色板。

<img src="../.gitbook/assets/ezp_fetch.gif" alt="" data-size="original">

</details>

### `save <paletteName> <palette> [-f]`

使用给定名称保存用户定义的调色板。

* **-f**：激活时，覆盖同名的现有调色板。

### `delete <paletteName>`

删除与给定名称匹配的用户定义调色板。

### `list [SET]`

* `ALL`\
  列出所有可用的调色板
* `DEFAULT`\
  列出所有默认插件调色板
* `MINE`\
  列出所有用户定义的调色板

### `place <palette> [direction]`

在世界中将调色板作为一行方块放置在给定方向上。\
方向默认为用户面向的方向。

### `swap <sourcePalette> <targetPalette> [-a] [-f]`

区域操作，将源调色板的方块与目标调色板的方块交换。

* **-a**：激活以忽略源调色板中的空气方块。
* **-s**：激活以拉伸目标调色板以匹配源调色板的大小。
* **-f**：启用模糊匹配模式。忽略源调色板的方块状态。
* **-b**：将方块状态从源调色板方块复制到目标调色板。

### `print <palette> [-v]`

在聊天中打印给定调色板的方块。方块列表可点击复制。

**-v**：详细模式。将打印完整的方块名称和方块状态。

### `encode <palette>`

打印表示给定调色板的编码字符串。点击字符串以复制。\
_仅支持原版 Minecraft 方块。_

### `decode <string>`

打印给定编码调色板字符串的方块。方块列表可点击复制。
