# 为vscode配置cpp环境
下载[mingw-posix](https://github.com/niXman/mingw-builds-binaries/releases)后解压至目录，添加环境变量`(你的前置目录)/mingw32/bin`  
推荐下载`i686-13.1.0-release-posix-dwarf-ucrt-rt_v11-rev1.7z
`
> 一些参数解释  
> **posix**:可移植操作系统接口（英语：Portable Operating System Interface，缩写为POSIX）是IEEE为要在各种UNIX操作系统上运行软件，而定义API的一系列互相关联的标准的总称，其正式称呼为IEEE Std 1003，而国际标准名称为ISO/IEC 9945。  
> **win32**：Win32是Windows 95及后续版本的32位API。 与Win16相同，这个API由在系统DLL中实现的函数组成。 Win32的核心文件是kernel32.dll、user32.dll和gdi32.dll。 Win32最早在Windows NT中引入，而不是Windows 95。  
> **ucrt**:通用CRT (UCRT) 是Microsoft Windows 操作系统组件。 它包含在Windows 10 或更高版本以及Windows Server 2016 或更高版本的操作系统中。 在仍获得外延支持的较旧操作系统上使用Windows 更新，就可以使用UCRT。  
> **msvcrt**：msvcrt.dll是微软在windows操作系统中提供的C语言运行库执行文(Microsoft Visual C Runtime Library)，其中提供了printf,malloc,strcpy等C语言库函数的具体运行实现，并且为使用C/C++(Vc)编译的程序提供了初始化（如获取命令行参数）以及退出等功能。  

之后按照vscode[官方教程](https://code.visualstudio.com/docs/cpp/config-mingw)操作即可

为cpp文件添加两个运行/调试快捷键，将以下代码加入你的键盘快捷方式（crtl+shift+p后搜索keyboard shortcuts,选择带有josn字样的选项）

```json
[
  {
    "key": "f5",
    "command": "C_Cpp.BuildAndRunFile",
    "when": "editorTextFocus && editorLangId == 'cpp'"
  },
  {
    "key": "ctrl+f5",
    "command": "C_Cpp.BuildAndDebugFile",
    "when": "editorTextFocus && editorLangId == 'cpp'"
  }
]
```

现在可以按F5快速运行，crtl+F5调试
