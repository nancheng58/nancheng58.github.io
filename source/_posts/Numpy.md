---
title: Numpy学习笔记
date: 2020-03-30 17:44:29
tags: 学习笔记
categories: 学习笔记
---
## 前言

之前从网上学的，当时记录在了OneNote上，现整理成Markdown文档，发布在这里。
## 一.Ndarray 对象

### **是啥？**   
一个N维的数组对象。 存放同类型多元素的多维数组。

### **组成**：   

一个指向数据的指针。  
数据类型（dtype） 描述在数组中的固定大小值的格子。   
一个表示数组形状的元组，表示各维度大小的元组。   
一个跨度元组，里边有一个整数指的是为了前进到当前维度下一个元素需要跨过的字节数。



### **创建方法是啥**？  
用Numpy里的array函数   
```python
numpy.array(object, dtype = None, copy = True, order = None, subok = False, ndmin = 0)
```
    参数说明
	名称	         描述  
	* object	数组或嵌套的数列  
	* dtype	   	数组元素的数据类型(可选) 可以是复数，可以是结构体名  
	* copy		对象是否需要复制(可选)  
	* order		创建数组的样式，C 为行方向，F 为列方向，A 为任意方向（默认）  
	* subok		默认返回一个与基类类型一致的数组
	* ndmin		指定生成数组的最小维度



## 二.NumPy 数据类型

包含的数据类型非常多  

    名称		描述  
	* bool_		布尔型数据类型（True 或者 False）  
	* int_		默认的整数类型（类似于 C 语言中的 * long，int32 或 int64）  
	* intc		与 C 的 int 类型一样，一般是 int32 或 int 64  
	* intp		用于索引的整数类型（类似于 C 的   ssize_t，一般情况下仍然是 int32 或 int64）
	* int8		字节（-128 to 127）  
	* int16		整数（-32768 to 32767）  
	* int32		整数（-2147483648 to 2147483647）
	* int64		整数（-9223372036854775808 to 9223372036854775807）  
	* uint8		无符号整数（0 to 255）  
	* uint16	无符号整数（0 to 65535）  
	* uint32	无符号整数（0 to 4294967295）  
	* uint64	无符号整数（0 to 18446744073709551615）  
	* float_	float64 类型的简写  
	* float16	半精度浮点数，包括：1 个符号位，5 个指数位，10 个尾数位  
	* float32	单精度浮点数，包括：1 个符号位，8 个指数位，23 个尾数位  
	* float64	双精度浮点数，包括：1 个符号位，11 个指数位，52 个尾数位  
	* complex_	complex128 类型的简写，即 128 位复数  
	* complex64	复数，表示双 32 位浮点数（实数部分和虚数部分）  
	* complex128复数，表示双 64 位浮点数（实数部分和虚数部分）

### 数据类型对象

dtype 对象是使用以下语法构造的：   
```python
numpy.dtype(object, align, copy)
```
	object - 要转换为的数据类型对象
	align - 如果为 true，填充字段使其类似 C 的结构体。
	copy - 复制 dtype 对象 ，如果为 false，则是对内置数据类型对象的引用

其中每个内建类型都有一个唯一定义它的**字符代码**，如下：
  
	字符	对应类型  
	b		布尔型  
	i		(有符号) 整型  
	u		无符号整型 integer  
	f		浮点型  
	c		复数浮点型  
	m		timedelta（时间间隔）  
	M		datetime（日期时间）  
	O		(Python) 对象  
	S,a		(byte-)字符串  
	U		Unicode  
	V		原始数据 (void)  


## 三.Numpy 数组属性

### NumPy数组的一些基本属性  

**数组的维数称为秩，秩也就是轴的数量。**  
**每一个线性的数组称为轴(axis)，即维度。** 例如每个二维数组是由一维个一维数组组成的，这里边有两个轴。（很多时候可以声明 axis。axis=0，表示沿着第 0 轴进行操作，即对每一列进行操作；axis=1，表示沿着第1轴进行操作，即对每一行进行操作。）

NumPy 的数组中比较重要 ndarray 对象属性有：  

	属性					说明  
	ndarray.ndim	秩，即轴的数量或维度的数量  
	ndarray.shape	数组的维度，对于矩阵，n 行 m 列  
	ndarray.size	数组元素的总个数，相当于 .shape 中 n*m 的值  
	ndarray.dtype	ndarray 对象的元素类型  
	ndarray.itemsize	ndarray 对象中每个元素的大小，以字节为单位  
	ndarray.flags	ndarray 对象的内存信息  
	ndarray.real	ndarray元素的实部  
	ndarray.imag	ndarray 元素的虚部  
	ndarray.data	包含实际数组元素的缓冲区，由于一般通过数组的索引获取元素，所以通常不需要使用这个属性。



**常用的函数 reshape 调整数组大小**



## 四.NumPy 创建数组   

### numpy.empty numpy.empty方法  

用来创建一个指定形状（shape）、数据类型（dtype）且未初始化的数组：   
```python
numpy.empty(shape, dtype = float, order = 'C')   
```
	参数说明：  
	参数	描述  
	shape	数组形状  
	dtype	数据类型，可选  
	order	有"C"和"F"两个选项,分别代表，行优先和列优先，在计算机内存中的存储元素的顺序。  
**未初始化，所以是随机值**

### numpy.zeros  
创建指定大小的数组，数组元素以 0 来填充：
```py
 numpy.zeros(shape, dtype = float, order = 'C') 
```
参数含义同上。

### numpy.ones

创建指定形状的数组，数组元素以 1 来填充：
```py
numpy.ones(shape, dtype = None, order = 'C') 
```
参数含义同上。


## 五.NumPy 从已有的数组创建数组

### numpy.asarray

numpy.asarray 类似 numpy.array，但 numpy.asarray 参数只有三个，比 numpy.array 少两个。 
```py
numpy.asarray(a, dtype = None, order = None)
```

	参数说明：
	参数		描述
	a		任意形式的输入参数，可以是列表, 列表的元组, 元组, 元组的元组, 元组的列表，多维数组
	dtype	数据类型，可选
	order	可选，有"C"和"F"两个选项,分别代表，行优先和列优先，在计算机内存中的存储元素的顺序。

### numpy.frombuffer

numpy.frombuffer 用于实现动态数组。
numpy.frombuffer 接受 buffer 输入参数，以流的形式读入转化成 ndarray 对象。
```py
numpy.frombuffer(buffer, dtype = float, count = -1, offset = 0)
```
**注意：buffer 是字符串的时候，Python3 默认 str 是 Unicode 类型，所以要转成 bytestring 在原 str 前加上 b。**	

	参数说明：  
	参数	描述  
	buffer	可以是任意对象，会以流的形式读入。  
	dtype	返回数组的数据类型，可选  
	count	读取的数据数量，默认为-1，读取所有数据。  
	offset	读取的起始位置，默认为0。  

numpy.fromiter

numpy.fromiter 方法从可迭代对象中建立 ndarray 对象，返回一维数组。  
```py
numpy.fromiter(iterable, dtype, count=-1)
```
	参数		  描述  
	iterable	可迭代对象  
	dtype		返回数组的数据类型  
	count		读取的数据数量，默认为-1，读取所有数据

## 六.NumPy 从数值范围创建特殊数组

### numpy.arange

numpy 包中的使用 arange 函数创建数值范围并返回 ndarray 对象，函数格式如下：  
```py
numpy.arange(start, stop, step, dtype) 
```
根据 start 与 stop 指定的范围以及 step 设定的步长，生成一个 ndarray。  

	参数说明：
	参数	描述
	start	起始值，默认为0
	stop	终止值（不包含）
	step	步长，默认为1
	dtype	返回ndarray的数据类型，如果没有提供，则会使用输入数据的类型。
**范围：[strat,stop)**

### numpy.linspace

numpy.linspace 函数用于创建一个一维数组，数组是一个**等差数列**构成的，格式如下：  
```py
np.linspace(start, stop, num=50, endpoint=True, retstep=False, dtype=None) 
```

	参数说明：  
	参数			描述  
	start		序列的起始值  
	stop		序列的终止值，如果endpoint为true，该值于数列中  
	num			要生成的等步长的样本数量，默认为50  
	endpoint	该值为 true 时，数列中中包含stop值，反之包含，默认是True。  
	retstep		如果为 True 时，生成的数组中会显示间距，反之不显示。  
	dtype		ndarray 的数据类型

### numpy.logspace

numpy.logspace 函数用于创建一个于**等比数列**。  

格式如下： 
```py 
np.logspace(start, stop, num=50, endpoint=True, base=10.0, dtype=None) 
```
base 参数意思是取对数的时候 log 的下标。

	参数	描述  
	start	序列的起始值为：base  start  
	stop	序列的终止值为：base  stop。如果endpoint为true，该值包含于数列中  
	num	要生成的等步长的样本数量，默认为50  
	endpoint	该值为 true 时，数列中中包含stop值，反之不包含，默认是True。  
	base	对数 log 的底数，默认是10。  
	dtype	ndarray 的数据类型  
	创建了一个[base^start,base^stop) 的数组,数组个数为num

## 七.NumPy 切片和索引

 ### slice 函数  

 先创建一个数组
```py
a = np.arange(n) 
s = slice(start,stop,step) 
```

 a[s]为切片后的结果 或者 s = a[start : stop : step]  
 注：s为切片后的结果  
 start, stop 及 step 参数分别为 结果数组的三者 [start,stop)  
 注 ： 若只有一个参数start，则返回一个该参数索引的元素。 切片还可以包括省略号 …，来使选择元组的长度与数组的维度相同。 a[...,1] 是第二列 a[1,...] 是第二行 a[...,1:] 是从第二列开始以及以后的元素

**NumPy 高级索引 先略过吧…好像用处不大**

## 八.NumPy 广播(Broadcast)

广播(Broadcast)是 numpy 对不同形状(shape)的数组进行数值计算的方式， 对数组的算术运算通常在相应的元素上进行。   
如果两个数组 a 和 b 形状相同，即满足 a.shape == b.shape，那么 a*b 的结果就是 a 与 b 数组对应位相乘。这要求维数相同，且各维度的长度相同。  
如果两个数组形状不同，触发广播机制  

	广播的规则:  
	让所有输入数组都向其中形状最长的数组看齐，形状中不足的部分都通过在前面加 1 补齐。 
	输出数组的形状是输入数组形状的各个维度上的最大值。 
	如果输入数组的某个维度和输出数组的对应维度的长度相同或者其长度为 1 时，这个数组能够用来计算，否则出错。 
	当输入数组的某个维度的长度为 1 时，沿着此维度运算时都用此维度上的第一组值。  

简单理解：对两个数组，分别比较他们的每一个维度（若其中一个数组没有当前维度则忽略），满足： 数组拥有相同形状。 当前维度的值相等。 当前维度的值有一个是 1。 若条件不满足，抛出 "ValueError: frames are not aligned" 异常。 tile() 函数，将原矩阵横向、纵向地复制。 Tile(s,a,b)  将原矩阵横向复制a倍，纵向b倍。 

## 九.NumPy遍历数组  

### numpy.nditer  
**迭代器对象** 
```py
for x in np.nditer(a) : print(x) 
```
多维数组默认是行优先的，若使用列优先，则可将数组转置为a.t再强制使用行优先 因为a 和 a.T 的遍历顺序是一样的 for x in np.nditer(a, order='F'): Fortran order，列序优先； for x in np.nditer(a.T, order='C'): C order，行序优先；

修改数组中元素的值 可选参数 **op_flags**  
 默认情况下，nditer 将视待迭代遍历的数组为只读对象（read-only），为了在遍历数组的同时，实现对数组元素值得修改，必须指定 read-write 或者 write-only 的模式。
```py
np.nditer(a,op_flag = ['readwrite']) : 
```

## 十.Numpy 数组操作

X[…] = new value
	

	相关函数
	函数	描述  
	reshape	不改变数据的条件下修改形状  
	flat	数组元素迭代器  
	flatten	返回一份数组拷贝，对拷贝所做的修改不会影响原始数组  
	ravel	返回展开数组

### numpy.ndarray.flatten 
```py
ndarray.flatten(order='C') 
```
ndarray 是数组名  
参数说明：  
order：'C' -- 按行，'F' -- 按列，'A' -- 原顺序，'K' -- 元素在内存中的出现顺序。

### numpy.ravel   
```py
numpy.ravel(a, order='C')
```
 将数组展成一维数组 参数同上

### 翻转数组
	函数	描述
	transpose	对换数组的维度
	ndarray.T	和 self.transpose() 相同
	rollaxis	向后滚动指定的轴
	swapaxes	对换数组的两个轴
### numpy.transpose 

numpy.transpose 函数用于对换数组的维度，格式如下：  
```py
numpy.transpose(arr, axes) 
```
	参数说明:   
	arr：要操作的数组   
	axes(可选)：整数列表，对应维度，不选的话所有维度都会对换，所以二维就是转置。

numpy.rollaxis 函数向后滚动特定的轴到一个特定位置，格式如下： 
```py
numpy.rollaxis(arr, axis, start) 
```
	参数说明：   
	arr：	数组   
	axis：	要向后滚动的轴，其它轴的相对位置不会改变     
	start： 默认为零，表示完整的滚动。会滚动到特定位置。 目测用不到…且较难

### numpy.swapaxes 
函数用于交换数组的两个轴，格式如下： 
```py
numpy.swapaxes(arr, axis1, axis2) 
```
	参数说明
	arr：	输入的数组   
	axis1：	对应第一个轴的整数  
	axis2：	对应第二个轴的整数 和上面那个类似

修改数组维度
维度	描述
broadcast	产生模仿广播的对象
broadcast_to	将数组广播到新形状
expand_dims	扩展数组的形状
squeeze	从数组的形状中删除一维条目

### numpy.broadcast   
用于模仿广播的对象，它返回一个对象，该对象封装了将一个数组广播到另一个数组的结果。 也可以手动广播

### numpy.broadcastto  
```py
numpy.broadcast_to(array, shape, subok)
```
函数将数组广播到新形状。它在原始数组上返回只读视图。 它通常不连续。 **如果新形状不符合 NumPy 的广播规则，该函数可能会抛出ValueError。** 

### numpy.expanddims
函数通过在指定位置插入新的轴来扩展数组形状，函数格式如下:   
```py
numpy.expand_dims(arr, axis)   
```
	参数说明：  
	arr：输入的数组   
	axis：新轴插入的位置 插入了一个空轴

### numpy.squeeze numpy.squeeze   
函数从给定数组的形状中删除一维的条目，函数格式如下：  
```py 
numpy.squeeze(arr, axis) 
```
	参数说明：   
	arr：输入数组   
	axis：整数或整数元组，用于选择形状中一维条目的子集 和上面类似

连接数组

	函数	描述  
	concatenate	连接沿现有轴的数组序列  
	stack	沿着新的轴加入一系列数组。  
	hstack	水平堆叠序列中的数组（列方向）  
	vstack	竖直堆叠序列中的数组（行方向）  

### numpy.concatenate() 
numpy.concatenate 函数用于沿指定轴连接相同形状的两个或多个数组，格式如下： 
```py
numpy.concatenate((a1, a2, ...), axis) 
```
	参数说明：  
	a1, a2, ...：相同类型的数组 
	axis：沿着它连接数组的轴，默认为 0

### numpy.stack() 
numpy.stack 函数用于沿新轴连接数组序列，格式如下：
```py
numpy.stack(arrays, axis) 
```
	参数说明：  
	arrays 相同形状的一组数组序列，如(a,b)  
	axis：返回数组中的轴，输入数组沿着它来堆叠

### numpy.hstack() 
numpy.hstack 是 numpy.stack 函数的变体，它通过水平堆叠来生成数组。 
```py
ans =  np.hstack((a,b))
```
### numpy.vstack  
同上 竖直堆叠

### 分割数组
	函数	数组及操作
	split	将一个数组分割为多个子数组
	hsplit	将一个数组水平分割为多个子数组（按列）
	vsplit	将一个数组垂直分割为多个子数组（按行）

### numpy.split() 
numpy.split 函数沿特定的轴将数组分割为子数组，格式`如下： 
```py
numpy.split(ary, indicesorsections, axis)
```
	参数说明：   
	ary：	被分割的数组   
	indicesorsections：	如果是一个整数，就用该数平均切分，如果是一个数组，为沿轴切分的位置（左开右闭）   
	axis：	沿着哪个维度进行切向，默认为0，横向切分，也就是水平切分。为1时，纵向切分 numpy.hsplit 水平切分 numpy.vsplit 垂直切分

### 数组元素的添加与删除
	函数	元素及描述
	resize	返回指定形状的新数组
	append	将值添加到数组末尾
	insert	沿指定轴将值插入到指定下标之前
	delete	删掉某个轴的子数组，并返回删除后的新数组
	unique	查找数组内的唯一元素

### numpy.resize()
numpy.resize 函数返回指定大小的新数组。 如果新数组大小大于原始大小，则包含原始数组中的元素的副本。
```py
numpy.resize(arr, shape)  
```
	参数说明：  
	arr：要修改大小的数组  
	shape：返回数组的新形状

### numpy.append()
numpy.append 函数在数组的末尾添加值。   
追加操作会分配整个数组，并把原来的数组复制到新数组中。 此外，输入数组的维度必须匹配否则将生成ValueError。   
append 函数返回的始终是一个一维数组。
```py
numpy.append(arr, values, axis=None) 
```
	参数说明： 
	arr：输入数组  
	values：要向arr添加的值，需要和arr形状相同（除了要添加的轴）  
	axis：默认为 None。当axis无定义时，是横向加成，返回总是为一维数组！当axis有定义的时候，分别为0和1的时候。当axis有定义的时候，分别为0和1的时候（列数要相同）。当axis为1时，数组是加在右边（行数要相同）。

### numpy.insert()
numpy.insert 函数在给定索引之前，沿给定轴在输入数组中插入值。 如果值的类型转换为要插入，则它与输入数组不同。 插入没有原地的，函数会返回一个新数组。 此外，如果未提供轴，则输入数组会被展开。
```py 
numpy.insert(arr, obj, values, axis) 
```
	参数说明：  
	arr：输入数组  
	obj：在其之前插入值的索引  
	values：要插入的值  
	axis：沿着它插入的轴，如果未提供，则输入数组会被展开

### numpy.delete() 
numpy.delete 函数返回从输入数组中删除指定子数组的新数组。 与 insert() 函数的情况一样，如果未提供轴参数，则输入数组将展开。
```py
numpy.delete(arr, obj, axis)  
```
	参数说明：
	arr：	输入数组  
	obj：	可以被切片，整数或者整数数组，表明要从输入数组删除的子数组  
	axis：	沿着它删除给定子数组的轴，如果未提供，则输入数组会被展开

### numpy.unique() 
numpy.unique 函数用于去除数组中的重复元素。 
```py
numpy.unique(arr, returnindex, returninverse, returncounts) 
```
	参数说明  
	arr：			输入数组，如果不是一维数组则会展开 
	returnindex：	如果为true，返回新列表元素在旧列表中的位置（下标），并以列表形式储存  
	returninverse：	如果为true，返回旧列表元素在新列表中的位置（下标），并以列表形式储存   
	returncounts：	如果为true，返回去重数组中的元素在原数组中的出现次数


## 十一.NumPy 位运算

**NumPy "bitwise_" 开头的函数是位运算函数。**  

NumPy 位运算包括以下几个函数：

	函数		描述  
	bitwise_and	对数组元素执行位与操作  
	bitwise_or	对数组元素执行位或操作  
	invert		按位取反  
	left_shift	向左移动二进制表示的位  
	right_shift	向右移动二进制表示的位

**bin(a)**  a的二进制 前两个函数顾名思义，对(a,b)做相应操作

### invert  
invert() 函数对数组中整数进行按位取反运算，即 0 变成 1，1 变成 0。 对于有符号整数，取该二进制数的补码，然后 +1。二进制数，最高位为0表示正数，最高位为 1 表示负数。

左右移就是 **right_shift(a,b)** 将a移动b位，全都补0


## 十二.NumPy 字符串函数

以下函数用于对 dtype 为 numpy.string 或 numpy.unicode 的数组执行向量化字符串操作。 它们基于 Python 内置库中的标准字符串函数。

这些函数在字符数组类（numpy.char）中定义。

	函数					描述
	add()			对两个数组的逐个字符串元素进行连接
	multiply()		返回按元素多重连接后的字符串
	center()		居中字符串
	capitalize()	将字符串第一个字母转换为大写
	title()			将字符串的每个单词的第一个字母转换为大写
	lower()			数组元素转换为小写
	upper()			数组元素转换为大写
	split()			指定分隔符对字符串进行分割，并返回数组列表
	splitlines()	返回元素中的行列表，以换行符分割
	strip()			移除元素开头或者结尾处的特定字符
	join()			通过指定分隔符来连接数组中的元素
	replace()		使用新字符串替换字符串中的所有子字符串
	decode()		数组元素依次调用str.decode
	encode()		数组元素依次调用str.encode(编码默认utf-8)


## 十三.NumPy 数学函数

### 三角函数
NumPy 提供了标准的三角函数：**sin()**、**cos()**、**tan()**。 也有相应的反三角函数。   
np.pi 就是pi

### 舍入函数
numpy.around() 函数返回指定数字的四舍五入值。 
```py
numpy.around(a,decimals)  
```
	参数说明：  
	a: 数组  
	decimals: 舍入的小数位数。 默认值为0。 如果为负，整数将四舍五入到小数点左侧的位置

### numpy.floor()  
numpy.floor() 返回小于或者等于指定表达式的最大整数，即向下取整。

### numpy.ceil() 
numpy.ceil() 返回大于或者等于指定表达式的最小整数，即向上取整。

## 十四.NumPy 算术函数

NumPy 算术函数包含简单的加减乘除: **add()**，**subtract()**，**multiply()** 和 **divide()**。 需要注意的是数组必须具有相同的形状或符合数组广播规则。

**一些有意思的函数**

### numpy.reciprocal()  
numpy.reciprocal()  函数返回参数逐元素的倒数。如 1/4 倒数为 4/1。

### numpy.power() 
numpy.power()  函数将第一个输入数组中的元素作为底数，计算它与第二个输入数组中相应元素的幂。

### numpy.mod() 
numpy.mod() 计算输入数组中相应元素的相除后的余数。 函数 numpy.remainder() 也产生相同的结果。分别对每个元素取模，ai%bi


## 十五.NumPy 统计函数

### numpy.amin() 和 numpy.amax()

numpy.amin() 用于计算数组中的元素沿指定轴的最小值。  
numpy.amax() 用于计算数组中的元素沿指定轴的最大值。

### numpy.ptp()
numpy.ptp()函数计算数组中元素最大值与最小值的差（最大值 - 最小值）

### numpy.percentile()
百分位数是统计中使用的度量，表示小于这个值的观察值的百分比。 

```py
numpy.percentile(a, q, axis) 
```
函数numpy.percentile()接受以下参数。 

	参数说明：
	a: 输入数组
	q: 要计算的百分位数，在 0 ~ 100 之间
	axis: 沿着它计算百分位数的轴

### numpy.median() 
numpy.median() 函数用于计算数组 a 中元素的中位数（中值）

### numpy.mean() 
numpy.mean() 函数返回数组中元素的算术平均值。  
如果提供了轴，则沿其计算。  
要给定轴 算术平均值是沿轴的元素的总和除以元素的数量。

### numpy.average()  
numpy.average() 函数根据在另一个数组中给出的各自的权重计算数组中元素的加权平均值。 不指定权重时相当于mean函数 该函数可以接受一个轴参数。 如果没有指定轴，则数组会被展开。 加权平均值即将各数值乘以相应的权数，然后加总求和得到总体值，再除以总的单位数。

### 标准差  
标准差是一组数据平均值分散程度的一种度量。 标准差是方差的算术平方根。 标准差公式如下： 使用时直接调用std函数即可 
```py
std = sqrt(mean((x - x.mean())2))
```
### 方差 
统计中的方差（样本方差）是每个样本值与全体样本值的平均数之差的平方值的平均数，即 
```py
var=mean((x - x.mean()) 2)。 
```
换句话说，标准差是方差的平方根。 使用时直接调用var函数即可


## 十六.NumPy 排序、条件刷选函数

提供了以下三种排序。

				种类	   速度	最坏情况		工作空间	  稳定性
	'quicksort'（快速排序）	1	O(n^2)		   0		否
	'mergesort'（归并排序）	2	O(n*log(n))	  ~n/2		是
	'heapsort'（堆排序）		3	O(n*log(n))	   0		否


### numpy.sort() 
numpy.sort() 函数返回输入数组的排序副本。函数格式如下： 
```py
numpy.sort(a, axis, kind, order) 
```

	参数说明：
	a: 		要排序的数组
	axis: 	沿着它排序数组的轴，如果没有数组会被展开，沿着最后的轴排序， axis=0 按列排序，axis=1 按行排序
	kind: 	默认为'quicksort'（快速排序）
	order: 	如果数组包含字段，则是要排序的字段
### numpy.argsort() 
numpy.argsort() 函数返回的是数组值从小到大的索引值。

### numpy.lexsort() 
numpy.lexsort() 用于对多个序列进行排序。把它想象成对电子表格进行排序，每一列代表一个序列，排序时优先照顾靠后的列 也就是多关键字排序   
```py
numpy.lexsort(a,b,c)
```
按照优先级为c>b>a的优先级排序

其他的一些排序 **msort、sort_complex、partition、argpartition**

	函数			描述
	msort(a)	数组按第一个轴排序，返回排序后的数组副本。np.msort(a) 相等于 np.sort(a, axis=0)。
	sort_complex(a)	对复数按照先实部后虚部的顺序进行排序。
	partition(a, kth[, axis, kind, order])	指定一个数，对数组进行分区
	argpartition(a, kth[, axis, kind, order])	可以通过关键字 kind 指定算法沿着指定轴对数组进行分区

### numpy.argmax() 和 numpy.argmin()
numpy.argmax() 和 numpy.argmin()函数分别沿给定轴返回最大和最小元素的索引。 
### numpy.where()
numpy.where()函数返回输入数组中满足给定条件的元素的索引。 
### numpy.extract() 
numpy.extract() 函数根据某个条件从数组中抽取元素，返回满条件的元素。


## 十七. NumPy 字节交换及副本和视图

**很有意思的大小端调换**

### numpy.ndarray.byteswap() 
numpy.ndarray.byteswap() 函数将 ndarray 中每个元素中的字节进行大小端转换。 用ndarray.byteswap(True)

**副本和视图的概念**  
副本是一个数据的完整的拷贝，如果我们对副本进行修改，它不会影响到原始数据，物理内存不在同一位置。 视图是数据的一个别称或引用，通过该别称或引用亦便可访问、操作原有数据，但原有数据不会产生拷贝。如果我们对视图进行修改，它会影响到原始数据，物理内存在同一位置。

**场景** 

	视图一般发生在：    
	1、numpy 的切片操作返回原数据的视图。  
	2、调用 ndarray 的 view() 函数产生一个视图。 副本一般发生在： Python 序列的切片操作，调用deepCopy()函数。 调用 ndarray 的 copy() 函数产生一个副本。

一般时候是无复制 简单的赋值不会创建数组对象的副本。 相反，它使用原始数组的相同id()来访问它。 id()返回 Python 对象的通用标识符，类似于 C 中的指针。 此外，一个数组的任何变化都反映在另一个数组上。 例如，一个数组的形状改变也会改变另一个数组的形状。


## 十八.NumPy 矩阵库(Matrix)

NumPy 中包含了一个矩阵库 numpy.matlib，该模块中的函数返回的是一个矩阵，而不是 ndarray 对象。 矩阵里的元素可以是数字、符号或数学式。

### matlib.empty()
matlib.empty() 函数返回一个新的矩阵，语法格式为： numpy.matlib.empty(shape, dtype, order) 参数说明：
填充为随机数据

### numpy.matlib.zeros()
numpy.matlib.zeros() 函数创建一个以 0 填充的矩阵。

### numpy.matlib.ones()
numpy.matlib.ones()函数创建一个以 1 填充的矩阵。

### numpy.matlib.eye()
numpy.matlib.eye() 函数返回一个矩阵，对角线元素为 1，其他位置为零。
```py
numpy.matlib.eye(n, M,k, dtype)
```

	参数说明：
	n: 返回矩阵的行数
	M: 返回矩阵的列数，默认为 n
	k: 对角线的索引
	dtype: 数据类型

### numpy.matlib.identity()
numpy.matlib.identity() 函数返回给定大小的单位矩阵。 单位矩阵是个方阵，从左上角到右下角的对角线（称为主对角线）上的元素均为 1，除此以外全都为 0。

### numpy.matlib.rand()
numpy.matlib.rand() 函数创建一个给定大小的矩阵，数据是随机填充的。


矩阵总是二维的，而 ndarray 是一个 n 维数组。 两个对象都是可互换的。



## 十九.NumPy 线性代数

NumPy 提供了线性代数函数库 **linalg**，该库包含了线性代数所需的所有功能：

	函数			描述
	dot			两个数组的点积，即元素对应相乘。
	vdot		两个向量的点积
	inner		两个数组的内积
	matmul		两个数组的矩阵积
	determinant	数组的行列式
	solve		求解线性矩阵方程
	inv			计算矩阵的乘法逆矩阵

### numpy.dot() 
numpy.dot()  
对于两个一维的数组，计算的是这两个数组对应下标元素的乘积和(数学上称之为内积)；  
对于二维数组，计算的是两个数组的矩阵乘积；  
对于多维数组，它的通用计算公式如下，即结果数组中的每个元素都是：数组a的最后一维上的所有元素与数组b的倒数第二位上的所有元素的乘积和：  
dot(a, b)[i,j,k,m] = sum(a[i,j,:] * b[k,:,m])。 
```py
numpy.dot(a, b, out=None)  
```
	参数说明： 
	a : ndarray 数组 
	b : ndarray 数组 
	out : ndarray, 可选，用来保存dot()的计算结果

### numpy.vdot() 
numpy.vdot() 函数是两个向量的点积。 如果第一个参数是复数，那么它的共轭复数会用于计算。 如果参数是多维数组，它会被展开。

### numpy.inner() 
numpy.inner() 函数返回一维数组的向量内积。对于更高的维度，它返回最后一个轴上的和的乘积。

### numpy.matmul() 
numpy.matmul 函数返回两个数组的矩阵乘积。 虽然它返回二维数组的正常乘积，但如果任一参数的维数大于2，则将其视为存在于最后两个索引的矩阵的栈，并进行相应广播。 另一方面，如果任一参数是一维数组，则通过在其维度上附加 1 来将其提升为矩阵，并在乘法之后被去除。

### numpy.linalg.det() 
numpy.linalg.det() 函数计算输入矩阵的行列式。

### numpy.linalg.solve() 
numpy.linalg.solve() 函数给出了矩阵形式的线性方程的解。


### numpy.linalg.inv() 
numpy.linalg.inv() 函数计算矩阵的乘法逆矩阵。  
**逆矩阵（inverse matrix）**：设A是数域上的一个n阶矩阵，若在相同数域上存在另一个n阶矩阵B，使得： AB=BA=E ，则我们称B是A的逆矩阵，而A则被称为可逆矩阵。  
注：E为单位矩阵。


## 二十.NumPy IO

Numpy 可以读写磁盘上的文本数据或二进制数据。 

 NumPy 为 ndarray 对象引入了一个简单的文件格式：**npy**。   
 npy 文件用于存储重建 ndarray 所需的数据、图形、dtype 和其他信息。   

 常用的 IO 函数有：  
 **load()** 和 **save()** 函数是读写文件数组数据的两个主要函数，默认情况下，数组是以未压缩的原始二进制格式保存在扩展名为 .npy 的文件中。 savze() 函数用于将多个数组写入文件，默认情况下，数组是以未压缩的原始二进制格式保存在扩展名为 .npz 的文件中。 loadtxt() 和 savetxt() 函数处理正常的文本文件(.txt 等)

### numpy.save()   
numpy.save() 函数将数组保存到以 .npy 为扩展名的文件中。  
```py
numpy.save(file, arr, allowpickle=True, fiximports=True) 
```
	参数说明：  
	file：要保存的文件，扩展名为 .npy，如果文件路径末尾没有扩展名 .npy，该扩展名会被自动加上。  
	arr: 要保存的数组   
	allowpickle: 可选，布尔值，允许使用 Python pickles 保存对象数组，Python 中的 pickle 用于在保存到磁盘文件或从磁盘文件读取之前，对对象进行序列化和反序列化。   
	fiximports: 可选，为了方便 Pyhton2 中读取 Python3 保存的数据。

### np.savez()   
numpy.savez() 函数将多个数组保存到以 npz 为扩展名的文件中。 
```py
numpy.savez(file, args, *kwds) 
```
	参数说明：  
	file：要保存的文件，扩展名为 .npz，如果文件路径末尾没有扩展名 .npz，该扩展名会被自动加上。   
	args: 要保存的数组，可以使用关键字参数为数组起一个名字，非关键字参数传递的数组会自动起名为 arr0, arr1, …　。  
	kwds: 要保存的数组使用关键字名称（别名）。

### savetxt()  
savetxt() 函数是以简单的文本文件格式存储数据，对应的使用 loadtxt() 函数来获取数据。 
```py
np.loadtxt(FILENAME, dtype=int, delimiter=' ')
np.savetxt(FILENAME, a, fmt="%d", delimiter=",")
```
 注：参数 delimiter 可以指定各种分隔符、针对特定列的转换器函数、需要跳过的行数等。


## 二十一. 一些其他的函数

### np.random.multivariate_normal

生成一个服从多元正态分布的数组
```py
multivariate_normal(mean, cov, size=None, check_valid=None, tol=None)
``` 
	mean：均值，维度为1，必选参数；
	cov：协方差矩阵，必选参数；
	size： 指定生成矩阵的维度，若size=(1, 1, 2)，则输出的矩阵的 shape 即形状为 1X1X2XN（N为mean的长度）；
	check_valid：可取值 warn，raise以及ignore；
	tol：检查协方差矩阵奇异值时的公差，float类型；

### np.diag

提取对角线或构造对角线数组。
```py
numpy.diag（v，k = 0 ）

```
	v : 数组，如果是二维数组，返回对角线元素；如果是一维数组，返回一个二维数组，v在其对角线上。
	k ：int ，可选， 对角线的偏移量。k=0,选择主对角线；k>0 选择上方的对角线；反之，选择下方的对角线；
