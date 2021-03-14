# 四种工作方式

`micro_route` 拥有四种工作方式,分别是:

| 阻塞\线程 |     单线程      |     多线程      |
| :-------: | :-------------: | :-------------: |
|   阻塞    |  单线程 - 阻塞  |  多线程 - 阻塞  |
|  非阻塞   | 单线程 - 非阻塞 | 多线程 - 非阻塞 |



## 阻塞

​	阻塞选项用来设定当执行 `app.run()` 时是否卡住主线程不返回, 如果您设置为阻塞, 那么您在 `app.run ()` 之后的代码可能一直无法运行, 这可以给 `micro_route` 提供一个稳定的工作环境.

​	如果您设定为非阻塞, 即当您调用 `app.run ()` 之后, 程序将马上返回, 以便您在 `app.run ()` 之后的代码得以运行, 如果您设置为非阻塞, 当浏览器发起 `socket` 请求时, 您目前正在处理的程序可能会被中断.



## 线程

​	在有些开发版上, `micropython` 并没有对其进行 `多线程` 支持, 这也就意味着您无法使用多线程.

​	如果您的开发版支持多线程, 您可以考虑开启多线程以加速多多请求访问的速度.



如何设定工作方式? 详见 [run ()函数](./library/micro_route.html/#func-run-)