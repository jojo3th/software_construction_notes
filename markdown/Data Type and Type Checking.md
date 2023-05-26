### Type Checking
#### static checking：编译时检查

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230521204238546.png" alt="image-20230521204238546" style="zoom:50%;" />

#### dynamic checking：运行时检查

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230521204259347.png" alt="image-20230521204259347" style="zoom:50%;" />

总结：

1. 静态检查：关于“类型”的检查，不考虑值 

2. 动态检查：关于“值”的检查

### Data Type

**immutable**

不变对象：一旦被创建，始终指向同一个值/引用

**mutable**

可变对象：拥有方法可以修改自己的值/引用

例如：

```java
String str = "a";
str = str + "b";
String otherStr = str;
otherStr += "c";
StringBuilder sb = new StringBuilder("a");
sb.append("b");
StringBuilder otherSb = sb;
otherSb.append("c");
```

snapshot diagram

![image-20230521205115801](C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230521205115801.png)

尽量少使用可变数据类型

### Snapshot Diagram

基本类型：

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230521205400853.png" alt="image-20230521205400853" style="zoom:33%;" />

对象类型：

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230521205423630.png" alt="image-20230521205423630" style="zoom:33%;" />

不可变数据对象用双椭圆：

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230521205508758.png" alt="image-20230521205508758" style="zoom:33%;" />

不可变的引用用双箭头：

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230521205614774.png" alt="image-20230521205614774" style="zoom:33%;" />

### 迭代器错误

原因：iterator是一个mutable的类，它里面有mutator

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230522235044429.png" alt="image-20230522235044429" style="zoom:50%;" />

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230522235133253.png" alt="image-20230522235133253" style="zoom:50%;" />

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230522235201134.png" alt="image-20230522235201134" style="zoom:50%;" />

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230522235220133.png" alt="image-20230522235220133" style="zoom:50%;" />

ArrayList就是一个动态数组
