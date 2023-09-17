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

## 构建Shader类

- 把顶点着色器+片段着色器+Program的编写、定义、编译、使用、销毁做成一个类，放到shader.h头文件下
- vertexShaderSource和fragmentShaderSource作为着色器源码，放在项目资源目录下

## 关于VS

解决方案资源管理器 和 文件资源管理器是两个目录树，文件资源管理器的文件可以放在项目目录下同时不放进解决方案资源管理器中