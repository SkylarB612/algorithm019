## Class的概念

class被认为是面向对象的“蓝图”，可以拥有自己的属性(characteristics they possess)和方法(actions they perform).

面向对象编程的基本原理举例：

一个class的类别是dog，他不是特指的某一个类型的狗，也不是属于你的狗。而是描述**狗是什么而且它能做什么**。狗通常是拥有*name*和*age*的，这个是它的属性(attributes), 狗也可以*bark*，这是方法（method)。

当我们谈论特定一个类型的狗的时候，意味着在编程中我们就有了一个对象（object）：这个对象就是类别的实例（an object is an instantiation of a class）

*我有一只狗叫Ozzy，属于dog这个类别的（class），它的属性(attributes)就是**name = 'Ozzy'` and `age = '2'**。不同的狗就有不同的属性(attributes)*



#### 如何用Python建立一个类别（Class）

如果用Python定义class，就是：

```python
class Dog:  #class这个关键词，加上定义的名称和分号
```

在class内部，需要用**def**来定义**-- init--**, 这是日后进行实例化对象的初始程序。这个‘**-- init--**是必须存在的’。它有一个参数是self，指的是对象本身。在method内部，pass是关键词使用，因为Python希望在这里输入一些内容

```python
class Dog:
  def __init__(self):
    pass
```

在这个时候，你只有一个几近空白的dog的class，但是没有还没有对象



#### 实例化对象

要实例化对象，需要输入class的名字（Dog），并在后面加上括号

```python
ozzy = Dog()

#打印的话
print(ozzy)

#结果
<__main__.Dog object at 0x111f47278>
```



#### 向class里添加属性

在打印ozzy后，很清楚的发现对象是一只狗，但是你还需要添加属性：name和age

```python
class Dog:
  def __init__(self,name,age):
    self.name = name
    self.age = age
```

现在这个函数self后面有两个参数，name和age，然后将他们分别匹配给self.name和self.age. 现在可以创建具有名字和年龄的ozzy新对象

```python
oozy = Dog('Ozzy',2)

print(ozzy.name)    ---->   Ozzy
pring(ozzy.age)     ---->    2

#进行更加复杂的操作
print(ozzy.name + " is " + str(ozzy.age) + " year(s) old.")
-----> 
Ozzy is 2 year(s) old.
```



#### 在class里定义method

现在有Dog这个class了，同时赋予了name和age，

