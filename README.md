#  一、DOL框架描述  

The distributed operation layer (DOL) is a framework that enables the (semi-) automatic mapping of applications onto the multiprocessor SHAPES architecture platform. 

The DOL consists of basically three parts:

* DOL Application Programming Interface

* DOL Functional Simulation

* DOL Mapping Optimization



# 二、DOL安装笔记

1.  打开命令行操作窗口
2.  安装一些必要的环境：
 
    ` $	sudo apt-get update `   
    ` $	sudo apt-get install ant`      
    ` $ 	sudo apt-get install openjdk-7-jdk `   
     ` $	sudo apt-get install unzip`
3. 下载文件
    在命令行输入        
` sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz   `   
` sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip   `   
或者从主机下载完拷贝进去。   
[参考网站](http://jingyan.baidu.com/article/c33e3f48a5c153ea15cbb5b2.html)
4. 解压文件
新建dol的文件夹    
` $	mkdir dol   `   
将dolethz.zip解压到 dol文件夹中   
` $	unzip dol_ethz.zip -d dol   `   
解压systemc   
` $	tar -zxvf systemc-2.3.1.tgz   `
5. 编译systemc   
解压后进入systemc-2.3.1的目录下  
` $	cd systemc-2.3.1 `  
新建一个临时文件夹objdir  
` $	mkdir objdir `  
进入该文件夹objdir  
` $	cd objdir`  
运行configure(能根据系统的环境设置一下参数，用于编译)  
` $	../configure CXX=g++ --disable-async-updates`  
下图为运行configure之后的截图     
![](http://g.hiphotos.baidu.com/image/pic/item/42a98226cffc1e1764adb2d14290f603728de9c4.jpg)
编译
` $	sudo make install`  
编译完后文件目录如下($ cd ..        $ ls  ）  
![](http://d.hiphotos.baidu.com/image/pic/item/0bd162d9f2d3572c028fa53c8213632763d0c3e4.jpg)
能看到include, lib-linux64(对于32位系统，这里是lib-linux)  
记录当前的工作路径(会输出当前所在路径，记下来，待会有用)  
$	pwd   
![](http://d.hiphotos.baidu.com/image/pic/item/9358d109b3de9c8242dfc06f6481800a18d84393.jpg)
这里表示我当前的工作路径为 /root/systemc-2.3.1

    6.编译DOL  
进入刚刚dol的文件夹
$	cd ../dol
修改build_zip.xml文件  
找到下面这段话，就是说上面编译的systemc位置在哪里，  
<property name="systemc.inc" value="YYY/include"/>  
<property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>  
把YYY改成上页pwd的结果（注意，对于  64位 系统的机器，lib-linux要改成lib-linux64）  
然后是编译  
` $	ant -f build_zip.xml all`  
若成功会显示build successful  
接着可以试试运行第一个例子  
进入build/bin/mian路径下  
` $	cd build/bin/main`  
然后运行第一个例子  
` $	ant -f runexample.xml -Dnumber=1`  

成功结果如图
![](http://e.hiphotos.baidu.com/image/pic/item/5fdf8db1cb13495485c9d1845e4e9258d0094a7e.jpg)
# 三、实验心得
本次实验的内容是github版本控制和熟悉markdown文档的书写格式，并把markdown文档上传到github仓库。Github的版本控制的意思是每个人对同一个文档进行修改后，不用一份一份对照拼接成一份新文档，而是上传到Github，显示每个人作的修改，这样每个人的修改都可以被知道。而markdown作为一款操作简单，排版简易的文字编辑软件，用起来确实比Word等文字软件要方便很多。