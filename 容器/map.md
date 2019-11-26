# map集合

解决生活中一一对应的关系  这种关系叫做映射  
map有如下特点
+ 键唯一 值可以重复
+ 键和值一一映射 一个键对应一个值 
+ 

map接口中的常用方法 
```
public V put(K key, V value) : 把指定的键与指定的值添加到Map集合中。
public V remove(Object key) : 把指定的键 所对应的键值对元素 在Map集合中删除,返回被删除元素的
值。
public V get(Object key) 根据指定的键,在Map集合中获取对应的值。
public Set<K> keySet() : 获取Map集合中所有的键,存储到Set集合中。
public Set<Map.Entry<K,V>> entrySet() : 获取到Map集合中所有的键值对对象的集合(Set集合)。

```
map实现遍历
```java
public class MapDemo01 {
public static void main(String[] args) {
//创建Map集合对象
HashMap<String, String> map = new HashMap<String,String>();
//添加元素到集合
map.put("胡歌", "霍建华");
map.put("郭德纲", "于谦");
map.put("薛之谦", "大张伟");
Set<String> keys = map.keySet();
// 遍历键集 得到 每一个键
for (String key : keys) {
//key
就是键
//获取对应值
String value = map.get(key);
System.out.println(key+"的CP是:"+value);
}
}
}
```



Entry 键值对对象
既然Entry表示了一对键和值,那么也同样提供了获取对应键和对应值得方法:
```
public K getKey() :获取Entry对象中的键。
public V getValue() :获取Entry对象中的值。
在Map集合中也提供了获取所有Entry对象的方法:
public Set<Map.Entry<K,V>> entrySet() : 获取到Map集合中所有的键值对对象的集合(Set集合)。
```
hashmap实现存储自定义的键值对
```
首先是学生类的编写
class Student
{
	public name;
	public age;
	public boolean equal(O o)
	{
		if(this==o)
			return true;
		if(o==null||getClass()!=o.getClass())
			return false;
		Student student = (student) o;
		return age==student.age&&Object.equals(name,student.name);
		
	}
	public int hashCode(){
		return Objects.hash(name,age);
	}
}
```

```
public class HashMapTest{
	public static void main(String[] args)
		Map<Student,String>map = new HashMap<Student,String>();
		map.put(new Student("list",21),"上海");
		map.put(new Student("shenxixi",21),"海上");
		map.put(new Student("lillllt",21),"上海tan");

		Set<Student>keySet = map.keySet();
		for(Student key:keySet)
		{
			Stringvalue = map.get(key);
			System.out.println(key.toString()+",,,,,"+value);
		}
}
```

当给 HashMap中存放自定义对象时,如果自定义对象作为key存在,这时要保证对象唯一,必须复写对象的
hashCode和equals方法(如果忘记,请回顾HashSet存放自定义对象)。
如果要保证 map中存放的key和取出的顺序一致,可以使用 java.util.LinkedHashMap 集合来存放。
