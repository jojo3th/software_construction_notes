### Equality of Immutable Types

1. AF映射到同样的结果，则等价

2. 站在外部观察者角度：对两个对象调用任何相同的操作，都会得到相同的结果，则认为这两个对象是等价的。 反之亦然！（行为等价性）

### Equality of Mutable Types

      1. 观察等价性：在不改变状态的情况下，两个mutable对象是否看起来一致（When they cannot be distinguished by observation that doesn’t change the state of the objects, i.e., by calling only observer, producer, and creator methods. This is often strictly called observational equality）
      2. 行为等价性：调用对象的任何方法都展示出一致的结果（When they cannot be distinguished by any observation, even state changes.This interpretation allows calling any methods on the two objects, including mutators. This is called behavioral equality）

 **对可变类型来说，往往倾向于实现严格的观察等价性**

***but*这样可能会有bug**

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230523213335143.png" alt="image-20230523213335143" style="zoom:50%;" />

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230523213632204.png" alt="image-20230523213632204" style="zoom:50%;" />

***简单的来说就是HashSet用的是hash值来找元素，list变了之后它的hash值也变了，但是list已经在HashSet中了，它的位置不会再变了，当set再调用contains时，set还是按原来的HashCode来找，所以找不到***

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230523213109461.png" alt="image-20230523213109461" style="zoom:50%;" />

### == vs equals

== 引用等价性

equals 对象等价性

在自定义ADT时，需要重写Object的equals()

#### override equals方法

```java
@Override
public boolean equals(Object o) {
    if (this == o) return true;
    if (!(o instanceof 原类)) return false;
    将o强转为原类;
    自己的判断;
}
```

```java
public class Name {
private final String first, last;
public Name(String first, String last) {
    if (first == null || last == null)
    throw new NullPointerException();
    this.first = first;
    this.last = last;
}
public boolean equals(Name o) {
	return first.equals(o.first) && last.equals(o.last);
}
public int hashCode() {
	return 31 * first.hashCode() + last.hashCode();
}
public static void main(String[] args) {
    Set<Name> s = new HashSet<>();
    s.add(new Name("Mickey", "Mouse"));
    System.out.println(s.contains(new Name("Mickey", "Mouse")));
	}
}
```

结果：false

原因：contains方法底层，用的是Object来接收s中的变量，所以第18行中的contains中在比较的时候想调用equals方法，但是由于变量的编译类型为Object，所以，由动态绑定原理，jvm会先在Name类中找equals方法(是Object中的equals方法的重写)，没找到，因为Name中的equals方法是overload，所以jvm会调用Name的父类equals方法，所以是false

Using instanceof is dynamic type checking，It should be disallowed anywhere except for implementing equals . 

equals函数的contract：

1. equals必须定义一个等价关系：自反、传递、对称
2. 除非对象被修改了，否则调用多次equals应同样的结果
3. for a non-null reference x , x.equals(null) should return false
4. “相等”的对象，其hashCode()的结果必须一致

#### override hashcode方法

要保证“相等”的对象，其hashCode()的结果必须一致



### 总结

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230523214308371.png" alt="image-20230523214308371" style="zoom:50%;" />

Unchecked Exception Classes：在编程和编译的时候，IDE与编 译器均不会给出任何错误提示

Checked Exception Classes：在编译阶段会有错误提示

不应该throws Unchecked Exception Classes，应为这是程序员可以处理的

子类型方法可以抛出更具体的异 常，也可以不抛出任何异常

***instanceOf***：它是dynamic-checking,所以能不用就不用，尽量使用多态来取代它
