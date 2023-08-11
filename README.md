# 標的物調整方法
## 0. 電腦配置
* Ubuntu 18.04
* ROS Melodic
## 1. 模型位置調整
* 於文件夾位置找到欲修改.world文件，範例位置:src/Firmware/sitl_gazebo/worlds/empty.world開啟.world文件後可已看到文件中有多個模型描述內容，此文件中之模型內容皆為開啟gazebo時直接顯示之物件，以下為.world範例部分內容。
```xml=
...
    <include>

      <name>solarboat2</name>

      <uri>model://solarBoat2</uri>

      <pose>-45.830273 205.161697 2.752399 0 0 1.452424</pose>

    </include>
...
```
* 開啟專案後可以看到
![image](https://github.com/gaya7502/gazebo_object_move/blob/main/Screenshot%20from%202023-08-10%2017-15-53.png)

* 可以看到.world文件中，此模型名稱為solarboat2，此名稱是對應gazebo模型列表中之名稱，若欲修改模型位置，可修改<pose>...</pose>中內容，其中前三個數值對應為gazebo中之x、y、z絕對座標系，後三個數值對應為gazebo中該模型之旋轉角度值，x:-45.830273, y:205.161697, z:2.752399, rx:0, ry:0, rz:1.452424，以上述內容為例，修改該模型之x:-45.830273 -> -55.830273，如下所示。
```xml=
...
    <include>

      <name>solarboat2</name>

      <uri>model://solarBoat2</uri>

      <pose>-55.830273 205.161697 2.752399 0 0 1.452424</pose>

    </include>
...
```
* 修改完成後請記得進行存檔動作，並重新開啟專案
