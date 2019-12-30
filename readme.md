![](https://github.com/lgtbp/lp_tool/blob/master/image/me.ico)
# lp tool多功能工具
* lptool使用stm32f401cc做主控。利用其所有io，还有复用了几个io！以实现daplink,cdc串口，mscU盘，电流和电压检测，预留spi和iic的下载和调试功能，还有2个io。
* 开源电路图(禁止用于商业)，提供boot loader(bin文件)，app地址偏移0xc000.进入bootloader模式按着key1键开机，电脑出现U盘符号，把app文件复制到U盘内即可，app文件需经过lptool.exe软件处理后。

### 使用说明
* 注：按键1是模式切换按键
* lpttol存在多种模式
    1. 不使用usb连接到电脑。（lptool自带电池）
        * 按key1开机后是电流检测模式
    2. 使用usb链接到电脑。
        * 1.daplink模式，可使用cdc串口，屏幕不刷新，保证mcu给dap独占
        * 2.daplink与电流监控共存。
        * 3.pc端监控电流模式。



### 参数说明
* stm32f401cc:frequency 84M,flash 256KB,RAM 64KB,ADC 2.4MSPS,USB
* 电流监控范围：1ua~3A
* 1ua~3ma 范围内精度1ua
* 3ma~3A 范围内进度1ma
* 采集速度1K
* 外挂128Mbit flash
* 0.96寸 80*160 tft。(pcb兼容1.14寸tft)
* 对外供电：电池电压和3.3V（与mcu独立供电），5V(连接usb)

### 对外输入输出io
![](https://github.com/lgtbp/lp_tool/blob/master/image/io.png)