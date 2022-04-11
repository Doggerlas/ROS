Ubuntu 20.04安装Ros Noetic步骤：
综合以下安装帖子：https://blog.csdn.net/r1141207831/article/details/106327172  http://www.4k8k.xyz/article/shao918516/103384095
注意安装时出现的获取IP报错，更换下载源即可。一般阿里云yyds

1.添加 sources.list（设置你的电脑可以从 packages.ros.org 接收软件.）
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list' 

2.添加 keys(这步不成功就换源，一般阿里云源最好)
sudo sh -c '. /etc/lsb-release && echo "deb http://mirrors.tuna.tsinghua.edu.cn/ros/ubuntu/ $DISTRIB_CODENAME main" > /etc/apt/sources.list.d/ros-latest.list'

3.添加秘钥到本地的trusted数据库中并加以验证，方法如下：
sudo apt-key adv --keyserver hkp://pgp.mit.edu:80 --recv-key 421C365BD9FF1F717815A3895523BAEEB01FA116

4.在更新之前，需要安装公钥，否则无法验证签名，这一步也是原书没有的，需要朋友们注意，命令如下：
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys F42ED6FBAB17C654

5.更新Ubuntu 20.04 LTS的最新可用软件包列表：
sudo apt update

6.下面开始安装ROS，推荐安装桌面完整版，这样就可以将ROS、rqt、rviz、机器人通用库、2D/3D仿真器、导航、2D/3D感知等功能一次性安装完成。
(安装依赖，选择性，20220315没有安装)sudo apt install libvtk7-jni libvtk7-java libvtk7-dev libvtk7-qt-dev libpcl-dev
(安装依赖，选择性，20220315没有安装)sudo apt install ros-melodic-pcl-conversions ros-melodic-pcl-ros ros-melodic-perception-pcl ros-melodic-perception
(安装桌面完整版)sudo apt install ros-noetic-desktop-full

7.在使用ROS的每个bash终端中获取此脚本的源代码。
source /opt/ros/noetic/setup.bash

8.环境配置
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
