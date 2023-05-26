### LSP中关于subtyping

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230523234804090.png" alt="image-20230523234804090" style="zoom:50%;" />

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230523235000136.png" alt="image-20230523235000136" style="zoom:50%;" />

> **covariance 父类型--->子类型，变得越来越具体或不变**
>
> contra-variance **父类型--->子类型，变得越来越具体，或不变**

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230523235513245.png" alt="image-20230523235513245" style="zoom:50%;" />

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230523235530987.png" alt="image-20230523235530987" style="zoom:50%;" />

***Arrays are covariant***

***Generics are not covariant***

### Wildcards --> ?

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230524000430599.png" alt="image-20230524000430599" style="zoom:50%;" />

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230524000607847.png" alt="image-20230524000607847" style="zoom:50%;" />

### delegation

**委派模式：通过运行时动态绑定，实现对 其他类中代码的动态复用**

一个类不需要继承另一个类的全部方法，通过委托机制调用部分方法

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230524125228584.png" alt="image-20230524125228584" style="zoom:50%;" />

#### **Dependency: 临时性的delegation**

通过传参的方式委托

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230524213230614.png" alt="image-20230524213230614" style="zoom:50%;" />

#### **Association: 永久性的delegation**

通过在类中添加属性

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230524213255212.png" alt="image-20230524213255212" style="zoom:50%;" />

##### **Composition: 更强的association，但难以变化**

Composition是Association的一种特殊类型，其中Delegation关系通过类内部field初始化建立起来，无法修改。已经给你指定运行类型了

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230524213425432.png" alt="image-20230524213425432" style="zoom:50%;" />

##### **Aggregation: 更弱的association，可动态变化**

Aggregation也是Association的一种特殊类型，其中Delegation关系通过客 户端调用构造函数或专门方法建立起来。可以通过方法改变属性的运行类型
