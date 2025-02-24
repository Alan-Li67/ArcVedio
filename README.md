ArcVideo 项目
一、项目概述
ArcVideo 是一个使用 C# 编写的跨平台视频处理应用，主要采用进程隔离方式对部分开源 GPL 组件进行封装，提供跨进程调用方法。通过命名管道和 FFMPEG 库实现多摄像头的实时视频流处理和录制功能。

二、功能介绍
多摄像头支持：支持 USB 摄像头和 OV5647 摄像头，可同时处理主摄像头、左摄像头和右摄像头的视频流。
实时视频流：能够实时读取摄像头数据并显示在界面上。
视频录制：支持对主摄像头、左摄像头和右摄像头的视频流分别进行录制，录制文件格式为 MP4。
进程隔离：通过创建独立的进程来运行 GPL 组件，确保主应用程序与这些组件之间的隔离，避免直接使用 GPL 组件带来的法律风险和兼容性问题。
跨进程通信：提供命名管道机制，方便不同进程之间的数据交换。
三、技术栈
编程语言：C#
开发环境：Visual Studio 2022
依赖库：OpenCvSharp（用于图像处理）、FFMPEG（用于视频录制）
其他工具：DirectShowLib（用于获取摄像头设备信息）
四、项目结构
        
复制代码
ArcVideo/
├── bin/
│   └── Debug/
│       └── ArcVideo.exe
├── config/
│   ├── MainArcVideo.json
│   ├── LeftArcVideo.json
│   └── RightArcVideo.json
├── src/
│   ├── ArcVideo/
│   │   ├── App.xaml
│   │   ├── App.xaml.cs
│   │   ├── MainWindow.xaml
│   │   ├── MainWindow.xaml.cs
│   │   └── ...
├── ...
└── ...

    
五、使用方法
启动项目：打开 Visual Studio 2022，加载 ArcVideo 项目，然后点击“开始调试”按钮启动项目。
配置摄像头：在 config 目录下创建或修改 MainArcVideo.json、LeftArcVideo.json 和 RightArcVideo.json 配置文件，设置摄像头名称、分辨率和帧率。
运行应用：启动应用后，将自动扫描可用的摄像头设备，并根据配置文件中的设置进行初始化。用户可以通过界面上的按钮控制摄像头的开启、关闭和录制功能。