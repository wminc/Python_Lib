> 本学习过程是根据官方文档学习https://seaborn.apachecn.org/#/docs/3

seaborn一共有5个大类21种图

- Relational plots 关系类图表 
    1. relplot() 关系类图表的接口，其实是下面两种图的集成，通过指定kind参数可以画出下面的两种图
    2. scatterplot() 散点图
    3. lineplot() 折线图
- Categorical plots 分类图表 
    1. catplot() 分类图表的接口，其实是下面八种图表的集成，通过指定kind参数可以画出下面的八种图
    2. stripplot() 分类散点图
    3. swarmplot() 能够显示分布密度的分类散点图
    4. boxplot() 箱图
    5. violinplot() 小提琴图
    6. boxenplot() 增强箱图
    7. pointplot() 点图
    8. barplot() 条形图
    9. countplot() 计数图
- Distribution plot 分布图 
    1. jointplot() 双变量关系图
    2. pairplot() 变量关系组图
    3. distplot() 直方图，质量估计图
    4. kdeplot() 核函数密度估计图
    5. rugplot() 将数组中的数据点绘制为轴上的数据
- Regression plots 回归图 
    1. lmplot() 回归模型图
    2. regplot() 线性回归图
    3. residplot() 线性回归残差图
    4. Matrix plots 矩阵图 
    5. heatmap() 热力图
    6. clustermap() 聚集图