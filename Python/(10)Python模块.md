# 模块



### 一、模块导入

##### 导入整个模块

使用 import 语句导入指定模块，导入后可以使用改模块中的所有函数。格式为模块名+函数名。

```python
import module_name

module_name.function_name()
```

##### 导入特定函数

```python
from module_name import function_1, function_2, function_3
```

##### 使用 as 指定别名

```python
from module_name import function_name as fn
import module_name as mn
```

##### 导入模块中的所有函数

```python
from module_name import *
```

由于导入了每个函数，可通过名称来调用每个函数，而无需使用点句表示法。然而，使用并非自己编写的大型模块时，最好不要使用这种导入方法：如果模块中有函数名称与你的项目中使用的名称相同，可能导致意料之外的错误。

> 问题1:
>
> Linux环境中自定义的模块basic，import basic 出错。basic 模块在/quoteEastmoney/目录下。
>
> 解决：
>
> 两种方法：
> **1. 在导入模块之前（每个.py文件都需要加）**
>
> import sys
> sys.path.append('/quoteEastmoney/')
>
> **2. 更改环境变量（一次修改永久生效）**
>
> 管理员权限修改：/etc/profile。在最后一行加上
>
> export PYTHONPATH=$PYTHONPATH:/quoteEastmoney/
>
> 运行 source /etc/profile

 每个模块都有一个__name__属性，当其值是'__main__'时，表明该模块自身在运行，否则是被引入。

说明：**__name__** 与 **__main__** 底下是双下划线， **_ _** 是这样去掉中间的那个空格。

### 二、dir() 函数

内置的函数 dir() 可以找到模块内定义的所有名称。以一个字符串列表的形式返回;如果没有给定参数，那么 dir() 函数会罗列出当前定义的所有名称。

### 三、包

包是一种管理 Python 模块命名空间的形式，采用"点模块名称"。

比如一个模块的名称是 A.B， 那么他表示一个包 A中的子模块 B 。

就好像使用模块的时候，你不用担心不同模块之间的全局变量相互影响一样，采用点模块名称这种形式也不用担心不同库之间的模块重名的情况。

在导入一个包的时候，Python 会根据 sys.path 中的目录来寻找这个包中包含的子目录。 

目录只有包含一个叫做  _init__.py 的文件才会被认作是一个包，主要是为了避免一些滥俗的名字（比如叫做 string）不小心的影响搜索路径中的有效模块。

最简单的情况，放一个空的 :file:__init__.py就可以了。当然这个文件中也可以包含一些初始化代码或者为（将在后面介绍的） __all__变量赋值。

