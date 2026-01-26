# 染色玻璃

与使用染色玻璃进行着色相关的命令。

### `//ezstainedglassgradient`

<details>

<summary>玻璃渐变</summary>

**`//ezstainedglassgradient <startColor> [endColor] <layers> [length] [quality] [direction] [-c <backgroundColor>] [-bs]`**

**`别名: //stainedglassgradient, //glassgradient`**

* **StartColor**: 指定渐变的起始颜色（十六进制代码）。
* **EndColor** (默认值: 无): 指定渐变的结束颜色（十六进制代码）。如果未提供值，则整个渐变将使用起始颜色。
* **Layers**: 创建渐变时使用多少层玻璃。
* **Length** (默认值: 1): 渐变应该有多少方块长。
* **Quality** (默认值: 7): 渐变应该有多精确。较高的值可能需要更长的运行时间。
* **-c** (默认值: #000000): 指定渐变所在的背景颜色（十六进制代码），如果未使用 **-b** 标志。
* **-b**: 查找最接近的实心方块放在玻璃后面以提高色彩准确度。这需要更多的资源。
* **-s**: 跳过重复的层组合。

</details>