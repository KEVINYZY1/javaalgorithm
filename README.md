javaalgorithm
========

模仿Java标准库的一些API实现的算法库，包括了数据结构，字符串处理（StringBuilder），图（有向图）。原来是用Python实现的，但是Python实现的并没有经过完整的测试，不能够保证完全的正确性。
使用Java实现的集合库都经过完整的测试，实际上，我在实现的过程中基本上用的都是自己实现的数据结构。另外的一些算法和工具来自《程序员面试金典》和《剑指offer》中的习题。

注意：项目需要使用java 8编译，因为用到了lambda和stream类库。

在实现的过程中也发现了Java集合类库中的一些问题。
=========

1.  并没有实现函数式编程语言中三个经典的操作符，map,filter,reduce

2.  toArray方法返回的是Object[]类型，原因是Java不能够通过泛型创建数组，我是通过toVector来实现这个需求的

3. JDK集合类库中所有的迭代器next方法实际上会向下移动一位，而我的集合迭代器中则是在hasNext的时候向下移动一位。

#数据结构

##链表

1. Vector: 可变数组实现，名字参考C++中同名的类，和集合类库中的ArrayList类似。

2. LinkedList:  类似于Java中的LinkedList，双向链表实现，同时也实现了Queue接口，因此可以被用作队列。

##栈 (栈并没有继承任何类或者接口（也是Java集合框架中的一个问题）)

1. LinkedStack：使用双向链表实现的一个栈，对于标准的push,pop和head都是O(1)

2. ExtensiveStack：同时记录了栈中的最大值和最小值，来自于金典

3. MultiStack：表示多个栈的栈，也就是说这个数据结构中可以有任意多的栈，来自金典

##队列(暂时不会实现阻塞队列)

1. PriorityQueue：使用最大堆实现的优先队列

##字典

1. HashMap：使用链接法解决冲突的Map。

2. TreeMap：在插入键的时候会保持键的比较顺序，在遍历的时候会按照比较顺序来。

3. LinkedHashMap：类似于HashMap，但是保持了插入顺序。

##集合

1. HashSet：使用HashMap实现的集合

2. TreeSet：使用红黑树实现的集合

##平衡树

1. AVL树

2. 红黑树

3. B树

4. B+树

5. 前缀树，也叫单词查找树(Trie)，通过在每一个节点上使用HashMap来存储子节点，使得Tries可以支持UTF-8

##图

##其他

1. 跳跃表（SkipList）

2. BitSet

3. StringBuilder

#算法

##排序算法

1. 快速排序，也是默认的排序方法

2. 计数排序

3. 基数排序



