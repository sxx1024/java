# 容器
[红黑树](#hhs) 
[List](#lis)
	[linklist](#lin) 
	[arraylist](#arr) 

[set](#set)

<A name="hhs"> 红黑树 </A>  

<A name="lis"> List </A>  


List接口特点:
1. 它是一个元素存取有序的集合。例如,存元素的顺序是11、22、33。那么集合中,元素的存储就是按照11、 22、33的顺序完成的)。
2. 它是一个带有索引的集合,通过索引就可以精确的操作集合中的元素(与数组的索引是一个道理)。
3. 集合中可以有重复的元素,通过元素的equals方法,来比较是否为重复的元素。

当然之前的collecion中的方法他也是可以使用的 add clear remove contain isEmpty size toArray  这个7中方法都可以   

现在就是在这个的基础上又多了几种方法就是我们把指定元素带进去了

public void add(int index,E e) 这个是在指定位置上来插入元素
public E get(int index)得到指定元素的值
public E remove(int index)移除指定元素位置上的值
public E set(int index,E e)设置指定元素上的值
下面就是这个的练习了  

<A name="lin"> linklist </A> 

linklist的底层是链表适合处理 经常插入和删除的数据结构

+ public void addFirst(E e) :将指定元素插入此列表的开头。
+ public void addLast(E e) :将指定元素添加到此列表的结尾。
+ public E getFirst() :返回此列表的第一个元素。
+ public E getLast() :返回此列表的最后一个元素。
+ public E removeFirst() :移除并返回此列表的第一个元素。
+ public E removeLast() :移除并返回此列表的最后一个元素。
+ public boolean isEmpty() :如果列表不包含元素,则返回true。


用链表模拟堆
+ public E pop() :从此列表所表示的堆栈处弹出一个元素。
+ public void push(E e) :将元素推入此列表所表示的堆栈。
							
<A name="arr"> arraylist </A>  
就是之前list的操作学好就可以了  


<A name="set"> set </A> 
在JDK1.8之前,哈希表底层采用数组+链表实现,即使用链表处理冲突,同一hash值的链表都存储在一个链表里。 但是当位于一个桶中的元素较多,即hash值相等的元素较多时,通过key值依次查找的效率较低。而JDK1.8中,哈 希表存储采用数组+链表+红黑树实现,当链表长度超过阈值(8)时,将链表转换为红黑树,这样大大减少了查找
时间。
简单的来说,哈希表是由数组+链表+红黑树(JDK1.8增加了红黑树部分)实现的,如下图所示。
![hashset](https://github.com/shenxixi250/photo/blob/master/javajichu/11_24_001_5.png) 
![hashset+photo](https://github.com/shenxixi250/photo/blob/master/javajichu/11_24_001_1.png) 
由上图我们可以看出来的是其实hashset的底层就是由hashmap来实现的只是相对来说hashset只有值  而hashmap 存在键值对

HashSet实际上是一个HashMap实例，都是一个存放链表的数组。它不保证存储元素的迭代顺序；此类允许使用null元素。HashSet中不允许有重复元素，这是因为HashSet是基于HashMap实现的，HashSet中的元素都存放在HashMap的key上面，而value中的值都是统一的一个固定对象private static final Object PRESENT = new Object();
```
HashSet<String> set = new HashSet<String>();
set.add("语文");
set.add("数学");
set.add("英语");
set.add("历史");
set.add("政治");
set.add("地理");
set.add("生物");
set.add("化学");
for(String name :set)
System.out.println(name);
结果就是
政治
生物
历史
数学
化学
语文
英语
地理
和放进去的时候顺序并不是一致的
```


我们知道HashSet保证元素唯一,可是元素存放进去是没有顺序的,那么我们要保证有序,怎么办呢?
在HashSet下面有一个子类 java.util.LinkedHashSet ,它是链表和哈希表组合的一个数据存储结构。

```

public class Hashset {
        public static void main(String[] args) {
            Set<String> set = new LinkHashSet<String>();
            set.add("语文");
            set.add("数学");
            set.add("英语");
            set.add("历史");
            set.add("政治");
            set.add("地理");
            set.add("生物");
            set.add("化学");
            Iterator<String> it = set.iterator();
            while (it.hasNext()) {
                System.out.println(it.next());
            }
        }

}
```

这样的输出就是一致的了


还有一个小tip就是 可以是实现接口Comparable和Comparator 来让他们按照我们的顺序进行排序


