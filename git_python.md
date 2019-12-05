1 z注释 #  后用空一格

2 文档注释 
“”“ 文档注释
开始
结束
”“”

命名 
模块全小写
import html

类名 驼峰式
AnimalFarm

函数一律小写多个字母用下划线
nihao__wobuahidao()

变量名小写 多个单词下划线 
count=0；
常量全大写
MAX__LIFE=122

##第一个py
print（‘hello world’）

##简要语法说明
用缩进代表{}关系 也就是当语句以：结尾时要缩进一行 缩进的语句别称做代码块

##python中的数据类型 
‘’ 扩中的字符串  不会照着本意输出  如
“” 会照着本意输出  
‘’‘
’‘’  可以分行


整数  python可以处理任意大小的整数

小数 0.1 带小数点的

type（） 可以查看类型

布尔类型 True 和 False 可以使用 or and not 运算

空值 none


## 编码问题
```
#! /usr/bin/env python
# -*- coding: utf-8 -*- 

第一行告诉linux 这是一个可执行程序 window会忽略这个注释
第二行 告诉python解释器 按照UTF-8 来读取源代码
```
| 方法                   | 说明                                                  |
|------------------------|-------------------------------------------------------|
| int(x [,base ])        | 将x转换为一个整数                                     |
| float(x )              | 将x转换到一个浮点数                                   |
| complex(real [,imag ]) | 创建一个复数                                          |
| str(x )                | 将对象 x 转换为字符串                                 |
| repr(x )               | 将对象 x 转换为表达式字符串                           |
| eval(str )             | 用来计算在字符串中的有效 Python 表达式,并返回一个对象 |
| tuple(s )              | 将序列 s 转换为一个元组                               |
| list(s )               | 将序列 s 转换为一个列表                               |
| chr(x )                | 将一个整数转换为一个字符                              |
| unichr(x )             | 将一个整数转换为 Unicode 字符                         |
| ord(x )                | 将一个字符转换为它的整数值                            |
| hex(x )                | 将一个整数转换为一个十六进制字符串                    |
| oct(x )                | 将一个整数转换为一个八进制字符串                      |


int() 将小数转化成为整数是直接去掉 小数点的部分

## 变量

首先是变量必须符合命名规则
支持 连续赋值 a=b=c=d=1
和 a，b，c = 1，2，‘niaho’
##列表  

列表就是一个容器   可以随时添加和删除操作
格式就是 
列表名 赋值符号 ['一','二两岁']
listname = ['一','二两岁']
逗号括起来的是元素    和java有所不同java的类似与列表的容器是数组和LIst 但是他们只支持一种数据类型  也就是 里面的元素 都是一种数据类型     

访问列表中的值   
print(name[2])
print(name[0:2])  这个是取列表中的name[0],name[1] 这两个元素也就是我们说的
左闭右开 
name = [1,'2',3,'34']
print(name[0:2])
print(name[:2])
print(name[:])
结果是

[1, '2']
[1, '2']
[1, '2', 3, '34']

如何删除列表里面的值 
del name[3]
值得注意的是下面这个语句没有什么用途
    
del name[:2]


### List列表运算符
列表对 + 和 * 的操作符与字符串相似。+ 号用于组合列表，* 号用于重复列表。
| Python 表达式         | 结果                         | 描述         |
|-----------------------|------------------------------|--------------|
| len([1, 2, 3])        | 3                            | 计算元素个数 |
| [1, 2, 3] + [4, 5, 6] | [1, 2, 3, 4, 5, 6]           | 组合         |
| ['Hi!'] * 4           | ['Hi!', 'Hi!', 'Hi!', 'Hi!'] | 复制         |
| 3 in [1, 2, 3]               | True                         | 元素是否存在于列表中 |
| for x in [1, 2, 3]: print x, | 1 2 3                        | 迭代                 |

 ## list 函数方法

| 函数&方法               | 描述                                                               |
|-------------------------|--------------------------------------------------------------------|
| len(list)               | 列表元素个数                                                       |
| max(list)               | 返回列表元素最大值                                                 |
| min(list)               | 返回列表元素最小值                                                 |
| list(seq)               | 将元组转换为列表                                                   |
| list.append(obj)        | 在列表末尾添加新的对象                                             |
| list.count(obj)         | 统计某个元素在列表中出现的次数                                     |
| list.extend(seq)        | 在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表） |
| list.index(obj)         | 从列表中找出某个值第一个匹配项的索引位置                           |
| list.insert(index, obj) | 将对象插入列表                                                     |
| list.pop(obj=list[-1])  | 移除列表中的一个元素（默认最后一个元素），并且返回该元素的值       |
| list.remove(obj)        | 移除列表中的一个元素（参数是列表中元素），并且不返回任何值         |
| list.reverse()          | 反向列表中元素                                                     |
| list.sort([func])       | 对原列表进行排序                                                   |


name = [1,'2',3,'34']
print(name[0:2])
print(name[:2])
print(name[:])
del name[1]
print(name)
print(len(name))
name1=[1,2,3,2,1,3,12,312,121]
print(max(name1))
print(name1)
print(min(name1)) 
print(name1.append(1))       
print(name1)
print(name1.count(1))        
print(name1)
print(name1.extend([1,2,3]))       
print(name1)
print(name1.index(3))        
print(name1)
print(name1.pop()) 
print(name1)
print(name1.remove(1))       
print(name1)
print(name1.reverse())         
print(name1)
print(name1.insert(1,"nihao"))
print(name1)
```
[1, '2']
[1, '2']
[1, '2', 3, '34']
[1, 3, '34']
3
312
[1, 2, 3, 2, 1, 3, 12, 312, 121]
1
None
[1, 2, 3, 2, 1, 3, 12, 312, 121, 1]
3
[1, 2, 3, 2, 1, 3, 12, 312, 121, 1]
None
[1, 2, 3, 2, 1, 3, 12, 312, 121, 1, 1, 2, 3]
2
[1, 2, 3, 2, 1, 3, 12, 312, 121, 1, 1, 2, 3]
3
[1, 2, 3, 2, 1, 3, 12, 312, 121, 1, 1, 2]
None
[2, 3, 2, 1, 3, 12, 312, 121, 1, 1, 2]
None
[2, 1, 1, 121, 312, 12, 3, 1, 2, 3, 2]
None
[2, 'nihao', 1, 1, 121, 312, 12, 3, 1, 2, 3, 2]
```
元组（tuple） 不可变是指当你创建了 tuple 时候，它就不能改变了，也就是说它也没有 append()，insert() 这样的方法，但它也有获取某个索引值的方法，但是不能赋值。
如何创建元组呢
元组创建很简单，只需要在括号中添加元素，并使用逗号隔开即可。

tuple1=('两点水','twowter','liangdianshui',123,456)
tuple2='两点水','twowter','liangdianshui',123,456

创建空元组
tuple3=()
元组中只包含一个元素时，需要在元素后面添加逗号
tuple4=(123,)
如果不加逗号，创建出来的就不是 元组（tuple），而是指 123 这个数了。
这是因为括号 () 既可以表示元组（tuple），又可以表示数学公式中的小括号，这就产生了歧义。
所以如果只有一个元素时，你不加逗号，计算机就根本没法识别你是要进行整数或者小数运算还是表示元组。
因此，Python 规定，这种情况下，按小括号进行计算，计算结果自然是 123 ，而如果你要表示元组的时候，就需要加个逗号。

元组的 标志是逗号  
数组的标志是[]加,号
i

### 修改元组 

虽然不可以改变 但是可以进行连接和组合
```
#-*-coding:utf-8-*-
list1=[123,456]
tuple1=('两点水','twowater','liangdianshui',list1)
print(tuple1)
list1[0]=789
list1[1]=100
print(tuple1)
```

```
('两点水', 'twowater', 'liangdianshui', [123, 456])
('两点水', 'twowater', 'liangdianshui', [789, 100])
```

### delect tuple

```
#-*-coding:utf-8-*-

tuple1=('两点水','twowter','liangdianshui',[123,456])
print(tuple1)
del tuple1
```
| Python 表达式                | 结果                         | 描述         |
|------------------------------|------------------------------|--------------|
| len((1, 2, 3))               | 3                            | 计算元素个数 |
| (1, 2, 3) + (4, 5, 6)        | (1, 2, 3, 4, 5, 6)           | 连接         |
| ('Hi!',) * 4                 | ('Hi!', 'Hi!', 'Hi!', 'Hi!') | 复制         |
| 3 in (1, 2, 3)               | True                         | 元素是否存在 |
| for x in (1, 2, 3): print(x) | 1 2 3                        | 迭代         |

### 元组内置函数
| 方法       | 描述                 |
| len(tuple) | 计算元组元素个数     |
| max(tuple) | 返回元组中元素最大值 |
| min(tuple) | 返回元组中元素最小值 |
| tuple(seq) | 将列表转换为元组     |

字典
相当于java中的map
name={‘nihao’：hello ，‘nanren’：man， ‘shenxixi’：handsome}  
简单描述就是 键值对用：  每对之间的， 最后{}

要注意键必须唯一 值不必唯一


访问字典
print（name【‘nihao’】）
hello
如果字典中没有这个键会报错

修改字典

新增 
namei【‘shenxixi’】=‘zhuanye’
修改
name【‘nihao’】= ‘hi’

删除
del 【‘nihao’】 删除单个键值
del name 删除整个字典表



set 集合




函数
def sum（num1，num2）：
“两数之和”
	if not（isinstance （num1，（int，float）） and isinstance（num2，（int，float）））：
		raise TypeError（‘参数有错误’）
	return num1+num2 ，num1-num2
num3 ，num4 = division（9，4）# 注意这种特别的赋值方式是很方便的
tuple1 = division（9，4）#这个要注意python中一次能接受多个返回值的类型一定就是元组  



函数的参数

1. 主要的参数类型有  : 默认参数 ,关键之参数(位置的参数) 
默认参数  就是在构造函数的时候给参数赋值就可以了 

```
# -*- coding: UTF-8 -*-

def print_user_info( name , age , sex = '男' ):
    # 打印用户信息
    print('昵称：{}'.format(name) , end = ' ')
    print('年龄：{}'.format(age) , end = ' ')
    print('性别：{}'.format(sex))
    return;

# 调用 print_user_info 函数

print_user_info( '两点水' , 18 , '女')
print_user_info( '三点水' , 25 )
```

```

```


但是这里需要注意的一点是：只有在形参表末尾的那些参数可以有默认参数值，也就是说你不能在声明函数形参的时候，先声明有默认值的形参而后声明没有默认值的形参。

这是因为赋给形参的值是根据位置而赋值的。例如，def func(a, b=1) 是有效的，但是 def func(a=1, b) 是 无效 的。

还有一种情况  就是如果 我们的参数是一个list 或者dict 南无我们使用什么来作为默认值呢
我们可以只用None来作为我们 的默认值 
```
# 如果 b 是一个 list ，可以使用 None 作为默认值
def print_info( a , b = None ):
    if b is None :
        b=[]
    return;
```



认真看下例子，会不会有这样的疑问呢？在参数中我们直接 b=[] 不就行了吗？

也就是写成下面这个样子：
```
def print_info( a , b = [] ):
    return;
```

对不对呢？

运行一下也没发现错误啊，可以这样写吗？

这里需要特别注意的一点：默认参数的值是不可变的对象，比如None、True、False、数字或字符串，如果你像上面的那样操作，当默认值在其他地方被修改后你将会遇到各种麻烦。

这些修改会影响到下次调用这个函数时的默认值。

示例如下：
```
# -*- coding: UTF-8 -*-

def print_info( a , b = [] ):
    print(b)
    return b ;

result = print_info(1)

result.append('error')

print_info(2)
```
输出的结果：
```
[]
['error']
```

还有一种使用
```
_no_value =object()

def print_info( a , b = _no_value ):
    if b is _no_value :
        print('b 没有赋值')
    return;
```


## 关键字参数位置 

就是我们传参数的时候就告诉这个变量是我们准备传给那个变量的


```

def print_user_info( name ,  age  , sex = '男' ):
    # 打印用户信息
    print('昵称：{}'.format(name) , end = ' ')
    print('年龄：{}'.format(age) , end = ' ')
    print('性别：{}'.format(sex))
    return;



# 调用 print_user_info 函数

print_user_info( name = '两点水' ,age = 18 , sex = '女')
print_user_info( name = '两点水' ,sex = '女', age = 18 )
```

这样就很方便了


还有一种就是不定长的参数

```
# -*- coding: UTF-8 -*-

def print_user_info( name ,  age  , sex = '男' , * hobby):
    # 打印用户信息
    print('昵称：{}'.format(name) , end = ' ')
    print('年龄：{}'.format(age) , end = ' ')
    print('性别：{}'.format(sex) ,end = ' ' )
    print('爱好：{}'.format(hobby))
    return;

# 调用 print_user_info 函数
print_user_info( '两点水' ,18 , '女', '打篮球','打羽毛球','跑步')
```
其实在参数面前加上星号的意思就是 这个是一个空元组   我们也可以不向函数传递没有命名的变量


但是如果我们想向没有 可变长的变量中输入字典我们又该怎么做呢
```
# -*- coding: UTF-8 -*-

def print_user_info( name ,  age  , sex = '男' , ** hobby ):
    # 打印用户信息
    print('昵称：{}'.format(name) , end = ' ')
    print('年龄：{}'.format(age) , end = ' ')
    print('性别：{}'.format(sex) ,end = ' ' )
    print('爱好：{}'.format(hobby))
    return;

# 调用 print_user_info 函数
print_user_info( name = '两点水' , age = 18 , sex = '女', hobby = ('打篮球','打羽毛球','跑步'))

昵称：两点水 年龄：18 性别：女 爱好：{'hobby': ('打篮球', '打羽毛球', '跑步')}	
```

### 只接受关键字参数

关键字参数使用起来简单，不容易参数出错，那么有些时候，我们定义的函数希望某些参数强制使用关键字参数传递，这时候该怎么办呢？
```
将强制关键字参数放到某个*参数或者单个*后面就能达到这种效果,比如：

# -*- coding: UTF-8 -*-

def print_user_info( name , *, age  , sex = '男' ):
    # 打印用户信息
    print('昵称：{}'.format(name) , end = ' ')
    print('年龄：{}'.format(age) , end = ' ')
    print('性别：{}'.format(sex))
    return;

# 调用 print_user_info 函数
print_user_info( name = '两点水' ,age = 18 , sex = '女' )

# 这种写法会报错，因为 age ，sex 这两个参数强制使用关键字参数
#print_user_info( '两点水' , 18 , '女' )
print_user_info('两点水',age='22',sex='男')

通过例子可以看，如果 age , sex 不使用关键字参数是会报错的。

很多情况下，使用强制关键字参数会比使用位置参数表意更加清晰，程序也更加具有可读性。使用强制关键字参数也会比使用 **kw 参数更好且强制关键字参数在一些更高级场合同样也很有用。
```


### 函数传值的问题
```
def change_number(b):
	b=122
b=1
change_number(b)
print(b)
```
输出结果是1 

这里主要是函数参数的传递中，传递的是类型对象，之前也介绍了 Python 中基本的数据类型等。而这些类型对象可以分为可更改类型和不可更改的类型

在 Python 中，字符串，整形，浮点型，tuple 是不可更改的对象，而 list ， dict 等是可以更改的对象。

例如：

不可更改的类型：变量赋值 a = 1，其实就是生成一个整形对象 1 ，然后变量 a 指向 1，当 a = 1000 其实就是再生成一个整形对象 1000，然后改变 a 的指向，不再指向整形对象 1 ，而是指向 1000，最后 1 会被丢弃

可更改的类型：变量赋值 a = [1,2,3,4,5,6] ，就是生成一个对象 list ，list 里面有 6 个元素，而变量 a 指向 list ，a[2] = 5则是将 list a 的第三个元素值更改,这里跟上面是不同的，并不是将 a 重新指向，而是直接修改 list 中的元素值。


<++>
