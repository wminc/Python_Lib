```py
class seaborn.FacetGrid(data, row=None, col=None, hue=None, col_wrap=None, sharex=True, sharey=True, height=3, aspect=1, palette=None, row_order=None, col_order=None, hue_order=None, hue_kws=None, dropna=True, legend_out=True, despine=True, margin_titles=False, xlim=None, ylim=None, subplot_kws=None, gridspec_kws=None, size=None)
```

用于绘制条件关系的多图网格。

```py
__init__(data, row=None, col=None, hue=None, col_wrap=None, sharex=True, sharey=True, height=3, aspect=1, palette=None, row_order=None, col_order=None, hue_order=None, hue_kws=None, dropna=True, legend_out=True, despine=True, margin_titles=False, xlim=None, ylim=None, subplot_kws=None, gridspec_kws=None, size=None)
```

初始化 matplotlib 画布和 FacetGrid 对象。

该类将数据集映射到由行和列组成的网格中的多个轴上，这些轴与数据集中变量的级别对应。它产生的图通常被称为“lattice”，“trellis”或“small-multiple”图形。

它还可以用`hue`参数表示第三个变量的级别，该参数绘制不同颜色的不同数据子集。它使用颜色来解析第三维度上的元素，但是只绘制相互重叠的子集，并且不会像接受“hue”的坐标轴级函数那样为特定的可视化定制“hue”参数。

当使用从数据集推断语义映射的 seaborn 函数时，必须注意在各个方面之间同步这些映射。在大多数情况下，使用图形级函数（例如[`relplot()`](https://seaborn.apachecn.org/#/seaborn.relplot.html?id=seaborn.relplot)或[`catplot()`](https://seaborn.apachecn.org/#/seaborn.catplot.html?id=seaborn.catplot)）比直接使用[`FacetGrid`](https://seaborn.apachecn.org/#/seaborn.FacetGrid.html?id=seaborn.facetgrid)更好。

基本工作流程是使用数据集和用于构造网格的变量初始化 FacetGrid 对象。然后，通过调用[`FacetGrid.map()`](https://seaborn.apachecn.org/#/seaborn.FacetGrid.map.html?id=seaborn.facetgrid.map)或[`FacetGrid.map_dataframe()`](https://seaborn.apachecn.org/#/seaborn.FacetGrid.map_dataframe.html?id=seaborn.facetgrid.map_dataframe)，可以将一个或多个绘图函数应用于每个子集。最后，可以使用其他方法调整绘图，以执行更改轴标签、使用不同刻度或添加图例等操作。有关详细信息，请参阅下面的详细代码示例。

#### 参数：

`data`：DataFrame 数据。

> 整洁的（“长形式”）dataframe 数据，其中每一列是一个变量，每一行是一个观察实例。

`row, col, hue`：字符串。

> 定义数据子集的变量，这些变量将在网格的不同方面绘制。请参阅`*_order`参数以控制此变量的级别顺序。

`col_wrap`：整形数值，可选参数。

> 以此参数值来限制网格的列维度，以便列面跨越多行。与`row`面不兼容。

`share{x,y}`：布尔值，'col' 或 'row'可选

> 如果为 true，则跨列共享 y 轴或者跨行共享 x 轴。

`height`：标量，可选参数。

> 每个图片的高度设定（以英寸为单位）。另见：*aspect*

`aspect`：标量，可选参数。

> 每个图片的纵横比，因此 aspect * height 给出每个图片的宽度，单位为英寸。

`palette`：调色板名称，列表或字典，可选参数。

> 用于色调变量的不同级别的颜色。应为[`color_palette()`](https://seaborn.apachecn.org/#/seaborn.color_palette.html?id=seaborn.color_palette)可以解释的参数，或者是将色调级别映射到 matplotlib 颜色的字典。

`{row,col,hue}_order`：列表，可选参数。

> 对所给命令级别进行排序。默认情况下，这将是在数据中显示的级别，或者，如果变量是 pandas 分类，则为类别顺序。

`hue_kws`：参数-列表值的映射字典

> 插入到绘图调用中的其他关键字参数，使得其他绘图属性在色调变量的级别上有所不同（例如散点图中的标记）。

`legend_out`：布尔值，可选参数。

> 如果为 True，则图形尺寸将被扩展，图例将绘制在中间右侧的图形之外。

`despine`：布尔值，可选参数。

> 从图中移除顶部和右侧边缘框架。

`margin_titles`：布尔值，可选参数。

> 如果为 True，则行变量的标题将绘制在最后一列的右侧。此选项是实验性的，可能无法在所有情况下使用。

`{x, y}lim`：元组，可选参数。

> 每个图片上每个轴的限制（仅当 share {x，y}为 True 时才相关）。

`subplot_kws`：字典，可选参数。

> 传递给 matplotlib subplot（s）方法的关键字参数字典。

`gridspec_kws`：字典，可选参数。

> 传递给 matplotlib 的`gridspec`模块（通过`plt.subplots`）的关键字参数字典。需要 matplotlib> = 1.4，如果`col_wrap`不是`None`，则忽略它。

**另请参见**

用于绘制成对关系的子图网格。

[`relplot`](https://seaborn.apachecn.org/#/docs/32?id=seaborn.relplot)

结合关系图和[`FacetGrid`](https://seaborn.apachecn.org/#/docs/32?id=seaborn.facetgrid)。

[`catplot`](https://seaborn.apachecn.org/#/docs/32?id=seaborn.catplot)

结合分类图和[`FacetGrid`](https://seaborn.apachecn.org/#/docs/32?id=seaborn.facetgrid)。

[`lmplot`](https://seaborn.apachecn.org/#/docs/32?id=seaborn.lmplot)

结合回归图和[`FacetGrid`](https://seaborn.apachecn.org/#/docs/32?id=seaborn.facetgrid)。

范例

使用 tips 数据集初始化 2x2 网格图：

```py
>>> import seaborn as sns; sns.set(style="ticks", color_codes=True)
>>> tips = sns.load_dataset("tips")
>>> g = sns.FacetGrid(tips, col="time", row="smoker")
```

![http://seaborn.pydata.org/_images/seaborn-FacetGrid-1.png](https://seaborn.apachecn.org/docs/img/b8699392ad92687d3ac264d00b00ec9b.jpg)