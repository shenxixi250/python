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


