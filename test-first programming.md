##### Test-first编程的思想

让程序尽早失败，从而尽早地发现bug，以节省调试时间

##### Test-first编程的过程（以单元测试为例）：

1.  先写spec 
2.  再写符合spec的测试用例 
3.  写代码、执行测试、有问题再改、再执行测试用例，直到通过它

##### Test-first 编程的好处：

1. 可以让你更早的发现bug
2. 可以帮助你更加深入的理解spec
3. 让你写代码更加自信

##### Test Case

>  测试用例 = 输入 + 执行条件 + 期望结果

设计Test Case的一般方法：将输入按等价类划分，每个等价类代表着对输入约束加以满足/违反的有效 /无效数据的集合，在使用一种策略来根据等价类来设计测试用例

策略：

1. 笛卡尔积，多个划分维度上的多个取值，要组合起来，每个组合都要有一个用例
2. 覆盖每个取值，每个维度的每个取值至少被1个测试用例覆 盖一次即可

例如：

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230517223304477.png" alt="image-20230517223304477" style="zoom:50%;" />

还有一点值得注意，一般情况下我们都会将程序的边界情况加入等价类中。因为很多程序就是在边界情况最容易出错。

##### 使用JUnit来编写单元测试

教程：https://www.vogella.com/tutorials/JUnit/article.html#junit_testorganization

比较常用的：

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230517224014608.png" alt="image-20230517224014608" style="zoom:50%;" />

##### 黑盒测试和白盒测试

黑盒测试：用于检查代码的功能，不关心内部实现细节，主要用于检查程序是否符合spec。测试用例完全由spec导出，上面讲的都是黑盒测试

白盒测试：要更据程序·具体实现细节来写测试用例，例如一个程序可能跟据输入规模选择了不同的算法来实现，这是就要更具不同的规模来设计测试用例

##### 回归测试

1. 一旦程序被修改，重新执行之前的所有测试

2. 一旦发现bug，要马上写一个可重现该bug的测试用例，并将其加入测试库

##### Test Strategy

相当于测试的说明书，用于记录你是如何测试的。写给未来的你和你的同事。

例如：

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230517225043936.png" alt="image-20230517225043936" style="zoom:50%;" />