### 一些概念

**敏捷开发宣言**：

1. Individuals and interactions over processes and tools
2. Working software over comprehensive documentation
3. Customer collaboration over contract negotiation
4. Responding to change over following a plan

**归纳**：固定节奏、小步快跑、及时反馈、应对变化、快速交付

**本质**：以快速的增量和迭代方式进行软件开发

### eXtreme Programming

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230520212420326.png" alt="image-20230520212420326" style="zoom:50%;" />

#### Planning

1. 倾听客户陈述，形成一组“用户故事(User Stories)” ，描述其输出、 特性、功能等，用户故事可以分为：所有用户故事，优先级高的用户故事，风险高的用户故事
2. 按照价值或风险排序：客户为每个用户故事指定优先级(Priority) 
3. XP团队评估各个用户故事，为其指定成本(Cost, 开发周数)，若超过3 周，则拆分 
4. 将若干个用户故事指定为下一次发布的增量，确定发布日期
5. 规划整体进度(project velocity)：以怎样的速度开展项目 
6. 客户可以在开发过程中扩展新故事、去除原有故事、改变优先级、拆分等

#### Design

1. 遵循KIS原则(Keep It Simple) 

2. 设计模型：面向对象方法，CRC卡片(Class-Responsibility-Collaborator) 
3. 遇到困难问题，创建“Spike Solutions”(探针原型) 
4. 对设计方案不断重构(Refactoring):
   1.  遵循用户故事的外特性要求 
   2. 改善内部结构 
   3. 消除bug 
   4. 提高效率
   5. 提高易读性

#### Coding 

1. 在编码之前，根据用户故事设计单元测试用例 
2. 结对编程(Pair programming)：两人一起编程，实时讨论、实时评审 
3. 测试驱动的开发(TDD)：先写测试用例，再写代码

##### Pair programming

1. 驾驶员(Driver)：控制键盘输入的人 – 写设计文档，进行编码和单元测试等XP开发流程 

2. 领航员(Navigator)：起到领航、提醒的作用 – 审阅驾驶员的文档、驾驶员对编码等开发流程的执行；考虑单元测试的覆盖程度；是否需要和如何重构；帮助驾驶员解决具体的技术问题

3. 驾驶员和领航员不断轮换角色，不宜连续工作超过一小时；领航员要控制时间

结对编程(Pair programming)的好处：

1. 在开发层次上，结对编程能提供更好的设计质量和代码质量，两人 合作能有更强的解决问题的能力 
2. 对开发人员自身来说，结对工作能带来更多的信心，高质量的产出 能带来更高的满足感 
3. 在心理上, 当有另一个人在你身边和你紧密配合，做同样一件事情 的时候, 你不好意思开小差, 也不好意思糊弄 
4. 在企业管理层次上，结对能更有效地交流，相互学习和传递经验，能更好地应对人员流动；因为一个人的知识已经被其他人共享

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230520213726932.png" alt="image-20230520213726932" style="zoom:33%;" />

​																	       Pair programming

#### Testing

1. 自动化单元测试(Unit test) 
2. 持续集成(Continuous Integration) 
3. 持续进行回归测试(Regression test) 
4. 验收测试(Acceptance test)

### Scrum

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230520214220415.png" alt="image-20230520214220415" style="zoom:50%;" />

#### 基本过程

1. Product Owner组织会议将计划开发的产品分解成若干开发项（Product Backlog），该列表是有优先级的；该表中的开发项在没有被开发前是可以新增 或删除的（引入需求变更）
2. Product Backlog中的一个或几个任务项，是一次Scrum Sprint（Scrum冲 刺）要开发的任务；1个Sprint一般为2-4周；一旦Sprint启动，在开发完成前是 不允许变更需求的
3. 在Sprint开始前，Scrum Master组织Scrum Team会议将Sprint的任务分解 为更小的开发单元（Backlog Tasks）；Scrum Team成员的开发任务单元就是每个 Task
4. Sprint启动后，每天需要召开一次会议（Daily Scrum Meeting），一般不超 过15分钟，每人简短陈述3句话：上次Scrum例会后做了什么？遇到了什么问题？ 下次Scrum例会前计划做什么？（注意：提出的问题在例会上不做任何讨论）
5. Sprint启动后，每天需要召开一次会议（Daily Scrum Meeting），一般不超 过15分钟，每人简短陈述3句话：上次Scrum例会后做了什么？遇到了什么问题？ 下次Scrum例会前计划做什么？（注意：提出的问题在例会上不做任何讨论）
6. 上述Sprint过程循环进行，直到Product Backlog列表空了为止

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230520215246301.png" alt="image-20230520215246301" style="zoom: 50%;" />

##### 每日站会

1. 团队成员站着开会 — 强迫在短时间(15分钟)内高效率讨论问题，保持 注意力集中
2. 强迫每个人向同伴报告进度, 迫使大家把问题摆在明面上，如果每日站 会定于早上开会的话，则每个团队成员应该回答下面问题： 
   1. 我昨天做了什么 
   2. 我今天要做什么 
   3. 我碰到了哪些问题
3. 用简明的图表展现整个项目的进度，这个图最好放在大家工作的环境 中，或者每天传达给各个成员

<img src="C:\Users\xunhi\AppData\Roaming\Typora\typora-user-images\image-20230520215607623.png" alt="image-20230520215607623" style="zoom:50%;" />