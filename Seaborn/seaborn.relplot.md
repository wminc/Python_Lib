```python
seaborn.relplot(x=None, y=None, hue=None, size=None, style=None, data=None, row=None, col=None, col_wrap=None, row_order=None, col_order=None, palette=None, hue_order=None, hue_norm=None, sizes=None, size_order=None, size_norm=None, markers=None, dashes=None, style_order=None, legend='brief', kind='scatter', height=5, aspect=1, facet_kws=None, **kwargs)
```
此函数提供对一些不同轴级别函数的访问，这些函数通过子集的语义映射显示两个变量之间的关系。

`kind`参数选择要使用的基础轴级函数：

`scatterplot()  也可以  relplot(kind="scatter")；默认为此`

`lineplot()  也可以   relplot(kind="line") `  

对于数据不同子集的`x`与`y`的绘制关系可以通过`hue`, `size`以及`style`参数控制。绘制后，会返回带有图像的[`FacetGrid`](https://seaborn.apachecn.org/#/seaborn.FacetGrid.html?id=seaborn.facetgrid)

#### 参数：

- `x, y`：`data`中的变量名

  > 输入数据的变量；数据必须为数值型。

- `hue`: `data`中的名称，可选

  > 将会产生具有不同颜色的元素的变量进行分组。这些变量可以是类别变量或者数值型变量，尽管颜色映射在后面的情况中会有不同的表现。

- `size`：`data`中的名称，可选

  > 将会产生具有不同尺寸的元素的变量进行分组。这些变量可以是类别变量或者数值型变量，尽管尺寸映射在后面的情况中会有不同的表现。

- `style`：`data`中的名称，可选

  > 将会产生具有不同风格的元素的变量进行分组。这些变量可以为数值型，但是通常会被当做类别变量处理。

- `data`：DataFrame

  > 长格式的 DataFrame，每列是一个变量，每行是一个观察值。

- `row, col`：`data`中的变量名，可选

  > 确定网格的分面的类别变量。

- `col_wrap`：int, 可选

  >以此宽度“包裹”列变量，以便列分面跨越多行。与`row`分面不兼容。

- `row_order, col_order`：字符串列表，可选

  > 以此顺序组织网格的行和/或列，否则顺序将从数据对象中推断。

- `palette`：色盘名，列表，或者字典，可选

  > 用于`hue`变量的不同级别的颜色。应当是[`color_palette()`](https://seaborn.apachecn.org/#/seaborn.color_palette.html?id=seaborn.color_palette)可以解释的东西，或者将色调级别映射到 matplotlib 颜色的字典。

- `hue_order`：列表，可选

  > 指定`hue`变量层级出现的顺序，否则会根据数据确定。当`hue`变量为数值型时与此无关。

- `hue_norm`：元组或者 Normalize 对象，可选

  > 当`hue`变量为数值型时，用于数据单元的 colormap 的标准化。如果`hue`为类别变量则与此无关。

- `sizes`：列表、典或者元组，可选

  > 当使用`sizes`时，用于确定如何选择尺寸。此变量可以一直是尺寸值的列表或者`size`变量的字典映射。当`size`为数值型时，此变量也可以是指定最小和最大尺寸的元组，这样可以将其他值标准化到这个范围。

- `size_order`：列表，可选

  > 指定`size`变量层次的表现顺序，不指定则会通过数据确定。当`size`变量为数值型时与此无关。

- `size_norm`：元组或者 Normalize 对象，可选

  > 当`size`变量为数值型时，用于数据单元的 scaling plot 对象的标准化。

- `legend`：“brief”, “full”, 或者 False, 可选

  > 用于决定如何绘制坐标轴。如果参数值为“brief”, 数值型的`hue`以及`size`变量将会被用等间隔采样值表示。如果参数值为“full”, 每组都会在坐标轴中被记录。如果参数值为“false”, 不会添加坐标轴数据，也不会绘制坐标轴。

- `kind`：string, 可选

  > 绘制图的类型，与 seaborn 相关的图一致。可选项为(`scatter`及`line`).

- `height`：标量, 可选

  > 每个 facet 的高度（英寸）。参见`aspect`。

- `aspect`：标量, 可选

  > 每个 facet 的长宽比，因此“长宽比*高度”可以得出每个 facet 的宽度（英寸）。

- `facet_kws`：dict, 可选

  > 以字典形式传给[`FacetGrid`](https://seaborn.apachecn.org/#/seaborn.FacetGrid.html?id=seaborn.facetgrid)的其他关键字参数.

- `kwargs`：键值对

  > 传给后续绘制函数的其他关键字参数。

#### 返回值：

`g`：[`FacetGrid`](https://seaborn.apachecn.org/#/seaborn.FacetGrid.html?id=seaborn.facetgrid)

> 返回包含图像的[`FacetGrid`](https://seaborn.apachecn.org/#/seaborn.FacetGrid.html?id=seaborn.facetgrid)对象，图像可以进一步调整。