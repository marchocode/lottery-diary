# :one: Chapter 1 准备工作 工欲善其事必先利其器



## :question: 需要了解的内容



### 各种晕头转向的POJO

> 参考内容：https://blog.csdn.net/chenchunlin526/article/details/69939337



1. PO (Persistent Object)
   1. 对象和关系的映射
   2. PO的属性和数据库表字段对应
   3. 需要实现序列化接口
2. DTO (Data Transfer Object)
   1. 将PO的部分字段抽取出来，就成为了 `DTO`
   2. 例如一个100个字段的PO,客户端只需要显示10个字段，这个就是 `DTO`
   3. `DTO` 可能来源于多个表。
   4. 这10个字段到达客户端后，如果用于页面显示，此时身份就转换为 `VO`
3. VO (View Object)、（Value Object）
   1. Value Object 值对象，也是业务对象，存活在业务层
   2. View Object 视图对象，主要对应与页面。
4. BO (Business Object)
   1. 业务对象，封装逻辑的对象。
   2. 例如一个简历对象，包含一个教育经历（PO）,工作经历（PO）
5. DO (Data Object)
   1. DAO 层向外传输对象，应该和PO 是一致的。

> 参考阿里巴巴 JAVA开发手册：https://github.com/alibaba/p3c/blob/master/Java%E5%BC%80%E5%8F%91%E6%89%8B%E5%86%8C%EF%BC%88%E5%B5%A9%E5%B1%B1%E7%89%88%EF%BC%89.pdf

![](https://file.chaobei.xyz/202201071204196.png_imagess)





### 传统 MVC

> https://zh.wikipedia.org/wiki/MVC



- Model 模型
  - 实体Bean来实现
  - Model 负责资料访问，较现代的 Framework 都会建议使用独立的资料对象 (DTO, POCO, POJO 等) 来替代弱类型的集合对象
- View 视图
  - JSP担任,负责显示资料。
- Controller 控制器
  - 例如 Spring 的 `DispatcherServlet`



> MVC的一般流程是这样的：**View（界面）触发事件--》Controller（业务）处理了业务，然后触发了数据更新--》不知道谁更新了Model的数据--》Model（带着数据）回到了View--》View更新数据**
>
> https://www.zhihu.com/question/20148405/answer/23813147



参考了一些知乎的问答和Wiki上面的解释，自我的理解应该是这样的：

![](https://file.chaobei.xyz/202201071022603.png_imagess)

1. 用户在页面上出发 `动作`
2. Controller(Servlet) 接收到动作
3. 按照动作去调用不同的Model，组合要返回的页面View和数据。
4. 浏览器按照返回的页面，渲染展示给用户。



### Controller+Service+Dao ?

个人的理解应该是：随着前后端的分离，在页面触发一个动作的时候，不需要页面全部都更新，只需要更新部分，然后就衍生出 `JSON` 的前后端交互方式。

![](https://file.chaobei.xyz/20220110221303.png_imagess)

:question: 这个是一种全新的架构模式，还是说是一种 `MVC` 的改进版呢？



### 领域驱动 DDD

> https://bugstack.cn/md/develop/framework/ddd/2019-10-15-DDD%E4%B8%93%E9%A2%98%E6%A1%88%E4%BE%8B%E4%B8%80%E3%80%8A%E5%88%9D%E8%AF%86%E9%A2%86%E5%9F%9F%E9%A9%B1%E5%8A%A8%E8%AE%BE%E8%AE%A1DDD%E8%90%BD%E5%9C%B0%E3%80%8B.html



![](https://file.chaobei.xyz/20220110230252.png_imagess)

> 对于领域驱动型模型的理解：https://github.com/maruichao52/ddd-spring-demo



### :pushpin: 代码提交规范









### :book: 作业提交







## :arrow_down: 下一步计划

