# 標的物調整方法
## 0. 電腦配置
* Ubuntu 18.04
* ROS Melodic
## 1. 模型位置調整
* 於文件夾位置找到欲修改.world文件，範例位置:src/Firmware/sitl_gazebo/worlds/empty.world開啟.world文件後可已看到文件中有多個模型描述內容，此文件中之模型內容皆為開啟gazebo時直接顯示之物件，以下為.world範例部分內容，以模型solarboat1模型為例。
```xml=
...
    <include>

      <name>solarboat1</name>

      <uri>model://solarBoat1</uri>

      <pose>-67.638046 176.613419 2.752428 0 0 0</pose>

    </include>
...
```
* 開啟專案後可以找到模型名稱為solarboat1之位置。
![image](https://github.com/gaya7502/gazebo_object_move/blob/main/Screenshot%20from%202023-08-10%2017-15-53.png)

* 依照下圖順序，點擊上方十字圖示後，再點擊左方列表中Models下的solarboat1模型，即可發現畫面中之模型靜止不動，接著再查看其位置-pose內容，此位置為當前位置。
![image](https://github.com/gaya7502/gazebo_object_move/blob/main/Screenshot%20from%202023-08-10%2017-16-22.png)

* 回到.world文件中，若欲修改模型位置，可修改<pose>...</pose>中內容，其中前三個數值對應為gazebo中之x、y、z絕對座標系，後三個數值對應為gazebo中該模型之旋轉角度值，x:-67.638046, y:176.613419, z:2.752428, roll:0, pitch:0, yaw:0，以上述內容為例，修改該模型之x:-67.638046 -> -57.638046，如下所示。
```xml=
...
    <include>

      <name>solarboat1</name>

      <uri>model://solarBoat1</uri>

      <pose>-57.638046 176.613419 2.752428 0 0 0</pose>

    </include>
...
```
* 修改完成後請記得進行存檔動作，並重新開啟專案，即可看到solarboat1模型向左偏移了10個單位。
![image](https://github.com/gaya7502/gazebo_object_move/blob/main/Screenshot%20from%202023-08-10%2017-16-21.png)
