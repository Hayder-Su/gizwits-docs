title: MCU+2G/4G通讯模组 接入机智云方案
---

# 一、概述

本文主要介绍如何使用Gokit开发板和2G/4G通讯模组快速接入机智云，本文使用的是2G模组G510作为例子。

# 二、设备与机智云数据交互流程

设备与机智云数据交互的基本数据流如下图。

APP接收设备上报数据：设备上报数据→机智云平台→APP端

APP下发设备控制数据：APP端→机智云平台→设备接收数据

![name](/assets/zh-cn/deviceDev/debug/G510/G510project_3_1.png)

# 三、在机智云官网创建设备产品，定义数据点，添加设备

**这里以机智云的入门产品“微信宠物屋”为例子介绍设备接入机智云的整个流程。**

## 1. 创建新产品

![name](/assets/zh-cn/deviceDev/debug/NB_project/NBproject_2.png)

![name](/assets/zh-cn/deviceDev/debug/G510/G510project_3_3.png)

## 2. 创建15个数据点

![创建数据点-1](/assets/zh-cn/quickstart/dev/new7_7.png)

![创建数据点-1](/assets/zh-cn/quickstart/dev/new8_8.png)

![创建数据点-3](/assets/zh-cn/quickstart/dev/new9_9.png)

或者也可以直接选择导入微信宠物屋的数据点，机智云已经创建好了微信宠物屋的数据点。

![创建数据点-3](/assets/zh-cn/quickstart/dev/new10_10.png)

![创建数据点-3](/assets/zh-cn/quickstart/dev/new11_11.png)

# 四、下载自动生成mcu代码

![自动生成MCU SDK-1](/assets/zh-cn/quickstart/dev/new12_12.png)

![自动生成MCU SDK-3](/assets/zh-cn/quickstart/dev/new14.png)

# 五、修改mcu程序，使得mcu可以控制LED灯

修改代码步骤请参考，[微信宠物屋移植与开发](http://docs.gizwits.com/zh-cn/quickstart/UseMCU_BK.html#3-2-%E4%B8%8B%E8%BD%BD%E5%BE%AE%E4%BF%A1%E5%AE%A0%E7%89%A9%E5%B1%8BSTM32CubeMX%E7%89%88%E7%9A%84%E9%A9%B1%E5%8A%A8%E5%BA%93%E6%96%87%E4%BB%B6)

# 六、G510与mcu接线，通电让设备上线

![name](/assets/zh-cn/deviceDev/debug/G510/G510project_14.png)

# 七、设备上线，机智云IOE DEMO APP绑定设备

当模组正常开机十多秒以后，模组会自动连接上机智云平台，此时我们可以使用机智云APP扫描二维码的方式绑定G510，使用机智云串口助手的小工具生成设备绑定二维码（串口助手下载地址https://download.gizwits.com/zh-cn/p/98/119）

![name](/assets/zh-cn/deviceDev/debug/G510/G510project_12.png)

生成设备绑定二维码后，我们可以下载机智云IOE DEMO APP扫码绑定设备

（APP下载地址https://download.gizwits.com/zh-cn/p/98/99）

![name](/assets/zh-cn/deviceDev/debug/G510/G510project_13.png)

# 八、控制设备，点亮/熄灭LED灯成功，机智云接入完毕

![name](/assets/zh-cn/deviceDev/debug/G510/G510project_11.png)

![APP收发设备数据](/assets/zh-cn/quickstart/dev/new39_39.png)

# 九、机智云后台查看设备交互数据

![机智云后台查看设备交互数据1](/assets/zh-cn/quickstart/dev/new40_40.png)

![机智云后台查看设备交互数据2](/assets/zh-cn/quickstart/dev/new41_41.png)

# 十、参考代码下载

附件：[微信宠物屋参考代码](http://docs.gizwits.com/assets/pdf/gokit_code.zip)
