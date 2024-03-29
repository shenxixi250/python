python中一个.py文件就是一个模块 

## 模块的使用
import 放到要注入的模块之前就可以了
包之间用逗号隔开  
```
import math,sys
	print(math.pi)
	print(sys.path)

```
### import几种方式比较

import和 import from和import from   区别
一般使用前两个最后一个可能会造成包名的冲突 
导入之后就可以使用里面的方法和变量名了

### 主模块和非主模块

主模块  就是调用其他模块的模块 没有被其他调用的模块的模块
可以查看`__name__`这个字段 他会显示如果这个字段返回的`__main__`的话这个就是主方法  

##包
我组织模块我们使用包  (Package)    引入包名之后  py.py 就要加上 包.py.py了   
但是每一个包目录下面都会有一个 __init__.py 的文件， 因为这个文件是必须的，否则，Python 就把这个目录当成普通目录，而不是一个包 。 __init__.py 可以是空文件，也可以有Python代码，因为` __init__.py `本身就是一个模块，而它对应的模块名就是它的包名。
## python中实现访问权限
在 Python 中，是通过 `_` 前缀来实现的。正常的函数和变量名是公开的（public），可以被直接引用，比如：abc，ni12，PI等；类似`__xxx__`这样的变量是特殊变量，可以被直接引用，但是有特殊用途，比如上面的 `__name__` 就是特殊变量，还有 `__author__` 也是特殊变量，用来标明作者。
在 Python 中，是通过 `_` 前缀来实现的。正常的函数和变量名是公开的（public），可以被直接引用，比如：abc，ni12，PI等；类似`__xxx__`这样的变量是特殊变量，可以被直接引用，但是有特殊用途，比如上面的 `__name__` 就是特殊变量，还有 `__author__` 也是特殊变量，用来标明作者。

注意，我们自己的变量一般不要用这种变量名；类似 `_xxx` 和 `__xxx` 这样的函数或变量就是非公开的（private），不应该被直接引用，比如 `_abc` ，`__abc` 等；

**这里是说不应该，而不是不能。因为 Python 种并没有一种方法可以完全限制访问 private 函数或变量，但是，从编程习惯上不应该引用 private 函数或变量。**


注意，我们自己的变量一般不要用这种变量名；类似 `_xxx` 和 `__xxx` 这样的函数或变量就是非公开的（private），不应该被直接引用，比如 `_abc` ，`__abc` 等；

**这里是说不应该，而不是不能。因为 Python 种并没有一种方法可以完全限制访问 private 函数或变量，但是，从编程习惯上不应该引用 private 函数或变量。**

## 魔术方法
```
if __name__ == '__main__':
	print(dir(User()))
	
```

输出的结果：

```
['__class__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__',
	'__getattribute__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__',
	'__module__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__',
	'__sizeof__', '__str__', '__subclasshook__', '__weakref__']
```

魔术方法就是帮助我们构造出优美的代码  使用内置的方法dir()来可以列出所有的内置方法 但是我们只要掌握常用的就可以了  下面我们介绍常用的几个

### 二、构造(`__new__`)和初始化(`__init__`)

关于`__init__`这个方法我们已经学习过了  就是用来给类对象进行初始化的

`def __new__(cls)` 是在 `def __init__(self)` 方法之前调用的，作用是返回一个实例对象。还有一点需要注意的是：`__new__` 方法总是需要返回该类的一个实例，而 `__init__`  不能返回除了 `None` 的任何值

具体的示例：

```python
#!/usr/bin/env python3
# -*- coding: UTF-8 -*-

class User(object):
    def __new__(cls, *args, **kwargs):
        # 打印 __new__方法中的相关信息
        print('调用了 def __new__ 方法')
        print(args)
        # 最后返回父类的方法
        return super(User, cls).__new__(cls)

    def __init__(self, name, age):
        print('调用了 def __init__ 方法')
        self.name = name
        self.age = age


if __name__ == '__main__':
    usr = User('两点水', 23)
```

看看输出的结果：

```txt
调用了 def __new__ 方法
('两点水', 23)
调用了 def __init__ 方法
```

通过打印的结果来看，我们就可以知道一个类创建的过程是怎样的了，先是调用了 `__new__` 方法来创建一个对象，把参数传给 `__init__` 方法进行实例化。

其实在实际开发中，很少会用到 `__new__` 方法，除非你希望能够控制类的创建。通常讲到 `__new__` ，都是牵扯到 `metaclass`(元类)的。

当然当一个对象的生命周期结束的时候，析构函数 `__del__` 方法会被调用。但是这个方法是 Python 自己对对象进行垃圾回收的。


### 三、属性的访问控制 

之前也有讲到过，Python 没有真正意义上的私有属性。然后这就导致了对 Python 类的封装性比较差。我们有时候会希望 Python 能够定义私有属性，然后提供公共可访问的 get 方法和 set 方法。Python 其实可以通过魔术方法来实现封装。

| 方法                             | 说明                                                                                                                                                                                                                                                 |
| ---                              | ---                                                                                                                                                                                                                                                  |
| `__getattr__(self, name)`        | 该方法定义了你试图访问一个不存在的属性时的行为。因此，重载该方法可以实现捕获错误拼写然后进行重定向, 或者对一些废弃的属性进行警告。                                                                                                                   |
| `__setattr__(self, name, value)` | 定义了对属性进行赋值和修改操作时的行为。不管对象的某个属性是否存在,都允许为该属性进行赋值.有一点需要注意，实现 `__setattr__` 时要避免"无限递归"的错误，                                                                                             |
| `__delattr__(self, name)`        | `__delattr__` 与 `__setattr__` 很像，只是它定义的是你删除属性时的行为。实现 `__delattr__` 是同时要避免"无限递归"的错误                                                                                                                              |
| `__getattribute__(self, name)`   | `__getattribute__` 定义了你的属性被访问时的行为，相比较，`__getattr__` 只有该属性不存在时才会起作用。因此，在支持 `__getattribute__ `的 Python 版本,调用`__getattr__` 前必定会调用 `__getattribute__``__getattribute__` 同样要避免"无限递归"的错误。 |

下面的教程讲了  

## 枚举   
## 元类 
##  进程和线程
## 正则表达式
## 闭包 和装饰器  

和我现在变成相关的就是 最后两个了  有空再看看
