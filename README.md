# USB2CAN_cx
本项目的开发目的是为了给英特尔® NUC及其它x86架构的平台提供一个CAN (Controller Area Network)的外设接口。由于NUC及大部分x86不具有SPI等简单外设接口，故无法使用MCP2515等SPI (Serial Peripheral Interface) 转CAN芯片。为此，本项目基于github的开源方案candleLight开发，采用STM32F072CBT6作为主控芯片，实现USB (Universal Serial Bus) 转CAN的功能。本项目基于广东工业大学的usb2can项目开发，删去了多余的usb hub和串口接口（在大部分环境下，只需要一路usb转can即可满足要求），同时添加swd接口、ESD静电保护等模块，方便烧录固件。

![image](https://github.com/cxnaive/USB2CAN_cx/blob/master/pics/img.jpg)

(图片为初始版本，本仓库版本增加了CC脚电阻、ESD静电保护和电脑5V保护，优化了差分走线，过孔盖油)


**具体应用参照：**

https://github.com/rm-controls/rm_usb2can/blob/main/README_CN.md
# swd固件烧录
直接使用JFlash工具烧录firmware.bin至单片机即可，线序参考下图：

![image](https://github.com/cxnaive/USB2CAN_cx/blob/master/pics/swd.png)

# 特别感谢以下项目
[rm_usb2can](https://github.com/rm-controls/rm_usb2can)

[candleLight_fw](https://github.com/candle-usb/candleLight_fw)