### 推导式

```python
mylist = [i**2 for i in range(1, 11) if i > 5]
```

### 字符串的连接和拆分

```python
'.'.join(mylist)
mystrinng.split('.')[1:3]
```

### 格式化字符串

```python
str.format(*args, **kwargs)
f-string # python3.6引入，性能更好，易读性好
```

### 使用collections扩展内置数据类型

```python
# namedtuple 带命名的元祖
# deque 双向队列
# Counter 计数器
```

### 函数的可变长参数

```python
def func(*args, **kwargs):
  pass

# kwargs：获取关键字参数
# args：获取其他参数
```

### lambda表达式

```python
k = lambdba x:x+1
print(k(1))
```

### 高阶函数

```python
# 高阶：参数是函数，返回值是函数
# reduce被放在functools包中
# 推导式和生成器表达式可以替代map和filter函数
```

### 生成器

```python
# 在函数中使用yield关键字，可以实现生成器
# 生成器可以让函数返回可迭代对象
# yield和return不同，return返回后，函数状态终止，yield保存函数的执行状态，返回后，函数回到之前那保存的状态继续执行
# 函数被yield会暂停，局部变量也会保存
# 迭代器终止时，会抛出StopIteration异常
```

### 装饰器

```python
# 装饰器函数的参数是被装饰函数
# 装饰器函数处理被装饰函数，处理完成返回装饰函数，或者替换为另一个函数
# 装饰器不用入侵函数内部
# 装饰器强调定义态，而非运行态
```

### 魔术方法

```python
# __call__()允许类的实例成为可调用对象
# __str__被str()调用时的行为
# __getitem__使用[key]调用时的行为
# __iter__被迭代时的行为
```

### 属性描述符property

```python
# property类需要实现__get__,__set__,__init__方法
```

### 抽象基类

```python
# 抽象基类（ABC）
# 抽象基类提供了逻辑和实现解耦的能力
# 父类可以定义，不用实现
# 子类必须实现，否则报错
```

### ORM

```python
# ORM让python不用写原生SQL语句
```

### 运行性能

```python
# python代码是由python虚拟机执行的
# python虚拟机执行的是字节码
# python代码运行前会被编译为字节码
# dis模块可以对python代码进行生成字节码操作
```

### 异常捕获

```python
# 所有内置的非系统退出的一场都派生自Exception类
```

### 上下文管理器

```python
# with语句
# with实现了上下文管理协议，实现了__enter__,__exit
# 支持上下文管理协议对象，实现上下文管理器
```

### 代码风格

```python
# pylint
```

### 单例模式

```python
# 单例模式是设计模式的一种
# 单例模式确保类只有一个对象被创建
# 提供一个全局访问该对象的方式
# 控制共享资源的并行访问
```