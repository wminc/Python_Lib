```py
seaborn.jointplot(x, y, data=None, kind='scatter', stat_func=None, color=None, height=6, ratio=5, space=0.2, dropna=True, xlim=None, ylim=None, joint_kws=None, marginal_kws=None, annot_kws=None, **kwargs)
```

绘制两个变量的双变量及单变量图。

这个函数提供调用[`JointGrid`](https://seaborn.apachecn.org/#/seaborn.JointGrid.html?id=seaborn.jointgrid)类的便捷接口，以及一些封装好的绘图类型。这是一个轻量级的封装，如果需要更多的灵活性，应当直接使用[`JointGrid`](https://seaborn.apachecn.org/#/seaborn.JointGrid.html?id=seaborn.jointgrid).

#### 参数：
`x, y`：strings 或者 vectors

> `data`中的数据或者变量名。

`data`：DataFrame, 可选

> 当`x`和`y`为变量名时的 DataFrame.

`kind`：{ “scatter” | “reg” | “resid” | “kde” | “hex” }, 可选

> 绘制图像的类型。

`stat_func`：可调用的，或者 None, 可选

> 已过时

`color`：matplotlib 颜色, 可选

> 用于绘制元素的颜色。

`height`：numeric, 可选

> 图像的尺寸（方形）。

`ratio`：numeric, 可选

> 中心轴的高度与侧边轴高度的比例

`space`：numeric, 可选

> 中心和侧边轴的间隔大小

`dropna`：bool, 可选

> 如果为 True, 移除`x`和`y`中的缺失值。

`{x, y}lim`：two-tuples, 可选

> 绘制前设置轴的范围。

`{joint, marginal, annot}_kws`：dicts, 可选

> 额外的关键字参数。

`kwargs`：键值对

> 额外的关键字参数会被传给绘制中心轴图像的函数，取代`joint_kws`字典中的项。

#### 返回值：

`grid`：[`JointGrid`](https://seaborn.apachecn.org/#/seaborn.JointGrid.html?id=seaborn.jointgrid)

> [`JointGrid`](https://seaborn.apachecn.org/#/seaborn.JointGrid.html?id=seaborn.jointgrid)对象.