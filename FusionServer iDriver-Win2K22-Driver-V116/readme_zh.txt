################################################################

注意：
1、请先通过兼容性查询工具http://support.huawei.com/onlinetoolsweb/ftca来获取服务器与OS兼容性&部件与OS兼容性，然后使用驱动配套表查询配套关系，查询环境设备驱动是否需要安装或者升级驱动。

2、驱动请上传到OS目录下再执行安装。

3、请使用管理员权限用户进行驱动维护。

################################################################

1.在OS安装时加载iso/img驱动文件

1.1 镜像文件加载方法
	*.iso --- 使用虚拟 CD/DVD
	*.img --- 使用虚拟软盘
	
1.2 应用说明：
	1) RAID卡下的硬盘安装系统时需要加载RAID驱动
	2) SAN Boot启动OS加载FC卡驱动

1.3 镜像文件加载使用指导
	参考操作系统安装指南: https://forum.huawei.com/enterprise/zh/forum.php?mod=viewthread&tid=286397&extra=&page=1



################################################################

2. OS安装完成后安装onboard_driver_XXX.iso里的驱动文件:

onboard_driver_xxx.iso驱动文件列表和手动安装驱动指导:

NIC-CX4-Lx-Win2K22--1-x86_64_silence.exe
---SP333 CX4 driver
#说明：请以归档的包名替代xxx.rpm进行实际驱动安装
#升级安装
1. rpm -Uvh xxx.rpm
2. rmmod txgbe;modprobe txgbe;
3. modinfo txgbe |grep -i version
#降级安装
1. rpm -Uvh xxx.rpm --oldpackage
2. rmmod txgbe;modprobe txgbe;
4. modinfo txgbe |grep -i version