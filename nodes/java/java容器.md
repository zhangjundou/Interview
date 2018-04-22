
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

**集合的遍历**

**ArrayList的遍历**

``` java
import java.util.ArrayList;
public class ArrayListTest {
	public static void main(String [] args){
		List<String> list = new ArrayList<String>();
		
		
		list.add("Java");
		list.add("计算机网络");
		list.add("数据结构");
		list.add("MySql");
		
		// 方法一： 使用foreach遍历
		System.out.println(".......方法一..........");
		for(String it : list){
			System.out.println(it);
		}
		
		// 方法二： 使用迭代器遍历
		System.out.println(".......方法二..........");
		Iterator<String> cur = list.iterator();
		while(cur.hasNext()){
			System.out.println(cur.next());
		}
		
		//方法三：将集合转化为数组，然后进行for或foreach遍历
		System.out.println(".......方法三..........");
		 String[] strArray=new String[list.size()];
	     list.toArray(strArray);
	     for(int i=0;i<strArray.length;i++) 
	     {
	        System.out.println(strArray[i]);
	     }
		
		
	}

}
```

**Map的遍历**

``` java 
import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;

public class MapTest {
	public static void main(String [] args){
		Map<Integer,String> map = new HashMap<Integer,String>();
		
		map.put(1, "Java");
		map.put(2, "计算机网络");
		map.put(3, "数据结构");
		map.put(4, "MySql");
		
		//方法一：先通过Map.keySet遍历key，再通过key获取value值
		System.out.println(".......方法一..........");
		for(Integer key : map.keySet()){
			System.out.println("key :" +key+ " " +"vaule :"  +map.get(key));
		}
		
		//方法二：通过Map.entrySet使用iterator遍历键值对对象，再通过getKey()和getValue()获取key和value的值
		System.out.println(".......方法一..........");
		Iterator<Map.Entry<Integer,String>> interator = map.entrySet().iterator();
		while(interator.hasNext()){
			Map.Entry<Integer, String> entry = interator.next();
			System.out.println("key :" + entry.getKey() + " " + "vaule :" + entry.getValue());
		}
		
		//方法三：通过Map.entrySet遍历key和value
		System.out.println(".......方法一..........");
		for(Map.Entry<Integer, String> entry : map.entrySet()){
			System.out.println("key :" + entry.getKey() + " " + "vaule :" + entry.getValue());
			
		}
		
	}

}
```

**Set的遍历**

``` java
import java.util.HashSet;
import java.util.Iterator;
import java.util.Set;

public class SetTest {
	public static void main(String [] args){
		Set<String> set = new HashSet();
		
		set.add("Java");
		set.add("计算机网络");
		set.add("数据结构");
		set.add("MySql");
		
		//方法一：迭代遍历
		System.out.println(".......方法一..........");
		for(Iterator<String> iterator = set.iterator() ; iterator.hasNext(); ){
			System.out.println(iterator.next());
		}

		//方法二：foreach循环（没有普通for循环方法）
		System.out.println(".......方法二..........");
		for(String it : set){
			System.out.println(it);
			
		}
		
		
	}

}
```















