# Xuexi-By-ADB
基于ADB的“学习强国”APP自动化脚本

## 为什么要使用ADB这种麻烦的方式？
使用爬虫或者用自动化框架操控浏览器实现，他不香吗？  
当然香！但是也更容易被“学习强国”的后台技术监测到。  
到时候账号被封，那可就相当不香了！  
但是用ADB就不一样了，脚本只是在模拟人类操作手机，本身并未与“学习强国”的服务端产生任何联系；  
实际与服务端交互的仍然是真实手机（或模拟器）上真实运行着的APP，服务端就很难察觉异常。

## 使用条件与方法
1.建议在Windows 10的CMD中运行;  
2.确认安装了ADB驱动，以及Python3.7以上环境（3.8+，‘:=’的用法，在3.8之后）；  
3.此项目仅含有三个文件，其中xuexi.py是主程序，直接运行即可。

## 参数说明
共两个参数，位置固定，皆可省略。

### 第一个参数为工作模式选择，分为下列几种。
-a：全自动运行  
-d：列出当前连接的所有设备  
-t：手动启动应用，手动选择栏目，自动阅读文章  
-v：手动启动应用，手动选择栏目，自动播放视频  

-a全自动运行模式为：自动启动应用，根据程序内置的学习计划自动选择栏目，然后自动阅读文章和播放视频，直至达到每日积分上限为止。    
-d列出当前所连接设备的串号和ID（ADB自动分配），可用于之后的第二个参数。

### 第二个参数为设备的串号或ID，用于指定所操作的设备。
当只有一台设备连接的情况下可以省略，当有多台设备连接的情况下则必须指定，否则将会导致操作混乱。  
利用该参数可以同时操作多台设备，但需要多开CMD窗口，可以手动，也可以另写脚本或批处理自动执行。

### 参数省略
1.省略第二个参数：默认操作当前唯一或第一个设备。  
2.两个参数都省略：等同-a全自动模式。
