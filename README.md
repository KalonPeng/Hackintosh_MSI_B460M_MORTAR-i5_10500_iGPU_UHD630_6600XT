# Hackintosh_MSI_B460M_MORTAR-i5_10500_iGPU_UHD630_6600XT
微星MSI B460M迫击炮+10500+6600xt的黑苹果引导配置

**[240213 update] **

✅更新opencore 9.8版本。

✅升级 kext 至最新版本。

✅修改kext顺序，修复GPU温度不显示的问题（再次感谢Charley-Tang反馈）。

⚠️目前我停留在了Macos 13 Ventura最新版本，有比较大的原因是付费软件不兼容macos14版本，不想再花钱购买新版本了。Macos 14版本的博通网卡会有兼容的问题，解决方案可以到远景去搜一下(建议直接用板载的Intel网卡），我个人是不建议升级了，在13版本养老挺好的。等哪天确实需要14版本的时候我再折腾更新一下。

⚠️如果使用双系统的，建议去搜一下“双系统共用蓝牙”的教程，这样可以切换系统蓝牙依旧保持匹配，体验挺不错的。

__________________________________________


**[230903 update] **

更新opencore 9.4版本。

升级 kext 至最新版本。

修改 DP 内存参数以支持4K高分辨率屏幕显示（感谢Charley-Tang反馈）。

添加 intel网卡驱动。

添加 BRCM 网卡驱动。
__________________________________________

之前一直用别人的EFI（见下面分割线），磕磕碰碰从10用到12，升级到13之后就开始频繁出现问题，于是乎自己从0开始配置了这个EFI，经过1天的学习和调试，各方面都得到了极大的完善，一切正常（99%完美，也没发现有啥问题），第一次使用GitHub，不知道怎么使用，板式凑合看吧。


作为长久的伸手党，这次终于完成了身份的转变。


⚙️配置： 显卡：UHD630➕华擎AMD 6600xt ｜ CPU：i5 10500 ｜ 主板：微星MSI B460M 迫击炮 ｜ 内存：最便宜的32GB ｜ 硬盘：京造1T ｜ 网卡: BCM94360CS2（用intel网卡的自行加入驱动）。


💿OC版本：正式版 9.4 

💿系统版本：Ventura 13.3


‼️事前准备： Bios开启D.T.M。‼️


⚠️注意：


⚠️1、自行修改3码。

⚠️2、开机logo跑进度条的时候就有几秒钟的黑屏时间，等一会就好。 · 目前设置核显仅用作硬件加速，需要你接独显输出，开机很快进入桌面，核显加速正常。 · 如果没有独显，或者你想使用核显也作为输出口，需要调整参数“DP-PciRoot(0x0)/Pci(0x2,0x0)-AAPL,ig-platform-id”的“0300C89B”为“00009B3E”。缺点就是开的时候黑屏时间比较长，等一下。

⚠️3、解决双系统时间不一致：在Windows终端下使用管理员权限运行"Reg add HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation /v RealTimeIsUniversal /t REG_DWORD /d 1"

⚠️4、设置默认启动项：多系统在启动选择界面，先使用键盘移动到要启动的项，然后按Ctrl+Enter(回车键)进入系统，下次重启后默认就选中该项了
