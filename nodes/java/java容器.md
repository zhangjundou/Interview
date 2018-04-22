
**List和Set的区别**

1. Set 接口实例存储的是无序的，不重复的数据。List 接口实例存储的是有序的，可以重复的元素。

2. Set检索效率低下，删除和插入效率高，插入和删除不会引起元素位置改变 ，实现类有HashSet，TreeSet。

3. List和数组类似，可以动态增长，根据实际存储的数据的长度自动增长List的长度。查找元素效率高，插入删除效率低，因为会引起其他元素位置改变 ，实现类有ArrayList，LinkedList，Vector，CopyOnWriteArrayList。

 **ArrayList与Vector的区别**

 1.初始容量都为10，但ArrayList默认增长为原来的1.5倍+1，而Vector默认增长为原来的2倍，并且可以设置。

 2.ArrayList速度快但是ArrayList是线程异步的，是不安全的。Vector速度慢，是线程同步的，是安全的。

 **ArrayList与LinkedList的区别**

1.ArrayList是基于动态数组的数据结构，而LinkedList是基于链表的数据结构

2.对于随机访问get和set（查询操作），ArrayList要优于LinkedList，因为LinkedList要移动指针。

3.对于增删操作（add和remove），LinkedList优于ArrayList。

**HashMap与HashTable的区别**

1.HashTable是线程同步的，它使用synchronized来进行同步。也是线程安全的，多线程可以共享同一个HashTable。

2.HashMap不是线程同步的，但它可以使用ConcurrentHashMap，它是HashTable的替代，而且比HashTable扩展性更好。

3.HashMap允许key和value为null，而HashTable不允。

4.HashMap提供对key的Set进行遍历，因此它支持fail-fast机制，而HashTable提供对key的Enumeration进行遍历，不支持fail-fast。

5.在Java1.4中引入了HashMap的子类LinkedHashMap，若需要遍历顺序，可以从HashMap转向LinkedHashMap， 而HashTable的顺序是不可预知的。










