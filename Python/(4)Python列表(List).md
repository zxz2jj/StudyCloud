# List

### 访问列表元素

给出列表名称并指出元素下标，列表下标从0开始。

索引指定为-1，返回列表最后一个元素。-2倒数第二个，以此类推。

#### 修改列表元素

使用列表名称及下标。

#### 列表中添加元素

1、append()

​	方法 append() 将元素添加到了列表的末尾。

2、insert()

​	方法 insert() 将元素插入到指定的列表中的下标位置。

#### 删除列表元素

1、del 语句可以删除列表元素。i.e.  del list[n]

2、pop()

​	方法 pop() 可删除列表末尾的元素，并返回这个值。

​	还可以为 pop() 方法指定参数下标，弹出任意位置的列表元素。参数默认为 -1。

3、remove()

​	方法 remove() 删除列表中指定的值。

​	如果不知道要从列表中删除的元素所处的位置，只知道要删除的元素的值，可以使用remove()。

​	方法 remove() 只删除第一个指定的值。如果要删除的值可能在列表中出现多次，就需要使用循环。

#### 列表函数

sorted() 函数

​	返回一个列表排序后的副本，排序规则与sort()方法类似。

len() 函数

​	返回列表第一维的元素个数。

list() 函数

​	可以将一个数组、元组、迭代器等转化为列表。

#### 列表解析

列表解析可以生成复杂的列表。

​	1、定义一个表达式。 2、编写一个for循环用于给表达式提供值。

​	i.e.  [x**2  for x in rang(10)]

#### 列表切片

列表切片可以访问列表的部分元素。

元素由起始下标开始访问到终止下标的前一个元素。

>  list[2:5]     访问下标 2、3、4的元素

将列表切片赋值给一个变量，则变量指向了这个切片的新副本。

>  	如果只是将列表名赋值给一个变量，则这个变量与列表名指向了同一个列表。
>
> ​	因此创建一个列表的新副本，正确的为:  copy_list = list[ : ]。

#### Python列表脚本操作符

列表对 + 和 * 的操作符与字符串相似。+ 号用于组合列表，* 号用于重复列表。

| list.append(x)    | 把一个元素添加到列表的结尾，相当于 a[len(a):] = [x]。        |
| ----------------- | ------------------------------------------------------------ |
| list.extend(L)    | 通过添加指定列表的所有元素来扩充列表，相当于 a[len(a):] = L。 |
| list.insert(i, x) | 在指定位置插入一个元素。第一个参数是准备插入到其前面的那个元素的索引，例如 a.insert(0, x) 会插入到整个列表之前，而 a.insert(len(a), x) 相当于 a.append(x) 。 |
| list.remove(x)    | 删除列表中值为 x 的第一个元素。如果没有这样的元素，就会返回一个错误。 |
| list.pop([i])     | 从列表的指定位置移除元素，并将其返回。如果没有指定索引，a.pop()返回最后一个元素。元素随即从列表中被移除。（方法中 i 两边的方括号表示这个参数是可选的，而不是要求你输入一对方括号，你会经常在 Python 库参考手册中遇到这样的标记。） |
| list.clear()      | 移除列表中的所有项，等于del a[:]。                           |
| list.index(x)     | 返回列表中第一个值为 x 的元素的索引。如果没有匹配的元素就会返回一个错误。 |
| list.count(x)     | 返回 x 在列表中出现的次数。                                  |
| list.sort()       | 对列表中的元素进行排序。                                     |
| list.reverse()    | 倒排列表中的元素。                                           |
| list.copy()       | 返回列表的浅复制，等于a[:]。                                 |

```
class list(object):
    """
    list() -> new empty list
    list(iterable) -> new list initialized from iterable's items
    """
    def append(self, p_object): # real signature unknown; restored from __doc__
        """ L.append(object) -> None -- append object to end """
        pass

    def clear(self): # real signature unknown; restored from __doc__
        """ L.clear() -> None -- remove all items from L """
        pass

    def copy(self): # real signature unknown; restored from __doc__
        """ L.copy() -> list -- a shallow copy of L """
        return []

    def count(self, value): # real signature unknown; restored from __doc__
        """ L.count(value) -> integer -- return number of occurrences of value """
        return 0

    def extend(self, iterable): # real signature unknown; restored from __doc__
        """ L.extend(iterable) -> None -- extend list by appending elements from the iterable """
        pass

    def index(self, value, start=None, stop=None): # real signature unknown; restored from __doc__
        """
        L.index(value, [start, [stop]]) -> integer -- return first index of value.
        Raises ValueError if the value is not present.
        """
        return 0

    def insert(self, index, p_object): # real signature unknown; restored from __doc__
        """ L.insert(index, object) -- insert object before index """
        pass

    def pop(self, index=None): # real signature unknown; restored from __doc__
        """
        L.pop([index]) -> item -- remove and return item at index (default last).
        Raises IndexError if list is empty or index is out of range.
        """
        pass

    def remove(self, value): # real signature unknown; restored from __doc__
        """
        L.remove(value) -> None -- remove first occurrence of value.
        Raises ValueError if the value is not present.
        """
        pass

    def reverse(self): # real signature unknown; restored from __doc__
        """ L.reverse() -- reverse *IN PLACE* """
        pass

    def sort(self, key=None, reverse=False): # real signature unknown; restored from __doc__
        """ L.sort(key=None, reverse=False) -> None -- stable sort *IN PLACE* """
        pass

```

