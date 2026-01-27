# 调色板详解

ezEdits 中的调色板代表一个方块列表，可以在多个命令中使用，其中方块的顺序将被保持。

调色板可以使用 **`#`** 前缀保存和访问用户保存的调色板，使用 **`##`** 访问[内置预设调色板](default-palettes.md)。

作为参考，这里有一个例子：

<figure><img src="../.gitbook/assets/palette_Grayscale.png" alt=""><figcaption><p>##Grayscale</p></figcaption></figure>

使用调色板的众多功能包括：

* `//eztexture ...` - [纹理命令](../commands/texturing.md)
* `#palette` - [调色板蒙版](../masks-and-patterns/masks.md#palette-mask)
* `//ezbrush gradient ...` - [笔刷](../brushes-and-tools/brushes/)

调色板可以构建为简单的方块列表，或通过几个修饰符：

* **`,`** - <mark style="color:orange;">**连接**</mark>：
  * 将一个方块或调色板添加到前面方块或调色板的末尾。\
    例如 `stone,dirt` 是一个包含石头和泥土的 2 方块调色板。`stone,##Grayscale` 是一个由石头和 ##Grayscale 预设调色板的方块组成的调色板。
* **`-`** - <mark style="color:orange;">**反转**</mark>：
  * 反转调色板的顺序。\
    例如 `-##Grayscale` 是反向顺序的 ##Grayscale 预设调色板（从白色开始而不是黑色）
* **`(start:end)`** - <mark style="color:orange;">**子调色板**</mark>：
  * 返回调色板的一部分。\
    例如 `##Grayscale(1:8)` 将返回 ##Grayscale 预设调色板的前 8 个方块。
* **`*`** - <mark style="color:orange;">**重复器**</mark>：
  * 将前一个片段重复给定次数。\
    例如 `gold_block*10,diamond_block` 将返回一个包含 10 个金块，后跟一个钻石块的调色板。
* **`[]`** - <mark style="color:orange;">**分组**</mark>：
  * 将调色板分组在一起，允许修饰符将它们视为单个调色板。\
    例如 `-##Grayscale,gold_block` 将返回反向顺序的 ##Grayscale 预设调色板，末尾带有一个金块。而 `-[##Grayscale,gold_block]` 将在开头返回金块。
* **`=`** - <mark style="color:orange;">**结果**</mark>：
  * 允许在需要时将调色板自动补全为其方块列表。

### 视频教程

[MegRae](https://megrae.art/) 也制作了一个关于调色板的教程：

{% embed url="https://youtu.be/VGsTle3g9AU" %}
