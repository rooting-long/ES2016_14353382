#1.
##"restricted"， "universe，" 和 "multiverse."前是打上勾的，如果不打勾，当安装ROS从网上下载东西时，会出错
![Deadlock](http://b.hiphotos.baidu.com/image/pic/item/8d5494eef01f3a29ccbf4cfe9025bc315c607c8f.jpg)


#2.    执行下面代码，给APT加上源列表
 `   sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
`

#3.执行下面代码，建立keys
`
sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116
`

#4.执行下面代码，更新最新数据包
`
sudo apt-get update
`

#5.安装完整版ros
`
sudo apt-get install ros-jade-desktop-full
`

#6.初始化和升级rosdep
`
sudo rosdep init
rosdep update
`
#7.设置环境变量
`
echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc
source ~/.bashrc
`
#8.获得安装包的源代码
`
apt-get source ros-jade-laser-pipeline
`

最后一步会出现错误：
E: Unable to find a source package for ros-jade-laser-pipeline


