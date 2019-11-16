### think in java中代码合集
```
public class Leaf
{
	int i = 0;
	Leaf increment()
	{
	i++;
	return this;
	}
	void print()
	{
	System.out.println("i="+i);
	}
	public static void main(String[] args)
		{
		Leaf x = new Leaf();
		x.increment().increment().increment().increment().print();
		
		}
} //这个是对当前对象的引用  increment函数中return this;
```

```
class Person
{
	public void eat(Apple apple){
		Apple peeled = apple.getPeeled();
		System.out.println("yummy")
	}
}
class Peeler
{
static Apple peel(Apple apple)
	{
		/**/ //去皮代码
		return apple; //Peeled
	
	}

}
class Apple 
{
Apple getPeeled(){return Peeler.peel(this);}
}

public class passingThis
{
public static void main(String[] args)
{
 new Person().eat(new Apple());

}
}

//Output    
//yummy 

```
代码的特点实在 Apple中的Peeler.peel(this)调用了自身   Peeler.peel可以直接用是因为 peel是静态方法   

```

```

<++>
