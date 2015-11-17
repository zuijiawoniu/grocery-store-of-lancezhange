# Python

#### 魔力方法/属性

 我们知道，python 中，**一切皆对象**，同时，python 也是一门多范式的语言：面向过程/面向对象/函数式和谐共存，这背后的奥秘就是 **magic method**.

 事实上，许多运算符和内置函数都是用魔力方法实现的。例如，*+* 其实是 `__add__()`, `len()` 为 `__len__()`，而任何具有`__call__()` 方法的对象都被当做是函数。此外，`with `**上下文管理器**也是借助`__enter__()` 和 `__exit__()`魔力函数实现的。

 如下列举一些重要的魔力方法和魔力属性

1. `__dict__` : 属性列表，`object.attr` 其实就是 `object.__dict__[attr]`，许多内置类型，如 list, 都没有该属性；类的属性
2. `__class__`, `__bases__`,`__name__`,
2. `__slots__` 对拥有该属性的类的对象，只能对`__slots__`中列出的属性做设置
3. 用以包构建的，如 `__all__`
4. `__setitem__`
5. `__init__()`,`__new__`
6. `__repr__`, `__str__`
7. `__exit__(self, type, value, traceback)`
8. `__iter__`(通常和 `yield` 一起用以定义可迭代类)
9. 



#### 动态类型

对象是存储在内存中的实体，程序中用到的名称不过是对象的引用。**引用和对象分离**
乃是动态类型的核心。引用可以随时指向新的对象，各个引用之间互相独立。

可变数据类型，如列表，可以通过引用改变自身，而不可变元素，如字符串，不能改变引用对象本身，只能改变引用的指向。

函数的参数传递，本质上传递的是引用，因此，如果参数是不可变对象，则对参数的操作不会影响原对象，这类似于C++中的值传递；但如果传递的是可变参数，则有可能改变原对象。

#### lamda 函数

我最早是在 haskell 中见到匿名函数的，后来它被加入到了 python 以及 java 中。python 中定义 lamda 函数很简单：

        func = lambda x,y: x+y

其他函数式编程的经典函数如 map, filter, reduce 等，我最早也是在 haskell 中见到的。大多类似，不再赘述。

#### 迭代器

- 循环对象 例如open() 返回的就是一个循环对象，具有 `next()` 方法，最终举出 `StopIteration` 错误
- 迭代器 和循环对象没有差别装饰器
- 生成器 用以构建用户自定义的循环对象，这要用到神秘的`yield`关键字

#### 装饰器

函数装饰器接受一个可调用对象作为参数，并返回一个新的可调用对象。装饰器也可以带有参数，从而更为灵活。类装饰器同理。

例如，上下文管理也可以用 *contexlib* 模块用装饰器的方式实现。

@statcimethod

@classmethod

@property


#### 闭式

闭式可以减少定义函数时的参数，例如可以利用闭包来定义泛函。

#### 元类(metaclass)

我们说过，python 中一切皆对象，就连类也是对象！metaclass 便是用来创建类对象的类。`__class__` 的 `__class__` 为 `type`, 是 python 中内置的创建类的元类。

自定义元类： `__metaclass__`，可以被赋值为任意可调用对象

#### 描述符

`__get__`, `__set__` , `__delete__` ： 实现这三个就能做描述符

#### 继承
1. super()
2. MRO(method resolution order): 也就是通常说的继承顺序，并非简单的深度或者宽度优先，而是确保所有父类不会出现在子类之前
3. `self`, `cls`


#### 协程
协程，用户级线程，可以`让原来要使用异步+回调方式写的非人类代码,可以用看似同步的方式写出来`。具体地，它可以保留上一次调用的状态，和线程相比，没有了线程切换的开销。

`yield`, `next()`, `.send()`, `.close()`



#### 并行

#### 自省(introspection)

`dir`, `type`, `id`

`inspect` 模块

####  性能优化建议/debug

debug： *pdb*模块

[官方 Performance Tips](https://wiki.python.org/moin/PythonSpeed/PerformanceTips)
##### C 接口
1. CDLL() 加载动态库，和 R 中的做法很相似。
2. C API


#### 其他
 1. 使用 *LBYL*(look before you leap, 例如前置 if 条件判断) 还是 *EAFP*(easy to ask forgiveness than permission，例如 `try--catch`)? 这里给出了一个[建议](http://stackoverflow.com/questions/5589532/try-catch-or-validation-for-speed/)

 2. 不定长无名参数 `\*args`(元组) 和 不定长有名参数 `\*\*kwargs`（列表）
 3. `python -m SimpleHTTPServer 8088` 文件共享从此 so easy.
 4. `self` 并非关键字，而只是一个约定俗成的变量名


### 参考资料
- [stackoverflow 上一些 python 问题合集 ](http://pyzh.readthedocs.org/en/latest/python-questions-on-stackoverflow.html)
- [python tips/intermediate python](http://book.pythontips.com/en/latest/index.html)

- [关于 python 的面试题](https://github.com/taizilongxu/interview_python)


- [The Best of the Best Practices(BOBP) GUide for Python](https://gist.github.com/sloria/7001839)
