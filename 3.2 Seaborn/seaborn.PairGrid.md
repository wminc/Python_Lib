```py
class seaborn.PairGrid(data, hue=None, hue_order=None, palette=None, hue_kws=None, vars=None, x_vars=None, y_vars=None, diag_sharey=True, height=2.5, aspect=1, despine=True, dropna=True, size=None)
```

用于绘制数据集中成对关系的子图网格。

此类将数据集中的每个变量映射到多个轴的网格中的列和行。可以使用不同的轴级绘图函数来绘制上三角和下三角的双变量图，并且对角线上可以显示每个变量的边际分布。

它还可以通过`hue`参数用不同颜色绘制不同的数据子集来表示附加级别的条件化。这使用颜色来解析第三维的元素，但只是在彼此之上绘制子集，并且不会像接受`hue`的轴级函数那样为特定可视化定制`hue`参数。

参考[教程](https://seaborn.apachecn.org/#/../tutorial/axis_grids.html?id=grid-tutorial)获取更多信息。

```py
__init__(data, hue=None, hue_order=None, palette=None, hue_kws=None, vars=None, x_vars=None, y_vars=None, diag_sharey=True, height=2.5, aspect=1, despine=True, dropna=True, size=None)
```

初始化绘图和 PairGrid 对象。

#### 参数：

`data`：DataFrame 格式

> 整洁（长形式）数据框，其中每列是一个变量，每行是一个观察。

`hue`：字符串 （变量名）, 可选

> `data`中的变量，将绘图的不同面映射为不同的颜色。

`hue_order`：字符串列表

> 调色板中色调变量的等级顺序

`palette`：字典或者 seaborn 调色板

> 用于映射`hue`变量的颜色集.如果是一个字典，键应为`hue`变量中的值。

`hue_kws`：参数字典 -> 值列表映射

> 其它的关键字参数，通过插入到绘图调用中使得其它的绘图属性在色调变量的不同水平上变化（例如散点图中的标记）。

`vars`：变量名列表, 可选

> 使用`data`中的变量，否则使用一个数值型数据类型的每一列。

`{x, y}_vars`：变量名列表，可选

> 将`data`中的变量分别用于图的行和列，即制作非方形图。

`height`：标量，可选

> 每个刻面的高度（以英寸为单位）。

`aspect`：标量，可选

> aspect 和 height 的乘积得出每个刻面的宽度（以英寸为单位）。

`despine`：布尔值，可选

> 从图中移除顶部和右侧脊柱。

`dropna`：布尔值，可选

> 在绘图之前删除数据中的缺失值。

例子

为每个成对关系绘制一个散点图：

```py
>>> import matplotlib.pyplot as plt
>>> import seaborn as sns; sns.set()
>>> iris = sns.load_dataset("iris")
>>> g = sns.PairGrid(iris)
>>> g = g.map(plt.scatter)
```

![http://seaborn.pydata.org/_images/seaborn-PairGrid-1.png](https://seaborn.apachecn.org/docs/img/34fc6de3cfc117757cc0e5f658a06928.jpg)