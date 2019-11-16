[Arraylist](#arr) 
[Linklist](#lin) 
<A name="arr"> Arraylist </A>  

ArrayList 
1. 在import java.util.ArrayList中
2. List是它的父类  List<String> list = new ArrayList<String>();
#### 一些常见的方法

| 返回值类型  | 函数格式                                                 | 举例                           |
|-------------|----------------------------------------------------------|--------------------------------|
| boolean     | add(E e) 添加元素到list末尾                              | 如list.add(2)                  |
| void        | add(int index, E e) 在指定位置添加元素                   | list.add(2,"你好")             |
| void        | clear()清除list中的元素                                  | list.clear()                   |
| boolean     | contains(Objiect o)  检查list中是否包含元素o             | list.contains("nihao")         |
| E           | get(int index)通过下标获取元素                           | list.get(1)                    |
| boolean     | isEmpty() 判断是否为空                                   | list.isEmpty()                 |
| Iterator<E> | iterator() iterator轻量级遍历list的工具                  | Iterator ite = list.iterator() |
| E           | remove(int index)   移除一个位置上的元素                 | list.remove(1)                 |
| boolean     | remove(Object o) 移除元素o                               | list.remove("描红")            |
| int         | size()返回长度                                           | list.size()                    |
| E           | set(int index,E e) 修改指定位置上的元素,返回被修改的元素 | list.set(1,"年后,")            |
| <++>        | <++>                                                     | <++>                           |

[源码实现](https://www.cnblogs.com/cxuanBlog/p/10949552.html) 
有时间撸一遍哈
#### 如何遍历
		第一种方法就是使用增强的For-Each来进行遍历
		```
		for (String str : list)
			{
				System.out.println(str)
			}
		```
		第二种方法 ArrayList中的toArray方法转成数组然后使用传统的for循环
		```
		String[] strArray = new String[list.size()];
		list.toArray(strArray);
		for(int i=0;i<strArray.length;i++)
		 {
			System.out.println(strArray[i]);
		 }
		```
		第三种方法 使用迭代器iterator  
		```
		Iterator<String> ite = list.iterator();
		while(ite.hasNext())
		{
		 System.out.println(ite.next());
		}
		```

		
<A name="lin"> Linklist </A>  
[用到的时候在学网站](https://blog.csdn.net/i_lovefish/article/details/8042883) 
