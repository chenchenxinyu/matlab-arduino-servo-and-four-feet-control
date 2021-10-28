you know, the control dog or four legs is the same as the robot arm, the arithmetic are the similar and the knowledge is interlinked
the arm robot is a project which I have wanted to do for a long time, I want to make a robot who can help me pick my objects and tidy up my desk, you know, that will a excellent thing.
so I have bought a AI arm robot in yahboom company in RMB2699, I will have some note about this.


# date 2021.10.28

## 关于机械臂基础功能的解析

### 开发工具：

jupyterlab  直接调用指定API

其中他们的硬件基础控制，基于自己的扩展版，写了自己的API。

涉及到RGB灯的控制，蜂鸣器的控制，单个舵机，多个舵机的控制，基础API不开源，猜测和自己定制的板子相关，开发思路和单片机嵌入式相似，主要还是基于GPIO的控制和PWM的控制，控制舵机涉及到通信协议，函数包括ID、角度、到达时间（正比于速度）三个参数，理论上对应到API中的通讯协议对应的编码位置，但是API的编写思路可以提升

比如，在官方写的机械臂跳舞的python源码中，只是把不同位置对应角度的信息一条一条写死在里面，代码显得低级而冗长，未加入不同关节坐标系和运动学正逆解，在后期深度开发将较难。

而机械臂实现的色块抓取功能也仅限于指定地图，识别之后直接调用对应固定位置的API，未加入正逆解，无法自由移植

但值得一提的是，用python开发确实简单而方便调试，而且还兼容opencv和对应的AI视觉开发，值得借鉴这种方法，但是需要自行开发底层API，目前还是知识空白，机械臂的正逆解和空间坐标系算法也需要深入

## OPENCV

opencv的课程质量还算客观，同样基于jupyterlab平台开发，兼容性很好，opencv本来就是擅长python开发的语言，直接适用opencv开源的API实现功能，包括图像处理降噪等，可以和matlab图像处理以及后续的人脸识别奠定基础

## ROS和运动学进阶

这是值得意外的一点，这里利用ros开展了机械臂正逆解和坐标系的换算，但是在jupyterlab没有看到对应文件，可能改部分舍弃了jupyterlab的开发平台，也可能这部分的API难以开发，还有待研究

## AI视觉

在jupyterlab中看到了AI视觉部分的源文件，涉及到了ROS的使用，PID算法，YOLO等高级算法，值得分模块钻研

## 总结

运动学进阶和AI视觉几乎能满足机械臂入门的所有要求，之前是小看亚博了

## ps

该机械臂的配套APP做的还可以，之后有空可以深入

学习机械臂过程可以参考亚博的jetson nano对应教程进行，而者有相通之处，同时值得一提的是对应的硬件接口或许有所不同，而机械臂的jetson借助亚博自己设计的主控底部扩展板，可能有所差异，所以镜像出现不兼容的情况













