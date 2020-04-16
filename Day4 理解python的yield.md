stackoverflow高赞回答之：What does the “yield” keyword do?

地址：https://stackoverflow.com/questions/231767/what-does-the-yield-keyword-do

---

想要理解yield，就必须要知道什么是生成器，想要理解什么是生成器，就必须理解什么是迭代器。

### 可迭代对象（Iterables）

逐一的阅读元素就叫做迭代（Iteration）

``` python
>>> mylist = [1, 2, 3]
>>> for i in mylist:
...    print(i)
1
2
3
```

所有你可以用for in的都是迭代器，list,strings...

这些可迭代的方法很方便，因为您可以随意读取它们，但是您将所有值都存储在内存中，当拥有很多值时，这并不总是想要的。

### 生成器（Generators）

生成器是迭代器，一种可迭代的对象，您只能迭代一次。生成器未将所有值存储在内存中，而是即时生成值：

``` python
>>> mygenerator = (x*x for x in range(3))
>>> for i in mygenerator:
...    print(i)
0
1
```

除了使用（）代替[]之外，其余部分完全相同。但是，您不能第二次在mygenerator中执行i，因为生成器只能使用一次：它们先计算0，然后忘记它，然后计算1，最后一次计算4。

### yield

yield是一个像return一样使用的关键字，只是函数将返回一个生成器。

``` python
>>> def createGenerator():
...    mylist = range(3)
...    for i in mylist:
...        yield i*i
...
>>> mygenerator = createGenerator() # create a generator
>>> print(mygenerator) # mygenerator is an object!
<generator object createGenerator at 0xb7555c34>
>>> for i in mygenerator:
...     print(i)
0
1
4
```

这是一个无用的示例，但是当您知道函数将返回大量的值（只需要读取一次）时，它就很方便。

要掌握yield，您必须了解当调用函数时，在函数主体中编写的代码不会运行。该函数仅返回生成器对象，这有点棘手:-)

然后，您的代码将从每次停止使用生成器的地方继续。

### 迭代的内部机制

迭代是一个包含可迭代对象（实现`__iter __（）`方法）和迭代器（实现`__next __（）`方法）的过程。可迭代对象是可以从中获取迭代器的任何对象。迭代器是使您可以迭代可迭代对象的对象。

Iteration is a process implying iterables (implementing the `__iter__()` method) and iterators (implementing the `__next__()` method). Iterables are any objects you can get an iterator from. Iterators are objects that let you iterate on iterables.

名词解释：

迭代： iteration
可迭代对象：iterables
迭代器：iterators
迭代：interate

