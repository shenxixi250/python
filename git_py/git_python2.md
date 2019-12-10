## 迭代

那些可以迭代
1 list tuple 这两个类 类数组形式的

for x in list
	print（x）
for x，y in 【（1，‘a’），（2，b）】
	print（x，y）
2 dict 字典也可以
for key in dict；
	print（key）
for value in dict
	print（value）


3 迭代器
讲白了就是在一定程度上替换 for 带来作用

没太看明白 oye



pass  就是一个空语句没有什么其他含义 是为了保持结构的完整性


python中的闭包

主要解决的是 函数的局部变量不能够保存信息 ,也就是在函数声明变量在函数调用结束之后函数中保存的变量信息就被销毁  

如 

def fun(step):
	num=1
	num+=step
	print(num)
i=1
while(i<5):
	fun(3)
	i+=1

这个的输出结果是每次都是4  也就是没有改变 的意思  局部变量没有被保存下来

所以我们要引入闭包 

闭包有两种形式 
闭包的本质就是函数的嵌套定义 ,也就是在函数内部在定义函数   

1 直接调用
def Maker(name):
	num=100
	def func1(weight,height,age):
	weight+=1
	height+=1
	age+=1
	print(name,wight,height,age)
func1(100,200,300)
Maker('feifei')


第二种形式就是返回函数名称
def Maker(name):
	num=100
	def func1(weight,height,age):
	weight+=1
	height+=1
	age+=1
	print(name,wight,height,age)
return func1
maker = Marker('feifei')
maker(100,200,300)

要注意这里不会循环调用 要在我们外部控制  

其实都是大同小异的


接着 闭包的原理我们要说一下 python的一个重要的性质就是  
装饰器

我的理解  其实就是python版本的实现类装饰者模式   

就是  在不改变原函数的基础上我们可以进行函数的拼装来实现我们想要的功能

例如  

def punch():
	print('我来上班了')

punch()

这个函数实现了上班打卡的 功能  

现在我们想要给他加一个时间的变量  让他能显示出具体的时间

方法1 当然就是直接修改我们的函数  这个很简单就不说了

方法二 我们可以使用函数的编程来修改这部分的代码  我们知道函数编程有两个特点
1 函数也是一个对象
2 函数可以嵌套函数

import datatime
def punch():
	print('我来上班了')
def add_time():
	print(datatime.datatime.now().strftime('%Y-%m-%d'))
	func()

add_time(punch)

这个就是我们的结果了  

可以通过对比发现  装饰器更简洁也符合python的审美 
还有更简洁的写法就是  通过@decortor 来进行装配 

# 面向对象的

类和对象的关系

面向对象的三大特征

简单的来说就是类是对象和变量的集合 
定义类 
```
class ClassName()
	<statement1>
	<statement2>
	'
	'
	<statementN>
```

```
class ClassA()
	var = 1
	var3= 0.1
	var4 ='sxx'
	def fun1():
		print('woshisuai')
	def fun2():
		print('nihao')
```

调用格式是
print(ClassA.var1)
print(ClassA.var3)
print(ClassA.var4)
Class.fun1()

要注意的是类方法调用类属性
```
class test()
	var = 1
	@classmethod#类方法
	def print1(cls,age): #cls指代当前的类
		print(cls.__name__) #获取当前类名
		print(cls.var)
		print(age)
```




修改和增加类属性 

1从内部来修改类属性

```python
	class nihao():
		var=1
		@classmethod
		def fun(cls):
			print('修改为2'+cls.var)
	
	nihao.fun(
```
2 从类的外部修改




类的实例化  
要强调一下前面学习的都是直接使用类  
格式如上  下面我们看一下类的实例化的对比
```
class test(object)#这里面放object是继承的意思 
	var=1
	def fun1(self)# 没有了@classmethon,cls 变成了 self
		print('var的值为'+var)
#实例化
a=test()
#实例化之后使用里面的方法或者属性
a.fun1()
print(a.var)
```

对于对象中的变量来说
实例化的类 类改变对象会跟着变 
对象变化 实例化的类不会改变

对于对象中的方法来说
实例化的类改变方法 对象会跟着变
对象不能够重写实例化方法 会直接报错


当代码在执行 `a = ClassA()` 的语句时，就自动调用了 `__init__(self)` 函数。

**而这个 `__init__(self)`  函数就是初始化函数，也叫构造函数。**

初始化函数的写法是固定的格式：中间是 `init`，意思是初始化，然后前后都要有【两个下划线】，然后 `__init__()` 的括号中，第一个参数一定要写上 `self`，不然会报错。

构造函数（初始化函数）格式如下：

```python
def __init__(self,[...):
```
当然初始化函数也是可以传递参数的

```
Class test(object)
	def __init__(self,str)
		print(str)
	def __del__(self)
		print('析构函数启动')

a = test('niaho')
del a
```
上面的代码会输出结果 
nihao 
析构函数启动

和`__init__(self)`一样 我们的`__del__(self)`函数在类被销毁的时候就会使用


继承关系 
1 python支持多继承
2 

```

#!/usr/bin/env python3
# -*- coding: UTF-8 -*-

class User(object):
    def __init__(self, name):
        self.name = name

    def printUser(self):
        print('Hello !' + self.name)


class UserVip(User):
    def printUser(self):
        print('Hello ! 尊敬的Vip用户：' + self.name)


class UserGeneral(User):
    def printUser(self):
        print('Hello ! 尊敬的用户：' + self.name)


def printUserInfo(user):
    user.printUser()


if __name__ == '__main__':
    userVip = UserVip('两点水')
    printUserInfo(userVip)
    userGeneral = UserGeneral('水水水')
	print(isinstance(userVip,user))
    printUserInfo(userGeneral)
```

```txt
Hello ! 尊敬的Vip用户：两点水
True
Hello ! 尊敬的用户：水水水
```
这段代码我们可以总结出三个要掌握的地方 
1 子类重写父类方法后调用的方法是子类的
2 也会继承父类的`__init__(self)`方法
3 isinstance 是判断是不是这个类型的函数


类属性的访问控制
java中有public private protect 和默认来控制  但是python中没有
只有假控制  
一般情况下，我们会使用 `__private_attrs` 两个下划线开头，声明该属性为私有，不能在类地外部被使用或直接访问。在类内部的方法中使用时 `self.__private_attrs`。
实际上是不行的我们举例来说就是


```python
	#!/usr/bin/env python3
	# -*- coding: UTF-8 -*-
	
	class User(object):
	    def __init__(self, name):
	        self.name = name
	
	    def printUser(self):
	        print('Hello !' + self.name)
	
	
	class UserVip(User):
	    def printUser(self):
	        print('Hello ! 尊敬的Vip用户：' + self.name)
	
	
	class UserGeneral(User):
	    def printUser(self):
	        print('Hello ! 尊敬的用户：' + self.name)
	
	
	def printUserInfo(user):
	    user.printUser()
	
	
	if __name__ == '__main__':
	    userVip = UserVip('两点水')
	    printUserInfo(userVip)
	    userGeneral = UserGeneral('水水水')
	    printUserInfo(userGeneral
```
结果就是 

```

|| [python3 py.py]
|| ['_UserInfo__account', '__class__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__module__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', '__weakref__', '_age', 'get_account', 'name']
|| {'name': '两点水', '_age': 23, '_UserInfo__account': 347073565}
|| 347073565
|| 347073565
|| [Finished in 0 seconds]
```

通过结果我们可以看出来  即使不用那个get方法我们依然可以访问到我们想要的变量值
类的专有方法：

| 方法           | 说明                       |
| ------         | ------                     |
| `__init__`     | 构造函数，在生成对象时调用 |
| `__del__ `     | 析构函数，释放对象时使用   |
| `__repr__ `    | 打印，转换                 |
| `__setitem__ ` | 按照索引赋值               |
| `__getitem__`  | 按照索引获取值             |
| `__len__`      | 获得长度                   |
| `__cmp__`      | 比较运算                   |
| `__call__`     | 函数调用                   |
| `__add__`      | 加运算                     |
| `__sub__`      | 减运算                     |
| `__mul__`      | 乘运算                     |
| `__div__`      | 除运算                     |
| `__mod__`      | 求余运算                   |
| `__pow__`      | 乘方                       |

当然有些时候我们需要获取类的相关信息，我们可以使用如下的方法：

* `type(obj)`：来获取对象的相应类型；
* `isinstance(obj, type)`：判断对象是否为指定的 type 类型的实例；
* `hasattr(obj, attr)`：判断对象是否具有指定属性/方法；
* `getattr(obj, attr[, default])` 获取属性/方法的值, 要是没有对应的属性则返回 default 值（前提是设置了 default），否则会抛出 AttributeError 异常；
* `setattr(obj, attr, value)`：设定该属性/方法的值，类似于 obj.attr=value；
* `dir(obj)`：可以获取相应对象的所有属性和方法名的列表：

