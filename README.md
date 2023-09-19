# LearnOpenGL

- 参考
- https://learnopengl-cn.github.io

## Windows VS配置环境

- 链接**opengl32.lib**，在Windows本地存了多份，用x64

C:\Program Files (x86)\Windows Kits\10\Lib\10.0.22621.0\um\x64\OpenGL32.Lib

C:\Program Files (x86)\Windows Kits\10\Lib\10.0.22621.0\um\arm64\OpenGL32.Lib

C:\Program Files (x86)\Windows Kits\10\Lib\10.0.22621.0\um\x86\OpenGL32.Lib

C:\Program Files (x86)\Windows Kits\10\Lib\10.0.22621.0\um\arm\OpenGL32.Lib

- 自己编译glfw，添加包含目录，添加库文件目录，链接glfw3.lib

- 下载对应版本glad，添加包含目录，把glad.c添加到项目源文件下面

- GLM(Open**GL** **M** athematics),只有头文件，直接去官网下载到本地，然后把头文件目录，写入项目配置的包含目录中

  GLM还有一个方法是，GLM的几个用到的头文件放到项目头文件目录下，然后#include "****" ,但是不建议，因为自己写的头文件才这样放                        

- std_image.h,用来加载图像文件，是一个单头文件图像加载库，整到工程头文件里，然后需要新建.cpp文件引用他

## 构建Shader类

- 把顶点着色器+片段着色器+Program的编写、定义、编译、使用、销毁做成一个类，放到shader.h头文件下，shader.h放到项目头文件目录下边
- vertexShaderSource和fragmentShaderSource作为着色器源码，放在项目资源目录下

## 关于VS

解决方案资源管理器 和 文件资源管理器是两个目录树，文件资源管理器的文件可以放在项目目录下同时不放进解决方案资源管理器中

## 关于相机

model矩阵，负责物体在世界坐标系中的位置和姿态：可以设置相对于初始位置的旋转角度，当这个角度设置为随时间变化的值，每一帧渲染出来，就变成了动画

view矩阵，负责世界坐标系整体的移动， 这个移动是相对于本身观察视角

projection矩阵，在上述两个矩阵确定的情况下，负责在三维空间中，观察到的景象，怎么被输出到屏幕上。本教程中，projection是透视投影，将一个view视角面前的台体空间，按照透视投影的关系，投影到2维平面。



openGl没有相机，所谓相机，就是封装好LookAt函数，以设置view矩阵。这样把相机的移动，转换成整个世界坐标系的移动。