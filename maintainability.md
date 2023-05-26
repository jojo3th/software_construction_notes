### Some common-used maintainability metrics

1. Cyclomatic Complexity 圈复杂度
2. Lines of Code 代码行数
3. Maintainability Index (MI) 可维护性指数。A high value means better maintainability
4. Depth of Inheritance 继承的层次数
5. Class Coupling 类之间的耦合度
6. Unit test coverage单元测试的覆盖度

### 模块化编程

#### coupling

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230524232428614.png" alt="image-20230524232428614" style="zoom: 50%;" />

#### cohesion

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230524232546391.png" alt="image-20230524232546391" style="zoom: 67%;" />

###  OO Design Principles: SOLID

#### SRP

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230524232847573.png" alt="image-20230524232847573" style="zoom:50%;" />

***例子：***

![image-20230524233258538](C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230524233258538.png)

***总结：***一个人只负责一件事



#### OCP

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230524233041562.png" alt="image-20230524233041562" style="zoom:50%;" />

***例子：***

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230524233411502.png" alt="image-20230524233411502" style="zoom:50%;" />

***总结：***利用继承进行模块的扩展

#### LSP

见reuse

#### ISP

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230524233936029.png" alt="image-20230524233936029" style="zoom:50%;" />

***例子：***

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230524234058226.png" alt="image-20230524234058226" style="zoom:50%;" />

***总结：***感觉像接口的SRP，接口不应过大，应该将fat接口按照功能分成几个小的接口

#### DIP

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230524234308854.png" alt="image-20230524234308854" style="zoom:50%;" />

***例子：***

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230524234925956.png" alt="image-20230524234925956" style="zoom:50%;" />

**总结：**感觉还是要更加抽象，分工明确，在设置参数的时候尽量用interface等高抽象的来做编译类型，这样的话自由度更大，让用户有更多的选择权力

### 正则表达式

正则语法：简化之后 可以表达为一个产生式而不包含任何非终止节点

https://www.runoob.com/java/java-regular-expressions.html