# ros_learning_node-
## 安装及参考网址

http://wiki.ros.org/cn/ROS/Tutorials

## 学习笔记
`rospack find [包名称]`  ： 查找包的信息

`roscd [本地包名称[/子目录]]`  ： roscd是rosbash命令集中的一部分，它允许你直接切换(cd)工作目录到某个软件包或者软件包集当中。

`pwd`  ： 输出当前的工作目录

`# catkin_create_pkg <package_name> [depend1] [depend2] [depend3]` ： 创建包并添加一些依赖

`roslaunch [package] [filename.launch]` :  启动roslaunch文件

### roslaunch
 
    <launch>                       //表明这是一个launch文件
     
      <group ns="turtlesim1">           //创建了两个节点分组并以'命名空间（namespace)'标签来区分
        <node pkg="turtlesim" name="sim" type="turtlesim_node"/>      使用节点sim   由于命名空间不同，所以节点sim不会冲突
      </group>
    
      <group ns="turtlesim2">
        <node pkg="turtlesim" name="sim" type="turtlesim_node"/>
      </group>
   
     <node pkg="turtlesim" name="mimic" type="mimic">
       <remap from="input" to="turtlesim1/turtle1"/>
       <remap from="output" to="turtlesim2/turtle1"/>
     </node>
     
     </launch>
