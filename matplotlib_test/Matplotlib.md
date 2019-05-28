# Matplotlib

pip install matplotlib    ———完事儿

pip install NumPy       ————ok

### 线条相关属性标记设置

axex: 设置坐标轴边界和表面的颜色、坐标刻度值大小和网格的显示
backend: 设置目标暑促TkAgg和GTKAgg
figure: 控制dpi、边界颜色、图形大小、和子区( subplot)设置
font: 字体集（font family）、字体大小和样式设置
grid: 设置网格颜色和线性
legend: 设置图例和其中的文本的显示
line: 设置线条（颜色、线型、宽度等）和标记
patch: 是填充2D空间的图形对象，如多边形和圆。控制线宽、颜色和抗锯齿设置等。
savefig: 可以对保存的图形进行单独设置。例如，设置渲染的文件的背景为白色。
verbose: 设置matplotlib在执行期间信息输出，如silent、helpful、debug和debug-annoying。
xticks和yticks: 为x,y轴的主刻度和次刻度设置颜色、大小、方向，以及标签大小。

### 用来该表线条的属性

| 线条风格linestyle或ls | 描述   | 线条风格linestyle或ls | 描述       |
| --------------------- | ------ | --------------------- | ---------- |
| ‘-‘                   | 实线   | ‘:’                   | 虚线       |
| ‘–’                   | 破折线 | ‘None’,’ ‘,’’         | 什么都不画 |
| ‘-.’                  | 点划线 |                       |            |

### 线条标记

| 标记maker | 描述    | 标记 | 描述             |
| --------- | ------- | ---- | ---------------- |
| ‘o’       | 圆圈    | ‘.’  | 点               |
| ‘D’       | 菱形    | ‘s’  | 正方形           |
| ‘h’       | 六边形1 | ‘*’  | 星号             |
| ‘H’       | 六边形2 | ‘d’  | 小菱形           |
| ‘_’       | 水平线  | ‘v’  | 一角朝下的三角形 |
| ‘8’       | 八边形  | ‘<’  | 一角朝左的三角形 |
| ‘p’       | 五边形  | ‘>’  | 一角朝右的三角形 |
| ‘,’       | 像素    | ‘^’  | 一角朝上的三角形 |
| ‘+’       | 加号    | ’\‘  | 竖线             |
|           |         |      |                  |

## 颜色

可以通过调用`matplotlib.pyplot.colors()`得到matplotlib支持的所有颜色。

| 别名 | 颜色   | 别名 | 颜色 |      |
| ---- | ------ | ---- | ---- | ---- |
| b    | 蓝色   | g    | 绿色 |      |
| r    | 红色   | y    | 黄色 |      |
| c    | 青色   | k    | 黑色 |      |
| m    | 洋红色 | w    | 白色 |      |

输出图像到文件中的格式有，emf、 eps、 pdf、 png、 ps、 raw、 rgba、 svg、 svgz

```python
np.random.randint(0, 50, 50)
```

（x最小值，y最大值不包括，生成量）

```python
np.random.randint(0, 50, size=(2,3))
```

size=(几组数据，每组几个)

```python
np.random.randn(50)
```

通过本函数可以返回一个或一组服从**标准正态分布**的随机样本值。

在-1.96～+1.96范围内曲线下的面积等于0.9500（即取值在这个范围的概率为95%），在-2.58～+2.58范围内曲线下面积为0.9900（即取值在这个范围的概率为99%）. 
因此，由 np.random.randn()函数所产生的随机样本基本上取值主要在-1.96~+1.96之间，当然也不排除存在较大值的情形，只是概率较小而已。

![scatter](C:\Users\hj137\Desktop\scatter.png)

![s2](C:\Users\hj137\Desktop\s2.png)

[官方文档](https://matplotlib.org/tutorials/introductory/pyplot.html#sphx-glr-tutorials-introductory-pyplot-py)

