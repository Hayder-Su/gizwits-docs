title: 博实结BC23M模组接入机智云方案及问题排查指引
---


# （备注：BC23M模组，前期名称叫BC26M，后期变更名称叫BC23M。该模组只是更换名称，其它的功能都是一样。）


# 1.本文编写背景
本文主要介绍博实结BC23M模组如何快速从零开始接入机智云，实现简单的远程控制设备功能，以及常见的模组连接失败问题排查，还提供了该模组的相关资料。

# 2.博实结BC23M资料下载及获取
链接：[https://eyun.baidu.com/s/3eSRIZZG](https://eyun.baidu.com/s/3eSRIZZG) 密码：6pAt

# 3.博实结BC23M外围设计原理理图
请参考本文第2章节的资料分享，《BC23(BC26、BC26M)设计参考》文档。
因为BC23M和BC26、BC23的外围电路设计可以共用的，所以共用该设计文档。

# 4.博实结BC23M串口烧写固件说明

### 4.1.烧录工具下载
烧录工具从第2章下载资料上面获取。

### 4.2.固件下载
由于博实结BC23M模组固件不对外开放，请联系相关的机智云商务同事或技术人员获取。

### 4.3.烧录固件用到的串口
烧录固件用到的串口，如下：

![Alt text](/assets/zh-cn/deviceDev/BC26_png/png1.png)
 
###  4.4.烧录流程
（1）打开烧录工具BSJ App Download Tool V1.3 (BC20 BC26M).exe，选择对应的串口和固件,如下图。

![Alt text](/assets/zh-cn/deviceDev/BC26_png/png2.png)

（2）点击“Start”后，烧写软件界面提示“Waiting for power on module”，此时，再设备上电。

![Alt text](/assets/zh-cn/deviceDev/BC26_png/png3.png)

（3）给模组上电后，烧写软件提示：“Start Download App To Module…”。

![Alt text](/assets/zh-cn/deviceDev/BC26_png/png4.png)

（4）烧写完成后，烧写软件提示：“Write APP Successfully!!”。

![Alt text](/assets/zh-cn/deviceDev/BC26_png/png5.png)

# 5.如何抓取博实结BC23M模组日志

### 5.1.下载机智云打开模组日志工具
 机智云串口打印软件工具下载链接：[https://eyun.baidu.com/s/3oAnx7AU](https://eyun.baidu.com/s/3oAnx7AU) 密码：Um2J

### 5.2.打印模组日志的串口1
打印模组debug日志的引脚为18和GND，然后接到USB 转 TTL 串⼝模块连接
上面，通信波特率为115200bps。

![Alt text](/assets/zh-cn/deviceDev/BC26_png/png6.png)

### 5.3.机智云串口打印软件工具
固件日志已采用加密方式，需要使用机智云日志打印工具将日志解码。请使用机智云日志打印工具。

![Alt text](/assets/zh-cn/deviceDev/BC26_png/png7.png)
备注：映射文件，该文件在第2章资料文件夹“模组日志打印解码映射文件”下获取。不同版本固件，映射文件都不一样。该文件的作用是机智云模组打印工具，根据映射表来解码加密过的模组debug日志。

![Alt text](/assets/zh-cn/deviceDev/BC26_png/png8.png)

# 6.BC23M模组与mcu通信串口

BC23M模组与mcu通信串口引脚为RXD_AUX和TXD_AUX，就是下图的28和29引脚，通信波特率为9600bps。

![Alt text](/assets/zh-cn/deviceDev/BC26_png/png9.png)


# 7.BC23M搭配gokit接入机智云（包含创建数据点，下载代码，demoAPP绑定及控制设备等等）

快速接入文档参考链接：
[http://docs.gizwits.com/zh-cn/deviceDev/debug/G510_Project.html](http://docs.gizwits.com/zh-cn/deviceDev/debug/G510_Project.html)

（注意：BC23M模组与gokit_st底板通信串口通信引脚请查看“6.BC26M模组与mcu通信串口”。）

# 8.FAQ

Q:烧录的时候，如果一直报“Waiting for power on module”提示？

A:重新换一下电脑上面的USB口，出现该问题可能是由于目前使用的串口不能使用。
