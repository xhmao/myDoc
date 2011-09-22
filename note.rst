==============
Python核心编程
==============

Chapter 1
=========

* 如果命令的路径不确定或者经常变化，env就非常有用，env会在PATH路径中搜索命令来执行，如下::
  #!/usr/bin/env python

* 请找到自己系统中python标准库的路径

* 启动python解释器，在屏幕上打印*hello world*，然后退出解释器；编写一个脚本，这个脚本也是在屏幕上打印*hello world*

Chapter 2
=========

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

p48













