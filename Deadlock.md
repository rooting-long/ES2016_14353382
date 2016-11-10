#1.死锁截图
##如图所示，死锁停在了第467次
![Deadlock](http://h.hiphotos.baidu.com/image/pic/item/b17eca8065380cd756490edda844ad34598281af.jpg)


#2.产生死锁的4个必要条件
产生死锁的四个必要条件：
（1） 互斥条件：一个资源每次只能被一个进程使用。
（2） 请求与保持条件：一个进程因请求资源而阻塞时，对已获得的资源保持不放。
（3） 不剥夺条件:进程已获得的资源，在末使用完之前，不能强行剥夺。
（4） 循环等待条件:若干进程之间形成一种头尾相接的循环等待资源关系。
这四个条件是死锁的必要条件，只要系统发生死锁，这些条件必然成立，而只要上述条件之
一不满足，就不会发生死锁。

#3.上述程序产生死锁的解释
![img1](http://f.hiphotos.baidu.com/image/pic/item/21a4462309f790520df6ed0e05f3d7ca7bcbd511.jpg)
当a.methodA(b)和 run()中的b.method(a)同时执行时，methodA和methodB会同时调用b.last()和a.last，但此时A类和B类的methodA、methodB方法（正在执行）都是synchronized，所以无法执行A类和B类的synchronized的last方法，即双方都被阻塞在方法last中，而产生死锁。
![img2](http://b.hiphotos.baidu.com/image/pic/item/83025aafa40f4bfbb2c70b640a4f78f0f73618ee.jpg)


