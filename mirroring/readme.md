## 获取镜像文件
链接：https://pan.baidu.com/s/1NsKTcxuPM5rs7dK7nXE59Q?pwd=etqg 
提取码：etqg 


## 文件结构
```
Linux镜像
.
├── Ubuntu系统镜像
|   ├── 根文件系统镜像-用于编译镜像使用
|   └── 通用镜像(extboot)-适用于所有板卡
|
├── Debian系统镜像
|   ├── 根文件系统镜像-用于编译镜像使用
|   └── 通用镜像(extboot)-适用于所有板卡
|
└── OpenWrt系统镜像
```

## 镜像文件命名规则

lubancat-(处理器型号)-(根文件系统)-(桌面类型)-(更新时间)_update

### 处理器型号
rk3566 ：使用rk3566处理器的LubanCat板卡，如LubanCat-1系列和LubanCat-Zero系列

rk3568 ：使用rk3568处理器的LubanCat板卡，如LubanCat-2系列

### 根文件系统
debian10 ： 代表系统使用的根文件系统是debian10

ubuntu18.04 ： 代表系统使用的根文件系统是ubuntu18.04

ubuntu20.04 ： 代表系统使用的根文件系统是ubuntu20.04

ubuntu22.04 ： 代表系统使用的根文件系统是ubuntu22.04

### 桌面类型
xfce ：使用xfce4套件的桌面版镜像

xfce-full ：使用xfce4套件+推荐安装软件包的桌面版镜像，默认语言为中文，安装了中文输入法

lite ：命令行版，无桌面

### 更新日期
更新日期的格式为 yyyymmdd_update 即 年月日_update

### 举例说明
我们以LubanCat-rk3566 debian10的通用镜像为例

lubancat-rk3566-debian10-xfce-20230419_update

板卡的适用型号：适合LubanCat使用rk3566处理器的板卡

根文件系统：debian10

系统类别：xfce·桌面版

更新日期：2023年4月19日
