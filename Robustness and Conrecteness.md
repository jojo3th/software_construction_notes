健壮性：系统在不正常输入或不正常外部环境下仍能够表现正常的程度

正确性：永不给用户错误的结果

健壮性：尽可能保持软件运行而不是总是退出	

正确性倾向于直接报错(error)，健壮性则倾向于容错(fault-tolerance)

对外的接口，倾向于健壮；对内的实现，倾向于正确

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230525211502680.png" alt="image-20230525211502680" style="zoom:50%;" />

内部错误：程序员通常无能为力，一旦发生，想办法让程序优雅的结束

异常：你自己程序导致的问题，可以捕获、可以处理

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230525221300648.png" alt="image-20230525221300648" style="zoom:50%;" />

程序之外的事，不受你控制，不要乱断言

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230525221510332.png" alt="image-20230525221510332" style="zoom:50%;" />

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230525221718929.png" alt="image-20230525221718929" style="zoom:50%;" />

断言可用于private的方法或者用于检查post-condition