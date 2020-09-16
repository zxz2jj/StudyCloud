### 一、数据的读取与写入

#### 1. numpy.loadtxt()

| 参数       | 作用                                                         |
| ---------- | ------------------------------------------------------------ |
| fname      | 被读取的文件名（文件的相对地址或者绝对地址）                 |
| dtype      | 指定读取后数据的数据类型                                     |
| comments   | 跳过文件中指定参数开头的行（即不读取）                       |
| delimiter  | 指定读取文件中数据的分割符                                   |
| converters | 对读取的数据进行预处理，参数传递为一个字典，格式为：{列号：函数} |
| skiprows   | 选择跳过的行数                                               |
| usecols    | 指定需要读取的列，列号从0开始编码                            |
| unpack     | 选择是否将数据进行向量输出，默认False。如果设置成True，数据将按列输出 |
| encoding   | 对读取的文件进行预编码                                       |

> numpy读取后的数据是一个numpy多维数组的数据类型。
>
> csv 文件是一种特殊的 txt 文件，csv文件默认是以逗号分隔数据，因此如果想要分隔表格数据，可以设置 delimiter=”,“ 。
>
> 详情见：https://blog.csdn.net/ACID_lv_ing/article/details/87092714



### 二、数组的生成

np.array()可以接收一个序列数据，自动将其转换为 ndarray对象。

np.zeros(shape, )可以创建一个指定参数shape的全0数组。 

np.ones(shape, )可以创建一个指定参数shape的全1数组。

np.empty(shape, )可以创建一个指定参数shape的空数组，此时数组中的数字均为被初始化，有可能是垃圾数据。

np.arange()是内建函数range的数组版。

```python
np.empty_like(a, dtype=None) : Return an empty array with shape and type of input.
np.ones_like(a, dtype=None) : Return an array of ones with shape and type of input.
np.full_like(shape, fill_value, dtype=None) : Return a new array with shape of input filled with value.
np.zeros(a, dtype=None) : Return a new array setting values to zero.
```

### 三、数组的计算

Numpy的核心特征之一就是——n维数组对象。

#### 1、数组的数学计算

对ndarray对象进行的数学操作符（+ - * /）都将按照数组的计算方式计算。对于乘法：

　　np.dot(A, B) = A@B = 点乘

　　np.multiply(A, B) = A*B = 对应项相乘

　　点乘要求前者的列数等于后者的行数，对应项相乘需要矩阵的形状相同

带有标量计算的算术操作，会把计算参数传递给数组的每一个元素。

同尺寸数组之间的比较，会产生一个布尔数组。

#### 2、数据类型转换

```python
ndarray.astype(dtype=float32)
```

#### 3、切片与索引

与python的内建列表的切片不同,数组的切片是原数组的视图，任何对于视图的修改都将会反映在原数组上。而列表的切片将返回复制的副本。如果你确实需要一份数据的拷贝，则需要显示的复制数组切片。

```python
arr[5:8].copy()
```

#### 4、布尔索引

数组的比较操作也是可以向量化的，例如一个字符串数组：

```python
In: names = np.array(["Bob", "Joe", "will", "Bob"])
In: names == "Bob"   	# 数组元素逐个进行比较操作并生成Bool数组
  
Out: [True, False, False, True]
  
In: score = np.array([[1, 1, 1, 1],
             				  [2, 2, 2, 2],
            				  [3, 3, 3, 3],
            				  [4, 4, 4, 4]])
In: score[names == "Bob"]    # 使用布尔数组进行索引，Bool数组的长度必须和数组轴索引长度一致
 
Out: [[1, 1, 1, 1],
      [4, 4, 4, 4]]
```

符号 ~ 可以在对一个通用条件进行取反时使用。

Python的关键字 and 和 or  对于布尔值数组没用，使用 & 和 | 代替。

使用布尔值索引来选择数据时，总是生成数据的拷贝。

#### 5、神奇索引

使用整数数组进行数据索引，可以选出一个特定顺序的子集。

```python
In: data = np.array([[1, 1, 1, 1],
            				 [2, 2, 2, 2],
            				 [3, 3, 3, 3],
            				 [4, 4, 4, 4]])
In: data[[2, 0, 3, 1]]      # 通过行号选择数据子集

Out: [[3, 3, 3, 3],
      [1, 1, 1, 1],
      [4, 4, 4, 4],
      [2, 2, 2, 2]]
  
In: data = np.array([[1, 2, 3, 4],
           					 [1, 2, 3, 4],
           					 [1, 2, 3, 4],
         					   [1, 2, 3, 4]])
In: data[:, [2, 0, 3, 1]]    # 通过列号选择数据子集
Out: [[3, 1, 4, 2],
      [3, 1, 4, 2],
      [3, 1, 4, 2],
      [3, 1, 4, 2]]
  
# 传入多个一维数组进行索引，多个数组的对应位置将会组成坐标，依次选取元素，返回一个一维数组
```

#### 6、数组转置与换轴

数组有 tanspose 方法， 也有特殊的 T 属性。 使用 .T进行转置时换轴的一个特殊案例。

对于高维数组，transpose方法接收一个包含轴编号的元祖。按照指定的轴号顺序用以转置。

数组有swapaxes方法用于对轴进行调整，从而重新组织数据。方法接受一对（2个）轴编号作为参数。

> 转置与换轴返回的结果都是视图，任何对于视图的修改都将改变原数组。

#### 7、通用函数

numpy中的通用函数是对Python的内建简单函数的向量化封装，可以对数组中的元素进行逐元素操作。

8、