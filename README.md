# X NEO GSI 测试列表

测试列表[点此](https://github.com/a776058959/XneoROM-Test/blob/main/Testlist.md)打开

## GSI固件安装教程正文

**以下教程出自hardforum网站，本文为个人翻译和修改，本人英语苦手，如跟着教程依然不能刷机，请点[此](https://hardforum.com/threads/alldocube-x-neo.1998171/)访问原帖地址。**

**由于原作者[MEGA](https://mega.nz/folder/T8EASYRa#SJOqxo75C0MZ59t7sqYW9A/file/H1VgQZqJ)网盘国内无法访问，以下用到的链接替换为国内网盘地址。**

- [X NEO GSI 测试列表](#x-neo-gsi-测试列表)
  - [GSI固件安装教程正文](#gsi固件安装教程正文)
  - [基础固件刷入（EMMC版本MiFlash刷入）](#基础固件刷入emmc版本miflash刷入)
  - [刷入GSI 固件](#刷入gsi-固件)

## 基础固件刷入（EMMC版本MiFlash刷入）

1.下载[EDL/9008驱动程序](https://wwzg.lanzoue.com/ihJ1p0i0ktyh)、[MiFlash](ttps://cdn.alsgp0.fds.api.mi-img.com/micomm/MiFlash2020-3-14-0.rar)和[modified_global_stock_6gb_with_twrp_v3](https://jmj.cc/s/0cns7baw)固件。(默认是百度网盘，[飞猫盘](https://jmj.cc/s/0cns7baw)点这里，其他网盘看情况更新。或者去原作者[MEGA](https://mega.nz/folder/T8EASYRa#SJOqxo75C0MZ59t7sqYW9A/file/H1VgQZqJ)网盘)

2.使用解压软件将每个文件解压缩到单独的文件夹中。

3.在解压好的**modified_global_stock_6gb_with_twrp**文件夹中删除**prog_emmc_ufs_firehose_Sdm660_ddr.elf** 和 **prog_emmc_ufs_firehose_Sdm660_lite.elf**

4.安装EDL/9008驱动程序。

5.运行XiaoMiFlash.exe

6.如果出现“couldn’t find flash script”，忽略并点击“确定”。

7.点击“选择”找到**modified_global_stock_6gb_with_twrp**文件夹。选择并点击“确定”。

8.点击Configuration，然后点击 MiFlash Configuration。

9.RawProgram xml里选择“RawProgram_unsparse.xml”，Patch xml里选择“patch0.xml”。

10.单击“ok”退出MiFlash配置。

11.将X Neo连接到电脑(Windows系统)，并将USB-C电缆连接到USB端口(尽量用USB3.X的口)。

12.将X Neo完全断电。(不需要完全断电也可以，但要多试几次，保证下两条情况依次出现)。

13.按住电源+音量加+音量减，直到屏幕保持黑色。

14.点击加载设备以在设备栏中识别到COMXX端口。

15.点击刷机开始刷机，如果报错提示缺少XXXXXXXX.bat的文件，检查第9步是不是选择错了。

16.等待显示success说明刷写完成。

17.刷机完成之后，准备工作就到此完成，如果想用官方系统，那就到此为止按住电源键重启即可，如果想刷GSI那就继续往下看。

## 刷入GSI 固件

1.下载[ADB](https://dl.google.com/android/repository/platform-tools-latest-windows.zip)工具包 并解压后进入该文件夹，然后下载[批处理](https://www.feimaoyun.com/s/z38ea7)并解压放入ADB工具包文件夹。

2.确保文件夹内至少有“**adb.exe**”和“**fastboot.exe**”和“**打开CMD命令行.bat**”。

3.将下载的GSI固件解压，把里面xxxx.img名字的固件包也放入此文件夹。

5.把X Neo重启到Bootloader模式。如果跟着上边步骤走的，那么已经有TWRP，只需按住电源按钮和音量减按钮，就可以重启到recovery，然后再重启至Bootloader。如果还没有TWRP，那么就进系统，先启用ADB，然后允许调试，并发送“ADB reboot bootloader”添加到它。

6.双击运行“**打开CMD命令行.bat**”。根据提示输入，例如“fastboot flash system StagOS-12.1_arm64-bvN-UNOFFICIAL.img”，输入完成点击回车。

7.之后会刷入GSI固件，耐心等。

8.等待刷入完成输入“fastboot -w”回车，然后输入“fastboot reboot” 回车。

9.回车之后等待进入系统就可以了，GSI为通用刷机包，是否能正常使用得看运气，或者参考上边我测试的名单。