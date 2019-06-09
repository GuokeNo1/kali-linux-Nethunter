搞机有风险，入坑须谨慎。
> 工作原理主要借鉴了 [linuxonAndroid](https://sourceforge.net/projects/linuxonandroid/) 和 [Kali Linux NetHunter](https://www.kali.org/kali-linux-nethunter/)

简单的分析了一下大致是将 linux 的镜像挂载或者解压到 /data/local/ 目录下，然后设置PATH最后通过busybox的chroot将挂载或解压的目录临时作为根目录  **/**  。与Android共享一个内核。
> ## 准备个工作
- Android设备一部(root,busybox,Nethunter的APP[[蓝奏云](https://www.lanzous.com/b771490)][[Github(apk.zip)](https://github.com/GuokeNo1/kali-linux-Nethunter/releases/tag/kalionAndroid))]
- [kali Linux镜像一个(链接中的kalifs-armhf-minimal.tar)](https://github.com/GuokeNo1/kali-linux-Nethunter/releases/tag/kalionAndroid)
- 手  脑子

> ## 操作

操作前确保设备以及root并且安装了busybox

将所有Nethunter的apk安装若只用 **kali** 的 **terminal** 只需要安装提供的 **nethunter.apk**和**Term-nh.apk**

打开安装好的 **NetHunter终端** 在弹出的 Select shell  对话框中选择 ANDROIDSU 并给这个app授权root然后我们将获得一个Android的root账户权限的shell
有了root权限以后我们先在 **/data/local/** 目录下创建一个 **nhsystem** 的文件夹

**```mkdir /data/local/nhsystem```**

然后我们进入到之前下好的镜像所在目录，为放在了我的sdcard目录下所以我需要执行 

**```cd /mnt/sdcard/```**

将kali的tar包copy到我们刚创建的**/data/local/nhsystem/**目录下

 **```cp kalifs-*.tar /data/local/nhsystem/```**
 
然后在进入到 **/data/local/nhsystem/** 目录下 

**```cd /data/local/nhsystem/```**

解压我们复制过来的tar压缩文件 

**```tar -xvf kalifs-*.tar```**

删除tar文件

**```rm -rf kalifs-*.tar```**

然后打开另一个APP **NetHunter** 点击菜单中的 **Kali Chroot Manager** 然后点击 **ADD METAPACKAGES** 默认 **INSTALL&UPDATE** 即可打开一个Kali的shell了。

然后下次我们打开 **kali shell** 可以直接通过**NetHunter终端**这个APP选择Kali就OK了

> ## 不足之处

目前发现无法将wlan0设置为监听模式所以望大家找到方法告诉我一下

> ## 不要脸的二维码

![支付宝](https://raw.githubusercontent.com/GuokeNo1/kali-linux-Nethunter/master/image/AliPay.jpg)|![微信](https://raw.githubusercontent.com/GuokeNo1/kali-linux-Nethunter/master/image/WeChatPay.png)
----|----
