##  Stack

- 先入后出；添加、删除为O(1)

```python
# Python program to 
# demonstrate stack implementation
# using collections.deque
 
 
from collections import deque
 
stack = deque()
 
# append() function to push
# element in the stack
stack.append('a')
stack.append('b')
stack.append('c')
 
print('Initial stack:')
print(stack)
 
# pop() fucntion to pop
# element from stack in 
# LIFO order
print('\nElements poped from stack:')
print(stack.pop())
print(stack.pop())
print(stack.pop())
 
print('\nStack after elements are poped:')
print(stack)
 
# uncommenting print(stack.pop())  
# will cause an IndexError 
# as the stack is now empty
```

- stack如同有一摞书，你想要中间的那一本，你就必须先拿走上它上面的那本书。同时如果你要摞书，最上面一本就是你最后放在上面的

- stack用于：

  1. To backtrack to the previous task/state, for example, in recursive code

  2. To store a partially completed task, for example, when you are     exploring two different paths on a Graph from a point while figuring out the smallest path to the target

- Stack 的实施：

  | **Function**  |             **What dose it do？**              | **Time Complexity** |
  | :-----------: | :--------------------------------------------: | ------------------- |
  | push(element) |         Inserts an element at the top          | O(1)                |
  |     pop()     | Removes an element from the top and returns it | O(1)                |
  |   IsEmpty()   |   Returns a boolean 1 if the stack is empty    | O(1)                |
  |     top()     |    Returns the element added most recently     | O(1)                |
  |    size()     |         returns the size of the slack          | O(1)                |

- 建立一个Stack的类，并创建一个object

  ```PYTHON
  class MyStack:
    def __init__(self):
      self.stack_list = []
  
  stack = Mystack()
  ```

- 公式的运用

  ```python
  class MyStack:
    def __init__(self):
      self.stack_list = []
    
    def is_empty(self):
      return self.size() == 0    
    
    def top(self):
      if self.is_empty():
        return None
      return self.stack_list[-1]
    
    def size(self):
      return len(sel.stack_list)
  
  stack = Mystack()
  print("is_empyt():" + str(stack.is_empty()))
  print("top():" + str(stack.top()))
  print("size():" + str(stack.size()))
  
  _______________________________________________
  
  is_empyt(): True     #返回的是boolean
  top(): None
  size():0
  
  ----------------------------
  for i in range(5): #range(5):0-4
    
    stack.push(i)    #创造新的节点放在栈顶，增加值
  
  print("top():" + str(stack.top()))
  
  for x in range(5):
    print(stack.pop()) #删除栈顶的值
  
  print("is_empyt():" + str(stack.is_empty()))      #如果长度是0，返回的是True
  
  _______________________________________________
  
  top():4
  
    4
    3
    2
    1
    0
    
   is_empty():True
  
    
  ```

  



## Queue

- 先入先出；添加、删除为O(1)

- Queue就是排队等待从取票的人。 如果有新人来，他将从后面加入队伍，而站在前排的人将是第一个拿到票并因此离开队伍的人。

- 用处：

  1. We want to prioritize something over another
  2. A resource is shared between multiple devices

- |   **Function**   |              **What dose it do？**               | **Time Complexity** |
  | :--------------: | :----------------------------------------------: | ------------------- |
  | enqueue(element) |     inserts element at the end of the queue      | O(1)                |
  |    dequeue()     |  removes an element from the start of the queue  | O(n)                |
  |    IsEmpty()     |           checks if the queue is empty           | O(1)                |
  |     front()      |      returns the first element of the queue      | O(1)                |
  |      back()      | returns the last element inserted into the queue | O(1)                |
  |      size()      |          returns the size of the queue           | O(1)                |

- Deque：Double-End queue 双端队列  -----*两端可以进出* ：The double-ended queue acts as a queue from both the back and the front. It is a **flexible data** structure that provides `enqueue` and `dequeue` functionality on both ends in *O(1)*. Hence, it can act as a normal linear queue if needed. Python has a built-in `deque` class that can be imported from the `collections` module. The class contains several useful methods such as `rotate`. 

- Prioroty Queue：all elements have a priority associated with them and are sorted such that the most prioritized object appears at the front and the least prioritized object appears at the end of the queue. These queues are widely used in most operating systems to determine which programs should be given more priority.（所有的元素都有与其相关联的优先级，并进行排序。优先级最高的在最前面，最低的在队尾。这个主要用于在众多操作系统中以确定那个系统更高的优先级）

- 建立一个queue的class

  ```python
  class MyQueue:
      def __init__(self):
          self.queue_list = []
  
  
  queue = MyQueue()
  
  ```

- 增加 辅助函数（Helper Function），在添加 enqueue(element)和dequeue()的公式之前，需要增加一些辅助函数来使得code更加简洁和便于理解，辅助函数有：

  `is_empty()`

  `front()`

  `back()`

  `size()`

```PYTHON
class MyQueue:
  def __init__(self):
    self.queue_list = []
    
  def is_empty(self):
    return len(self.queue.list) ==0
  
  def front(self):
    if self.is_empty():
      return None
    return self.queue_list[0]
  
  def back(self):
    if self.is_empty():
      return None
    return self.queue_list[-1]
  
  def size(self):
    return len(self.queue_list)

queue = MyQueue()
print("is_empty(): " + str(queue.is_empty()))
print("front(): " + str(queue.front()))
print("back(): " + str(queue.back()))
print("size(): " + str(queue.size()))

--------------------------------------
is_empty(): True  
front(): None
back(): None
size(): 0
  #isempty 返回Trun， front返回None，说明辅助函数正常运转。列表最后一个元素在最后，第一个元素（位置为0）在最前面
  
```

```python
class MyQueue:
    def __init__(self):
        self.queue_list = []

    def is_empty(self):
        return self.size() == 0

    def front(self):
        if self.is_empty():
            return None
        return self.queue_list[0]

    def back(self):
        if self.is_empty():
            return None
        return self.queue_list[-1]

    def size(self):
        return len(self.queue_list)

    def enqueue(self, value):
        self.queue_list.append(value)

    def dequeue(self):
        if self.is_empty():
            return None
        front = self.front()
        self.queue_list.remove(self.front())
        return front


queue = MyQueue()

print("queue.enqueue(2);")
queue.enqueue(2)
print("queue.enqueue(4);")
queue.enqueue(4)
print("queue.enqueue(6);")
queue.enqueue(6)
print("queue.enqueue(8);")
queue.enqueue(8)
print("queue.enqueue(10);")
queue.enqueue(10)

print("Dequeue(): " + str(queue.dequeue()))
print("Dequeue(): " + str(queue.dequeue()))

print("front(): " + str(queue.front()))
print("back(): " + str(queue.back()))

queue.enqueue(12)
queue.enqueue(14)

while queue.is_empty() is False:
    print("Dequeue(): " + str(queue.dequeue()))

 ---------------------------------------------
queue.enqueue(2);
queue.enqueue(4);
queue.enqueue(6);
queue.enqueue(8);
queue.enqueue(10);
Dequeue(): 2
Dequeue(): 4
front(): 6
back(): 10
Dequeue(): 6
Dequeue(): 8
Dequeue(): 10
Dequeue(): 12
Dequeue(): 14
is_empty(): True
```



zip -r COVID19_Tweets_Dataset.zip ./*