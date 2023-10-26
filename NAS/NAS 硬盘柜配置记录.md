# NAS 硬盘柜配置记录

## 折腾背景

*updated 2021-2-5*

1. SAS 硬盘 3T 只需 150¥, 过于便宜
2. SAS 阵列卡较便宜, 且支持的硬盘数量也较多(对比 SATA)
3. 服务器砍头硬盘柜价格低廉(<200, 与此同时其他硬盘柜基本 200+)
4. 现有的 NAS 为利用学院的服务器搭建, 担心学院收回的问题, 也打算趁在家之际测试黑群晖的系统重装, 资料迁移等功能

总而言之, 为了省钱, 也是为了测试黑群晖的一些 grub 参数和兼容性, 于是有了该记录

## 硬盘柜需求

*updated 2021-2-5*

本次折腾硬盘柜的要求如下:

1. 至少拥有 12 盘位, 且具有扩展性
2. 阵列卡价格 < 200, 硬盘笼(包括背板) < 300, SAS 硬盘 3T 购入三个(≈450)

## 阵列卡选择

*updated 2021-2-5*

阵列卡选择 LSI 9207-8i (LSI 2308, 2308 是主控的名称), 该阵列卡最高支持 256 个 SAS/SATA/SSD, 且接口为 pcie 3.0 * 8, 且价格低廉 (咸鱼价普遍 < 150)

*updated 2021-2-6*

### LSI 阵列卡的型号问题

LSI 阵列卡有官方正式的型号, 如 LSI 9207-8i, LSI 9211-8i ([UserGuide)](./User_Guide_Host-Bus-Adapters_6Gb_SAS_20130219.pdf)

而店里有时会用主控的型号称呼, 如 LSI 9211-8i 采用 LSIsas2008 主控, 就称为 LSI2008; LSI 9207-8i 采用 LSIsas2308 主控, 就称为 LSI2008. 

### SFF-8087 及 SFF-8482 线选购

SFF-8087 对线, 咸鱼二手, 3¥ 一根, 购入三根

SFF-8087 转 4*SFF-8482, tb, 28¥, 购入一根

运费 10¥, 共 47

## SAS 硬盘选择

*updated 2021-2-5*

这个基本都长得一样, 价格也一样, 暂时没啥选择

*updated 2021-2-6*

已从咸鱼购入 LSI 9207-8i, 价格 100(加上运费)

## 硬盘笼选择

*updated 2021-2-5*

硬盘笼目前看中 tb 上的三款, 分别是 

[HP DL380P G8 25-bay](https://item.taobao.com/item.htm?spm=a230r.1.14.69.7ca3523cy22YCd&id=616118637177&ns=1&abbucket=1#detail)

目前 DL380P 的问题主要是不知道后面的两个 SFF8087 需要接几个才能工作, 推测只需要接一个. 有个大佬实验了 DL380P 12-bay 的背板([ref1)](https://7th-heaven.me/2020/04/29/HPDL380E-gen8-drive-cage-to-array-cabinet/?__cf_chl_captcha_tk__=52450c9ac3bca31786132b68c482781620f40a15-1612460136-0-AVaSPDc7ASkNlem1Gj0myMUREg_mVBtbnrBBXqY7dC-D9C90Dwp3nT9KtMRSt5WE05RCfOwAuHrdZrW0QUI__sRr0G2xq2H6M3vwz70A47mYMRux8R2dTQgyakgxXbjKjd8MQgr5PKbSJpDm3qnpD9opzcAea4mOBTQ2SQt5Rmoyu4wceEOOyHvy_Wz7TwnZgkadMIoxaj9JQiENsGeXQ503KbmYW9pdJkrxI-fhrUjefbq3c-Ib4uWHQ-852YDlZOr8RCkRUSapsGjTO4Q8CbMf1ZfGsh7jpe4hmdo7rggnUvy-2EISD5cFn28akgcB1S_mQGwtvGcsLz_9idtD1pjQrTXg4QY3opNe1CD_yuvB7jrBfXje0uPOCLQwvbYqGzkjtaJ4BXjjUaZgT8ryBUuPlShSwTDmmGxgj4hjEoxTZm4e4tcER0kPzksBnNL7lm85iI7Im2M01lmcZw0Iel_RhbsFHGZWcvu8Y6OqROhcUxqkTemfKSrSCmn3WbSpvfEX6Y7O3C0ucQUPNsopxM81S6tGRMbhA2nYY9seMP9Aj0mebcXOdVrlVpjJBQb-Tetp6UJWLDDXWzZbhA3mkb1I48dGpMRXg0lQqk04f_KH6NraulhkUuz6A4A8F3H256cvYdUxCslDNCl13l-aeU8), 根据他的说法只需要接一个, 但 DL380P 还有个问题是 HP 的该版本硬盘托架有些特性需要配合 HP 服务器, 且根据某个网友折腾记录, 这背板还不一定能直接用(?link). 

而且 DL380P 的 8pin 电源线序和正常 CPU 8pin 不太一样, 具体定义上面的 ref1 已经给出.

![image-20210307013755037](https://tva1.sinaimg.cn/large/008eGmZEly1goaphehgamj31ce0u0khg.jpg)

[HP DL180G6 12-bay](https://item.taobao.com/item.htm?spm=a230r.1.14.125.4a8d714bigdCZe&id=601929376154&ns=1&abbucket=1#detail)

DL180G6 有人做过实验([ref2)](https://post.smzdm.com/p/ag89d6m3/), 推测会好弄一点, 但 DL180G6 只有一个 SFF8087, 不能级联硬盘柜. 而且 10pin 电源接口也需要折腾一下

[某不知名硬盘柜](https://item.taobao.com/item.htm?spm=a230r.1.14.46.3f964451HG5tcg&id=636672954715&ns=1&abbucket=1#detail)

某不知名硬盘柜商家明面标出支持级联, 只需要接一个 SFF8087, 但没折腾记录(且硬盘托架不太好看), 作备用方案. 

ref3: [[NAS教程\]](https://www.hao4k.cn/k-Nas-t224.html) **教你花600元，获得一个24盘位的NAS硬盘扩展柜**

## 硬盘选择

*updated 2021-2-6*

无脑日立 3T sas 硬盘就完事了

已从 tb 购入 3T sas 硬盘*1, 价格 149(包邮)

## record1

*updated 2020-2-20*

硬盘已到, 阵列卡已到, U盘(闪迪)已到

#### T1

使用原 U盘尝试, 路由器未分配 IP, 计划使用 KVM 构建平台

## record2

*updated 2021-04-06*

### 准备工作

已安装 arch, 并且已安装群晖, 但不知为何 macvtap 的虚拟地址 find.synology.com 不能找到, 使用 Synology Assistant 找到了机子, 但是并不能安装 DSM.

原本打算买新网卡, 但最近网卡涨价了, 于是计划使用虚拟网卡, 并通过 gui(kde) 配置群晖.

kde 无法正常使用, 启动了, 但是无法登陆进去.

后来电脑有一次关机, 重启后运行 startx, 报错 xinit: connection to X server lost

一定记住修改 ~/.xinitrc, 不然没法正常启动 kde. **另外要记得 kde 不应该在 root 下启动, 不然会无法启动 chrome(因为 root 启动 chrome 要加参数), 也不能在 ssh 中, 因为不能.**

```bash
To start Plasma with xinit/startx, append export DESKTOP_SESSION=plasma and exec startplasma-x11 to your .xinitrc file. If you want to start Xorg at login, please see Start X at login.
```

要安装 chrome, 或任何一个浏览器, 我选择 AUR, 于是我要先装 git, base-devel, 然后从 github 拖, 然后换用户安装

```bash
# in root
pacman -S git
pacman -S base-devel
# you can <cd> to another path
git clone https://aur.archlinux.org/yay.git
chown -R <user_group>:<user> yay # define in yourself
cd yay
su <user>
makepkg -si
# then if no errors
yay -S google-chrome
```

### 安装 DSM

如果用 sata 做启动盘(指虚拟, 实际上就是 img 转的 qcow2), 那么 DSM 安装时会把他识别为机械硬盘, 所以会报错.

如果用 USB CDROM, 那么犹豫 Readonly, 而 引导程序貌似会处理这个盘, 就会直接把电脑卡爆.

**建议 Device Type: Disk device, Bus type: USB**

DSM 版本 6.2.1 不太行, 直接 unknown error, 但是 6.2.3 可以进, 不过 failed to install the file, 根据以往的经验, 这是因为引导设置不太对

### Convert img to qcow2

```bash
qemu-img convert -f raw -O qcow2 <image.img> <image.qcow2>
```

**DS918+ 貌似不行, 换了 DS3615xs 就可以了**

另外值得注意的是, 可以直接备份之前 nas 的设置, 虽然文件没有, 但是重要的如 User, Group 等都还在

下面计划测试数据迁移, 然后重安装, 看被一台群晖用过的硬盘插到另一个什么是不是能直接不丢数据.

## record3

试了下修改 引导文件参数, 修改了后需要 recover 系统, 但试着 recover 后系统爆炸了, 怀疑是因为引导没正确设置 reinstall 选项(进入系统的时候), 另外, 在试验过程中出现了一次关于 hd0 的读错误, 估计要重安装 DSM 了.

但操作过程是在 ssh tunnel 条件下进行的, 本地操作可能会有不同

## record4

不知道为什么 libvirt 不见了, 且系统开了 kde 后不稳定

arch 太麻烦, 换 debian

服务器不知为何 PSU 挂了, 于是换 win10 下的 vmware

**需要把 img 转成 workstation 的硬盘, 用 StarWind V2V Converter 工具, 免费. 转好之后加 sata.**

vmware 需注意 scsi 硬盘不支持, 添加之后会导致黑群晖启动异常. 而且 workstation 本身不支持设置 boot, 所以只能手动设置一下 sata 的位置, 但也不是很稳, 实在不行只能删了启动重加.

关于硬盘直通, workstation 虽然能够使用物理盘, 但是本质上还是虚拟, 所以 win10 可以看到硬盘状态(这个还算不错), 但黑群晖里是没办法看设备 smart 的

群晖套件 Drive 使用的端口是 6690

## record5

### Active Business Backup

通过网页参数, 已存到 NAS. backup 用的 5510

### Extended driver for RTL8125

XPEnology 有人搞了个 drive 包, 通过替换引导总的 extra.lzma 完成. 尝试使用 1.03b 的 ds3617 进行安装, 结果无法正常启动, 应该是找不到网卡, 可能是把虚拟网卡搞挂了. 原本想通 RTL8125 进去, 但 workstation 不支持 pci 直通. usb 网卡不行.

试着在 workstation 上安装 ds918, 没网, 估计是虚拟的网卡不行.

## record6
