### matplotlib折线图


```python
import matplotlib as mpl
import matplotlib.pyplot as plt
x = [1,3,5,7]
y = [4,9,6,8]
plt.plot(x,y)
plt.show()
```
创建figure（画布）的两种方式

1. 隐式创建figure对象

   当第一次执行plt.xxx()画图代码时，系统会去判断是否已经有了figure对象，如果没有，系统会自动创建一个figure对象，并且在这个figure之上，自动创建一个axes坐标系(注意：默认创建一个figure对象，一个axes坐标系)。

   如果figure对象是被默认创建的，那么我们根本拿不到axes对象。

2. 显示创建figure对象

	```python
	# 手动创建一个figure对象
	figure = plt.figure()
	# 获取每个位置的axes对象
	axes1 = figure.add_subplot(2,1,1)
	axes2 = figure.add_subplot(2,1,1)
	axes1.plot([1,3,5,7],[4,9,6,8])
	axes2.plot([1,2,4,5],[8,4,6,2])
	figure.show()
	```
   如果绘制一个简单的小图形，我们可以不设置figure对象，使用默认创建的figure对象，当然我们也可以显示创建figure对象。
   如果一张figure画布上，需要绘制多个图形。那么就必须显示的创建figure对象，然后得到每个位置上的axes对象，进行对应位置上的图形绘制。

```javascript
* figure 画布
* axes 坐标系，一个画布上可以有多个坐标系
* axis 坐标轴，一个坐标系中可以有多个坐标轴，一般都是二维平面坐标系，或者三维立体坐标系
* title 标题
* legend 图例
* grid 背景网格
* tick 刻度
* axis label 坐标轴名称
* tick label 刻度名称
   * major tick label 主刻度标签
   * minor tick label 副刻度标签
* line 线
* style 线条样式
* marker 点标记
* font 字体相关
```

```python
# 画正弦函数图像
import numpy as np  
import matplotlib.pyplot as plt  # 计算正弦曲线上点的 x 和 y 坐标 
x = np.arange(0,  3  * np.pi,  0.1)  
y = np.sin(x) 
plt.title("sine wave form")   # 使用 matplotlib 来绘制点 
plt.xlabel("x axis caption") 
plt.ylabel("y axis caption")
plt.plot(x, y，“ob”)  #用蓝色圆圈标记
plt.show()
```

`plot()` 蓝色b，绿色g，红色r，青色c，品红m，黄色y，黑色k，白色w

#### legend()

```python
plt.legend((u'头等舱', u'2等舱',u'3等舱'),loc='best',prop=myfont)
```

loc可用参数：

```
'best'         : 0, (自适应方式)
'upper right'  : 1,
'upper left'   : 2,
'lower left'   : 3,
'lower right'  : 4,
'right'        : 5,
'center left'  : 6,
'center right' : 7,
'lower center' : 8,
'upper center' : 9,
'center'       : 10,
```

#### annotate()

`Axes.annotate(s, xy, \*args, **kwargs)`用于在图形上给数据添加文本注解，而且支持带箭头的划线工具，方便我们在合适的位置添加描述信息。

s：注释文本的内容
xy：被注释的坐标点，二维元组形如(x,y)
xytext：注释文本的坐标点，也是二维元组，默认与xy相同
xycoords：被注释点的坐标系属性，允许输入的值如下

```python
for xy in zip(x, cov_cumulative):
		plt.annotate("(%s,%s)" % xy, xy=xy, xytext=(-20, 10), textcoords='offset points')
```

更详细参数：https://www.cnblogs.com/Rvin/p/9303901.html

