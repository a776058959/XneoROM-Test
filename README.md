Xneo 刷机，XNEO刷机，xneo刷机，X NEO刷机
# X NEO GSI 测试列表

GSI固件,个人测试列表[点此](https://github.com/a776058959/XneoROM-Test/blob/main/Testlist.md)打开查看

## GSI固件安装教程正文

**以下教程为个人编辑和整理，部分教程和固件出自hardforum网站，如跟着本教程依然不能正常刷机，请点[此](https://hardforum.com/threads/alldocube-x-neo.1998171/)访问hardforum地址直接查看英文帖。**

**由于原作者[MEGA](https://mega.nz/folder/T8EASYRa#SJOqxo75C0MZ59t7sqYW9A/file/H1VgQZqJ)网盘国内无法访问，以下用到的链接替换为国内网盘地址。**

- [X NEO GSI 测试列表](#x-neo-gsi-测试列表)
  - [GSI固件安装教程正文](#gsi固件安装教程正文)
  - [基础固件(底包+扩容+Twrp)刷入（EMMC版本MiFlash刷入）](#基础固件底包扩容twrp刷入emmc版本miflash刷入)
  - [刷入GSI 固件](#刷入gsi-固件)

## 基础固件(底包+扩容+Twrp)刷入（EMMC版本MiFlash刷入）

1.下载**EDL/9008驱动**[蓝奏盘](https://wwzg.lanzoue.com/ihJ1p0i0ktyh)链接，或[Github](https://github.com/a776058959/XneoROM-Test/blob/main/%E6%89%93%E5%BC%80CMD%E5%91%BD%E4%BB%A4%E8%A1%8C.rar)链接，Windows11系统下载→这个版本[9008驱动](https://github.moeyy.cn/https://github.com/a776058959/XneoROM-Test/blob/main/Qualcomm_Diag_QD_Loader_driver.exe)(亲测不需要关闭驱动程序签名验证)。

2.下载[MiFlash](https://cdn.alsgp0.fds.api.mi-img.com/micomm/MiFlash2020-3-14-0.rar)Fastboot刷机软件。下载[modified_global_stock_6gb_with_twrp_v3](https://www.123pan.com/s/aVxtVv-jCzI.html)官方基础固件。(默认是123网盘，[飞猫盘](https://jmj.cc/s/0cns7baw)下载点这里，[百度网盘](https://pan.baidu.com/s/1fdQKElLV5W4WTmnOKmnrDA?pwd=43gc)下载点这里，其他网盘看情况更新。或者去原作者[MEGA](https://mega.nz/folder/T8EASYRa#SJOqxo75C0MZ59t7sqYW9A/file/H1VgQZqJ)网盘)

3.使用解压软件将每个文件解压缩到单独的文件夹中。

4.在解压好的固件 **modified_global_stock_6gb_with_twrp**文件夹中删除 **prog_emmc_ufs_firehose_Sdm660_ddr.elf** 和  **prog_emmc_ufs_firehose_Sdm660_lite.elf**

5.安装EDL/9008驱动程序。

6.(尽量用管理员权限)运行XiaoMiFlash.exe

7.如果打开 MiFlash 之后出现提示 “couldn’t find flash script”，忽略它并点击“确定”。

8.点击“选择”找到 **modified_global_stock_6gb_with_twrp**文件夹。选择并点击“确定”。

9.点击MiFlash左上角的 Configuration，然后点击 MiFlash Configuration。

10.RawProgram xml框里选择“RawProgram_unsparse.xml”，Patch xml框里选择“patch0.xml”。

11.单击“ok”退出MiFlash配置。

12.将X Neo连接到电脑(Windows系统)，并将USB-C电缆连接到USB端口(尽量用USB3.X的口)。

13.将X Neo完全断电。(不需要完全断电也可以，但要多试几次，保证下两条情况依次出现)。

14.按住音量加+音量减+电源，平板会反复出现开机画面几次，直到不再出现开机画面并且屏幕保持黑色时，松开三个按键。这时查看电脑的设备管理器，确认出现9008的COM口设备并且没显示叹号。

15.MiFlash 里点击加载设备以在设备栏中识别到COMx端口(如果设备一栏显示的是一些数字而不是COMx的话就重新插拔数据线或者重新进入9008模式就好了)（x代表随意数字）。

16.MiFlash下边勾选全部删除，然后点击刷机按钮开始刷机，如果开始之后报错提示缺少xxxxxxxx.bat的文件，检查第10步是不是选择错了，或者检查第15步括号里的情况是不是正确。

17.等待显示success说明刷写完成。

18.刷机完成之后，准备工作就到此完成，如果想用官方系统，那就到此为止按住电源键重启即可，如果想刷GSI那就继续往下看。

## 刷入GSI 固件

1.下载[ADB](https://dl.google.com/android/repository/platform-tools-latest-windows.zip)工具包 并解压后进入该文件夹，然后下载[批处理-飞猫盘](https://www.feimaoyun.com/s/z38ea7)或[批处理-Github](https://github.com/a776058959/XneoROM-Test/blob/main/%E6%89%93%E5%BC%80CMD%E5%91%BD%E4%BB%A4%E8%A1%8C.rar)并解压放入ADB工具包文件夹。

2.确保文件夹内至少有“**adb.exe**”和“**fastboot.exe**”和“**打开CMD命令行.bat**”。

3.将下载的GSI固件解压，把里面xxxx.img名字的固件包也放入此文件夹。

4.把X Neo重启到Bootloader模式。如果跟着上边步骤走的，那么已经有TWRP Recovery，只需按住 电源+音量减 按钮，平板会反复出现开机画面1-3次，直到出现开机画面之后2-4秒不再重启，此时松开两个按键机器会进入到Recovery模式，然后Recovery里面重启到Fastboot模式。如果没有跟着上边步骤而是自己解锁的，那么还没有TWRP，可以先正常进系统，启用ADB后允许调试，电脑上命令行输入“ADB reboot bootloader”启动到fastboot模式。

5.双击运行“**打开CMD命令行.bat**”。根据提示输入，例如“fastboot flash system StagOS-12.1_arm64-bvN-UNOFFICIAL.img”，输入完成点击回车。

6.之后会刷入GSI固件，耐心等。

7.等待刷入完成输入“fastboot -w”回车，然后输入“fastboot reboot” 回车。

8.回车之后等待进入系统就可以了，GSI为通用刷机包，是否能正常使用得看运气，或者参考上边我测试的名单。