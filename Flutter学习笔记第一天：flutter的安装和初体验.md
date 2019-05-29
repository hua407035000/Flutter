
**1.flutter是什么**

Flutter是谷歌的移动端**跨平台UI框架**，可以快速在iOS和Android上构建高质量的原生用户界面。
**可以用一套代码同时构建Android和iOS应用**，并且性能可以达到原生应用一样的性能。 。
[详情请参考Flutter简介](https://flutterchina.club/)

**2.flutter的安装（这里只讲android方面，ios请参照官方文档）**

   系统要求：
  要安装并运行Flutter，您的开发环境必须满足以下最低要求:
 1.操作系统: Windows 7 或更高版本 (64-bit)
 2.磁盘空间: 400 MB (不包括Android Studio的磁盘空间).
 3工具: Flutter 依赖下面这些命令行工具：Git for Windows (Git命令行工具)

   开始安装：
 1.获取Flutter SDK（[官方网址](https://flutter.dev/docs/development/tools/sdk/releases?tab=windows#windows)）
 2.安装好之后在Flutter安装目录的flutter文件下找到**flutter_console.bat**，
 3.双击运行并启动flutter命令行在终端运行 **“flutter ”**命令 
 4.并启动flutter命令行在终端运行 **“flutter doctor”**命令 
	
	如果出现下面两张图表示成功
**注意：要在双击<font color=#ff0000>flutter_console.bat </font>之后 在<font color=#ff0000>  flutter console</font>  里面打这两个命令行！！** 
![在这里插入图片描述](https://img-blog.csdnimg.cn/2019052916324795.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM0OTI3MTE3,size_16,color_FFFFFF,t_70)
![](https://img-blog.csdnimg.cn/20190529163255216.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM0OTI3MTE3,size_16,color_FFFFFF,t_70)
**3.创建第一个flutter应用**
   1安装Android StudioAndroid Studio, 3.0或更高版本.
    2.安装 Flutter 和 Dart 插件
     选择<font color=#ff0000>File--->Settting--->Plugins--->选择 Browse repositories…, </font> 	选择<font color=#ff0000> Flutter  </font> 	插件和选择<font color=#ff0000> Dart </font> 	 插件install </font> 	
   3.重启Android Studio后插件生效.
   4.选择 File>New Flutter Project  ,sdk选择刚刚下载的sdk目录
   5选择 Flutter application 作为 project 类型, 然后点击 Next
   6.输入项目名称 (如 myapp), 然后点击 Next点击 Finish等待Android Studio安装SDK并创建项目.
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190529170924709.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM0OTI3MTE3,size_16,color_FFFFFF,t_70)![在这里插入图片描述](https://img-blog.csdnimg.cn/20190529164553785.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM0OTI3MTE3,size_16,color_FFFFFF,t_70)
