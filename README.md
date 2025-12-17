# LubanCat-4-Development-Guide
## 参考资料

This repository is used to record the development processes （allocation algorithm to diagnosis bearing fault） of LubanCat-4. 
>[6. LubanCat-4系列硬件介绍 — 快速使用手册—基于LubanCat-RK356x系列板卡 文档 (embedfire.com)](https://doc.embedfire.com/linux/rk356x/quick_start/zh/latest/quick_start/lubancat/lubancat4.html)

## LubanCat-4

### 板卡概述

LubanCat-4是野火科技基于RockChip RK3588s设计的一款低功耗、高性能单板电脑。LubanCat-4不仅能作为高性能单板电脑来使用，还可以作为嵌入式主板， 用于显示、控制、网络传输，文件存储，边缘计算等多种场景。

![概述1](image/20240712132257.png)
![概述2](image/20240712132313.png)

### 资源概述

![资源概述1](image/20240712132335.png)
![资源概述2](image/20240712132349.png)
![资源概述3](image/20240712132414.png)


| 板卡名称        | LubanCat-4                                 |
| ----------- | ------------------------------------------ |
| 电源接口        | Type-C5V@4A直流输入                            |
| 主芯片         | RK3588S(四核A76+四核A55、Mali-G610、6T算力)        |
| 内存          | LPDDR4X-4/8GB                              |
| 存储          | eMMC-32/64/128GB                           |
| 以太网         | 10/100/1000M自适应以太网口                        |
| USB2.0      | Type-A接口x3(HOST)                           |
| USB3.0      | Type-A接口x1(HOST)                           |
| USB3.0      | Type-C接口x1(OTG)，固件烧录接口，DP显示（支持与其他屏幕进行多屏异显） |
| Debug串口     | 一路Debug串口，默认参数1500000-8-N-1                |
| 按键          | ON/OFF(开关机键)、MR(MaskRom)、REC(Recovery)     |
| 音频接口        | 耳机输出+麦克风输入2合1接口                            |
| 40Pin接口     | 兼容树莓派40Pin接口，支持PWM,GPIO,I2C,SPI,UART功能     |
| MINI-PCIE接口 | 可配合全高或半高的WIFI网卡、4G模块或其他MINI-PCIE接口模块使用     |
| SIM卡接口      | 需要搭配4G模块使用                                 |
| HDMI2.1     | 显示器接口,支持与其他屏幕进行多屏异显                        |
| MIPI-DSI    | 2xMIPI屏幕接口,支持与其他屏幕进行多屏异显                   |
| MIPI-CSI    | 3x摄像头接口                                    |
| TF卡座        | 支持TF卡启动系统，最高支持512GB                        |
| 红外接收        | 支持红外遥控                                     |
| RTC电池接口     | 支持RTC功能                                    |
| 风扇接口        | 支持安装风扇散热                                   |


## 烧录镜像到eMMC

### 工具获取

下载mirroring 文件夹中的unbuntu镜像文件，以及software中的烧录工具 **RKDevTool** 和驱动程序 **DriverAssitant**，将这些压缩文件下载并解压缩（unbuntu镜像文件解压缩为img格式），同时安装驱动程序 **DriverAssitant**（其它文件压缩即可，不需要安装）安装反式如下图：双击 DriverInstall.exe 进入驱动安装界面，点击 驱动安装 即可开始安装驱动。如果不确定以前是否安装过旧版驱动， 先点击驱动卸载移除旧版本驱动程序，再点击驱动安装。

![DriverInstall](image/DriverInstall.png)

### MASKROM模式烧录镜像

我们打开 RKDevTool 烧录工具，并设置板卡进入烧录模式。

![打开 RKDevTool 烧录工具](image/1.png)

```
1.准备一根Type-C线，一端连接电脑，一端预留备用
2.连接电源线
3.按住MR按键(MASKROM)不松开，先将预留的USB线插入板卡的USB-OTG接口，再插入电源
4.等待软件提示 发现一个MASKROM设备，再松开按键
5.如果不成功，重复2-4步骤。
```

![MR-1](image/MR-1.png)
然后就可以点击 固件 选择要烧录的镜像，如update.img然后打开
![MR-2](image/MR-2.png)
等待固件加载完成，然后点击升级，开始烧录固件
![MR-3](image/MR-3.png)
镜像烧录成功，如下图
![MR-4](image/MR-4.png)





