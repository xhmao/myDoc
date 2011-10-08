==============
Python核心编程
==============

第一部分
========

Chapter 1 欢迎来到Python世界
============================

* 如果命令的路径不确定或者经常变化，env就非常有用，env会在PATH路径中搜索命令来执行，如下::
  #!/usr/bin/env python 
* 请找到自己系统中python标准库的路径

* 启动python解释器，在屏幕上打印*hello world*，然后退出解释器；编写一个脚本，这个脚本也是在屏幕上打印*hello world*

Chapter 2 Python起步
====================

* python有两种方式来完成你的要求：语句和表达式。语句使用关键字来组成命令，而表达式没有关键字

* 下划线*_*表示最后一个表达式的值

* print语句与字符串格式运算符*%*结合使用，可实现字符串的替换功能，这点和C语言的printf()函数相似；print也支持将输出重定向到文件(python2.0开始新增功能)::
  >>> print "%s is number %d!" % ("Python", 1)
  Python is number 1!

  >>> import sys
  >>> print >> sys.stderr, 'Fatal error: invalid input'
  Fatal error: invalid input

* raw_input()内建函数读取标准输入，并将读取到的数据赋值给指定的变量::
  >>> user = raw_input('Enter login name: ')
  Enter login name: root
  >>> print 'Your login is:', user
  Your login is:root

* int()内建函数将数字串转换成整数值::
  >>> num = raw_input('Now enter a number: ')
  Now enter a number: 1024
  >>> print 'Doubling your number: %d' % (int(num) * 2)
  Doubling your number: 2048

* help()内建函数可以帮助你得到相应的帮助信息，只需用一个生疏的函数名做参数::
  >>> help(raw_input)

* 2.2节的提示*核心风格*没看懂

* 注释从*#*开始到行结束，还有一种特别注释叫文档字符串，你可以在模块、类或者函数的起始添加一个字符串，起到在线文档的功能，这是JAVA程序员非常熟悉的一个特性::
  >>> #one comment
  >>> def foo():
  ...   "这是一个文档字符串"
  ...   return True

* 运算符::
  -算术运算符：+ - * / // % **
  -比较运算符：< <= > >= == != <>
  -逻辑运算符：and or not

* python支持这样的表达式::
  >>> 3 < 4 < 5
  True

* python的变量是大小写敏感的，python是动态类型语言，不需要预先声明变量的类型，变量的类型和值在赋值的那一刻被初始化。变量赋值通过等号来执行::
  >>> counter = 0
  >>> miles = 1000.0
  >>> name = 'Bob'

* python支持五种基本的数字类型，其中三种是整数类型，python中的长整形和C语言不同，他所能表达的范围远远超过C语言的长整数，事实上，python的长整数仅受限于虚拟内存的总数::
  - int
  - long
  - bool
  - float
  - complex

* python中字符串被定义为引号之间的字符集合。python支持使用成对的单引号或双引号，三引号(三个连续的单引号或双引号)可以用来包含特殊字符。使用索引或切片运算符可以得到子字符串。字符串有其特有的索引规则：第一个字符索引是0，最后一个字符索引是-1。加号*+*用于字符串连接，星号***则用于字符串重复::
  >>> 'Python' + ' is cool!'
  'Python is cool!'
  >>> 'Python' * 2
  'PythonPython'

* 列表和元组可以保存任意数量任意类型的Python对象，和数组一样，通过从0开始的数字索引访问元素。列表用中括号*[]*包裹，元组用小括号*()*包裹。元组可以看成是只读的列表。通过切片运算符可以得到子集。

* 字典是python中的映射数据类型，由键-值对构成。几乎所有类型的python对象都可以用作键，不过一般还是以数字或者字符串最为常用。值可以是任意类型的python对象，字典元素用大括号*{}*包裹

* 代码块通过缩进对其表达代码逻辑，而不是使用大括号

* if条件语句::
  if expression:
    if_suite
  elif expression:
    elif_suite
  else:
    else_suite

* while循环语句::
  while expression:
    while_suite

* for循环语句::
  for item in iter
    for_suite

* range(), len(), enumerate()

* 列表解析或叫列表表达式，这是个让人欣喜的功能::
  >>> squared = [x ** 2 for x in range(4)]
  >>> for i in squared
  ...  print i
  0
  1
  4
  9
  >>> sqdEvens = [x ** 2 for x in range(8) if not x % 2]

* open('filename', 'rwab+'), file()

* 属性是与数据有关的项目，属性可以是简单的数值，也可以是可执行的对象，如函数和方法。拥有属性的对象很多，如类、模块、文件还有复数等等对象都有属性。我们使用句点访问属性::
  object.attribute

* 错误和异常：try-except，我们可以通过raise语句引发一个异常

* 函数使用小括号*()*调用，函数在调用之前必须先定义。如果函数中没有return语句，就会自动返回None对象。python是通过引用调用的。这意味着函数内对参数的改变会影响到原始的对象::
  >>> def foo()
  ...  return True

* 类，可以提供一个可选的父类，如果没有适合的基类，就使用object做基类，所有名字开始和结束都有两个下划线的方法都是特殊方法

* 当一个类的实例被创建时，__init__()方法会自动执行，类似构造函数，每个方法都有一个self参数，它是类实例自身的引用。其他语言通常使用一个名为this的标识符::
  >>> class FooClass(object):
  ...   """my very first class:FooClass"""
  ...   version = 0.1 #class attribute
  ...   def __init__(self, nm='xhmao'):
  ...     """constructor"""
  ...     self.name = nm
  ...     print 'Created a class instance for', nm
  ...
  ...   def showself, xx):
  ...     ...
  ...
  >>> fool = FooClass()
  >>> fool.show(xx)

* 模块，模块导入和属性的引用

* PEP(Python Enhancement Proposal)：Python增强提案

* type()可以查看对象的类型::
  >>> type(dir)
  >>> type('fmsoft')

Chapter 3 Python基础
====================

* python语句一般使用换行分割，一行过长的语句可以使用反斜杠*\*分解成几行。有一种例外不用反斜杠也可以跨行，在使用闭合操作符时可以多行书写。另外就是三引号包括下的字符串也可以跨行书写。

* 链式赋值是被允许的，增量赋值也是允许的，但是自增自减不被允许::
  >>> y = x = x + 1
  >>> x += 1

* python在赋值之前，已经对新值做了计算，因此对于python，要交换两个变量的值，只需这样做::
  >>> x, y = 1, 2
  >>> x, y = y, x

* **68页表3.1列出了python的关键字**

* python用下划线做变量前缀和后缀指定特殊变量::
  _xxx 不用'from module import *'导入
  __xxx__ 系统定义名字
  __xxx 类中的私有变量名

* 这里有一种较为合理的布局::
  - 起始行
  - 模块文档
  - 模块导入
  - 变量定义
  - 类定义
  - 函数定义
  - 主程序

* 如果模块是被导入的，__name__的值就是模块的名字，如果模块是直接被执行的，则值为*__main__*::
  >>> if __name__ == '__main__':
  ...   main()  #或者unittest()

* 要保持追踪内存中的对象，python使用了引用计数这一简单技术。del语句会删除对象的一个引用，下列情况引用计数会增加::
  - 对象被创建
  - 另外的别名被创建
  - 或被作为参数传递给函数
  - 或成为容器对象的一个元素

* 下列情况引用计数会减少::
  - 一个本地引用离开了其作用范围
  - 对象的别名被显式的销毁
  - 对象的一个别名被赋值给其他对象
  - 对象被从一个窗口对象中移除:myList.remove(x)
  - 窗口对象本身被销毁:del myList

* **try-except-else**

* **print a,** ，print语句后面加一个逗号可以避免print自动输入换行

* 一些模块会帮到你::
  - Debugger: pdb
  - Logger: logging
  - Profilers: profile, hotshot, cProfile

* logging模块在python2.3中新增，共有5个级别： **紧急、错误、警告、信息、调试**

Chapter 4 Python对象
====================

* 所有对象都拥有三个特征：身份、类型、值。除了值，其他两个特征都是只读的

* 用type()得到的类型也是个对象，不是一个简单的字符串

* 标准类型::
  - 数字 - 整型 - 布尔型 - 长整型 - 浮点型 - 复数型 - 字符串 - 列表 - 元组 - 字典

* 其他内建类型::
  - 类型 - Null对象 - 文件 - 集合/固定集合 - 函数/方法 - 模块 - 类

* 下列对象的布尔值是False::
  - None - False - 所有值为0的数 - 0 - 0L - 0.0+0.0j - "" - [] - () - {}

* 内部类型::
  - 代码 - 帧 - 跟踪记录 - 切片 - 省略 - Xrange

* 运算符*is*和*is not*用来测试两个变量是否指向同一个对象

* Python只缓存简单的整数::
  >>> a=1
  >>> b=1
  >>> a is b
  True
  >>> a=111111
  >>> b=111111
  >>> a is b
  False

* **p107表4.5总结了标准类型运算符和内建函数**

* 类型工厂函数::
  int(), long(), float(), complex()
  str(), unicode(), basestring()
  list(), tuple()
  type()
  dict()
  bool()
  set(), frozenset()
  object()
  classmethod()
  staticmethod()
  super()
  property()
  file()

* 一个能保存单个字面对象的类型我们称它为原子或者标量存储，那些可容纳多个对象的类型，我们称之为容器存储::
  存储模型
  标量类型：数值，字符串 
  容器类型：列表、元组、字典 

* 以更新模型为标准的类型分类::
  更新模型
  可变类型：列表，字典 
  不可变类型：数字，字符串，元组 

* 访问模型中共有三种访问方式：直接存取，顺序，映射::
  访问模型 
  直接访问：数字
  顺序访问：字符串，列表，元组 
  映射访问：字典 

* 标准类型分类::
  数据类型  存储模型  更新模型  访问模型 
  数字      scalar    不可更改  直接访问 
  字符串    scalar    不可更改  顺序访问
  列表      container 可更改    顺序访问 
  元组      container 不可更改  顺序访问 
  字典      container 可更改    映射访问

Chapter 5 数字
==============

* 大写字母*L*表示长整数::
  aLong = 999999999999L

* abs(), coerce(), divmod(), pow(), round()

* oct(), hex()

* chr(), ord()

* unichr()

Chapter 6 序列：字符串、列表和元组 
==================================


第二部分
========

Chapter 19 图形用户界面编程
===========================












