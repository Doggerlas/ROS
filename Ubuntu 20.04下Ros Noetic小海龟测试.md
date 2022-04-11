Ubuntu20.04下 Ros -Noetic小海龟测试：https://blog.csdn.net/richardpark/article/details/109066841
小海龟测试需要依次打开三个新的命令行窗口：
窗口A 启动ros程序：roscore
窗口B 启动海龟程序：rosrun turtlesim turtlesim_node
窗口C 启动海龟控制程序，用键盘控制海龟移动：rosrun turtlesim turtle_teleop_key

小海龟简单拓展
显示调用节点：rqt_graph
海龟自主行动：rostopic pub -r 5 /turtle1/cmd_vel geometry_msgs/Twist 然后Tab 修改”linear“和”angular“中数据，便可以让小海龟做圆周运动了。
