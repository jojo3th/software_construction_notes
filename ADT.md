<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230521224629521.png" alt="image-20230521224629521"  />

Representation Independence

测试creators, producers, and mutators：调用observers来观察这些 operations的结果是否满足spec；

测试observers：调用creators, producers, and mutators等方法产生或 改变对象，来看结果是否正确。

除非迫不得已，否则不要把希望寄托于客户端上，ADT有责任保证自 己的invariants，并避免“表示泄露”。

最好的办法就是使 用immutable的类型，彻底避免表示泄露

AF(abstract function)：ADT中的属性表示的一个抽象物体，通俗来说就是这个ADT是用来干什么的

RI(rep invariant)：所有表示值的一个子集，包含了所有合法的表示值。也可以说RI就是ADT中的属性应该遵循的规范

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230521234306518.png" alt="image-20230521234306518" style="zoom:50%;" />

例子：分数有最简分数和不是最简分数，但不影响结果

AF，RI，safety from exposure均以注释形式写出，为了不暴露给客户端 