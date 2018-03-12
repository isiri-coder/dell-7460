dell-7460-7560-hackintosh
===

戴尔燃7000黑苹果安装和日常使用EFI

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**目录**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [说明](#%E8%AF%B4%E6%98%8E)
- [使用方法](#%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95)
- [其他说明](#%E5%85%B6%E4%BB%96%E8%AF%B4%E6%98%8E)
- [Change log](#change-log)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

### 说明

此合集适用于戴尔燃7000系列型号为7460/7560的笔记本电脑
EFI可直接用于安装和日常使用

SSDT hotpatch来自[RehabMan](https://github.com/RehabMan/OS-X-Clover-Laptop-Config) 

文件列表：

1. EFI (必须)
2. 一键开启HIDPI并注入EDID (可选)
3. 网卡驱动 (可选)
4. 黑果小兵的ALCPlugFix (详细说明[来源传送门](https://github.com/daliansky/ALCPlugFix/blob/master/README.md))

### 使用方法

**1**. EFI

安装时：使用transmac写入镜像至U盘后，拷贝EFI到U盘ESP分区中，重启按F12选择U盘启动即可开始安装

日常使用：安装好系统后，使用 `clover configurator` 挂载MacOS所在硬盘的ESP分区，把EFI拷贝进去，重启按F2进入BIOS设置此引导为首选，保存重启即可

**2**. 声卡、耳机

声卡驱动都已经有了，只需要进入 `黑果小兵的ALCPlugFix` 这个文件夹，双击 `install...` 运行即可，可以解决唤醒无声、耳机无声、耳机杂音等问题

**3**. 一键开启HIDPI并注入EDID

此一键命令可开启接近原生的HIDPI设置，不需要RDM软件即可在系统显示器设置中设置

双击安装命令即可进入设置，可选择安装或卸载

效果：

![设置.png](https://i.loli.net/2017/10/26/59f199e85deb7.png)

**4**. 网卡驱动

机器自带的无线网卡无法驱动，只能购买可驱动的网卡更换，推荐购买 `dw1560/dw1830` 这两款网卡，需要注意的是燃系列有个超燃版也就是没有独显的版本，它因为主板结构不同不能安装dw1830，另外dw1830是3天线网卡，在购买时可向商家索要一根 `7~15cm` 的天线，安装时将第三根天线放置在HDD下的开槽处防止金属屏蔽信号

文件夹内有两个网卡的驱动，自行将里面的驱动拷贝到 `EFI/clover/kext/other` 中

### 其他说明

触摸板手势

**1**. 先在设置->键盘->修饰键里设置恢复到默认

默认win对应cmd键，alt对应opt键，我习惯这样

**2**. 在快捷键里设置以下键位

![快捷键.png](https://i.loli.net/2017/10/26/59f19a6078345.png)

**3**. 触控板驱动+手势：

```
轻触和双指右键在设置->触控板里设置
三指轻触：打开通知
四指轻触：最小化应用到dock栏
三指向上轻扫：Mission Control
三指向下轻扫：应用程序窗口
三指向左轻扫：切换到下一个space
三指向右轻扫：切换到上一个space
四指向上轻扫：launchpad
四指向下轻扫：显示桌面
```

### Change log

2018-03-12

- 常规更新clover
- 更新 SSDT hotpath 
- 支持 MacOS 13.4 beta

2017-12-9

- 常规更新clover
- 支持13.2

2017-11-24

- 重新制作 SSDT hotpath 

2017-11-13

- 更新 clover 4297
- 更新 黑果小兵的ALCPlugFix
- 更新 HIDPI脚本，之前的版本虽然模糊过渡自然，但是睡眠唤醒闪屏，鱼与熊掌不可兼得
- 适配 MacOS 10.13.2
- Lilu相关常规更新
- 修复iTunes退出问题
- 可能修复了关机亮度保存，开机亮度恢复问题
- SSDT hotpath来自[RehabMan](https://github.com/RehabMan/OS-X-Clover-Laptop-Config) 


