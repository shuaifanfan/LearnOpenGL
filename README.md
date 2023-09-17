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