# matlab-arduino-servo-and-four-feet-control
Now I am learning using matlab to test the arduino the four feet spider move, for learn how to control the gait.
# date-2021年10月17日
these days I have do the first demol to make sure somethings right, now take the summary here.
## 第一代 date：2021年10月17日

## 产品描述：

四足  主控Nano  舵机SG90  连接 ：杜邦线

供电  18650*2  LM2596降压模块（8.4转5v）

充电模块 开关  舵机扩展版

## 实现程度

arduino多文件编程

定时器使用

基本电源管理

站立和简单步态



## 问题

1. 舵机质量差，扭矩太小，出现一个故障舵机，勉强能支撑机器人自重
2. 舵机旋转方向和初始角度考虑不全面，算法编写复杂度加深，具体可见图片

![1634436225137](https://i.loli.net/2021/10/17/KixyRujZh5Xv4qb.jpg)

3. 各部分布局不合理，线冗余，重心偏，电池等模组不方便更换
4. 做电源管理的时候接线繁杂，需要共地和共电极的部分处理困难
5. 舵机活动位置有限（受硬件制约），但没有反馈装置，导致舵机卡位，整体角度不方便测量
6. 双模式下需要能够更换腿部
7. 精确度控制  加入imu保持水平  pid
8. 极坐标换算未写入
9. 希望能将渴望的姿态输入之后自动解算出角度和运动
