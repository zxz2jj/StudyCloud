## 一、Python基础

### 1、python关键字

```python
'False',Bool值，逻辑“假”
'None',None有自己的数据类型NoneType，并且这个类型中永远只会有它一个
'True',Bool值，逻辑“真”
'and',表示逻辑‘与’
'as', 导入模块时起别名，import...as...；与with连用，with open(“file”,'r') as f
'assert',表示断言，用于声明某个条件为真，如果该条件不是真的，则抛出异常：AssertionError
'break',终止循环
'class', 声明类关键字
'continue',跳过continue后面循环块中的语句，继续进行下一轮循环
'def', 定义类、函数等
'del', 用于删除一个或者连续几个元素
'elif',和if配合使用的，if语句中的一个分支用elif表示
'else',if语句的逻辑假分支
'except',与try关键字一起使用，捕获异常
'finally',看到finally语句，必然执行finally语句的代码块
'for', for循环
'from', 导入相应的模块，用import或者from...import...
'global',定义全局变量
'if', if条件语句用于选择分支，依据条件选择执行那个语句块。
'import',导入模块
'in',查找列表中是否包含某个元素
'is',is判断的是a对象是否就是b对象，是通过id来判断的；而==判断的是a对象的值是否和b对象的值相等，是通过value来判断的
'lambda',匿名函数，不用想给函数起什么名字。提升了代码的简洁程度
'nonlocal',与global关键字的区别见下边。
'not',表示逻辑‘非’
'or',表示逻辑“或”
'print'输出
'pass',pass的意思就是什么都不做。
'raise',raise可以显示地引发异常。一旦执行raise语句，后面的代码就不执行了
'return', 函数返回关键字
'try',和try一起使用，用来捕获异常
'while', while循环
'with',上下文管理，在with关键字管理的语句块中，打开的文件在执行完with语句块后释放
'yield'用起来和return很像，但它返回的是一个生成器
```

> global与nonlocal关键字的区别：
>
> 第一，两者的功能不同。global关键字修饰变量后标识该变量是全局变量，对该变量进行修改就是修改全局变量，而nonlocal关键字修饰变量后标识该变量是上一级函数中的局部变量，如果上一级函数中不存在该局部变量，nonlocal位置会发生错误（最上层的函数使用nonlocal修饰变量必定会报错）。
>
> 第二，两者使用的范围不同。global关键字可以用在任何地方，包括最上层函数中和嵌套函数中，即使之前未定义该变量，global修饰后也可以直接使用，而nonlocal关键字只能用于嵌套函数中，并且外层函数中定义了相应的局部变量，否则会发生错

### 2、python标准数据类型

Python3 中有六个标准的数据类型：

- Number（数字）
- String（字符串）
- List（列表）
- Tuple（元组）
- Set（集合）
- Dictionary（字典）

Python3 的六个标准数据类型中：

- **不可变数据（3 个）：**Number（数字）、String（字符串）、Tuple（元组）；
- **可变数据（3 个）：**List（列表）、Dictionary（字典）、Set（集合）

### 3、 条件语句

#### if语句

> if  boolean_exp :
>
> ​	exp;

​	if-elif-else结构依次检查每个测试条件，直到遇到通过了的条件，Python将执行紧跟在其后边的代码块，并跳过余下的代码块。

​	else是一条包罗万象的语句，只要不满足任何 if 和 elif 的条件测试，其中的代码块就会被执行，这可能会引入无效甚至恶意的数据。如果知道最终要测试的条件，应考虑使用一个 elif 来代替 else 。这样你可以肯定仅当满足相应的条件时，你的代码才会被执行。

> ​	在 if 语句中将列表名用在条件表达式中时，Python将在列表至少包含一个元素时返回True，并在列表为空时返回False。



### 4. 程序输入

#### 函数input()

函数 input() 让程序暂停运行，等待用户输入一些文本。获取用户输入后，Python将其存储在一个变量中。

```
input_var = input("Please input something:")
```

函数 input() 接受一个参数：即要向用户显示的**提示**或者**说明**，让用户知道该怎么做。可以将参数先存储在变量中，然后将变量传递给 input()。

使用函数 input() 时，Python将用户输入解读为**字符串**。因此**输入整数、浮点数等时需要强制格式转换**。



### 5. 循环

#### for循环

```
for value in iterator：
	use value do something
```

for循环可以遍历任何可迭代对象中的所有元素。每次返回一个元素赋值给for关键字后的变量名value。

冒号最易被遗忘。

#### while循环

```
while boolean_exp:
	do something
```

while循环当布尔表达式为真时一直运行。

在要求很多条件都满足时才继续运行的程序中，使用一个变量作为**标志**，用于判断整个程序是否处于活动状态是一个不错的做法。任何一个事件导致标志位False都将结束循环。

#### break

break语句跳出当前整个循环，不在继续执行余下的循环轮次。

#### continue

continue语句跳出当前循环轮次，回到循环的开头，判断循环条件后进行下一次循环。

<!--for循环是一种遍历列表的有效方式，但是for循环中不应该修改列表，否则将导致Python难以跟踪其中的元素。要在遍历列表的同时对其进行修改，可以使用while循环。通过while循环同列表和字典结合使用，可以收集、存储并组织大量的输入。-->

