系统升级到一周年正式版及以上(1607)  
依次在设置-更新与安全-针对开发人员选项中，启用"开发人员模式"    
在资源管理器中打开控制面板\所有控制面板项\程序和功能,打开"启用或关闭 Windows功能",勾选"适用于Linux的Windows子系统(Beta)"  
重启电脑  
命令行运行lxrun /install /y开始安装  
安装速度取决于网络情况，下载的文件在%localappdata%\lxss目录下lxss.tar.gz(181M)，解压后大概500M,rootfs目录即为子系统根目录。  
命令行运行bash  
推荐使用cmder进行cmd命令 
在cmder右键窗口条setting startup 选择Command line，输入"bash -cur_console:p"
进入"Settings>Startup>Startup options>Tasks",  
选择"Bash::bash"，将指令修改为"cmd /c "bash" -cur_console:p -new_console:d:%USERPROFILE%"
进入"Settings>Startup>Startup options>Tasks",
选择"bash::bash"，将指令修改为"cmd /c "bash" -cur_console:p -new_console:d:%USERPROFILE%"
sudo su进入root界面 
nano /etc/apt/sources.list  
使用nano编辑 下载映像  
改为阿里云  
->  # deb cdrom:[Ubuntu 16.04 LTS _Xenial Xerus_ - Release amd64 (20160420.1)]/ xenial main restricted  
<br />deb-src http://archive.ubuntu.com/ubuntu xenial main restricted #Added by software-properties
<br />deb http://mirrors.aliyun.com/ubuntu/ xenial main restricted
<br />deb-src http://mirrors.aliyun.com/ubuntu/ xenial main restricted multiverse universe #Added by software-properties
<br />deb http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted
<br />deb-src http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted multiverse universe #Added by software-properties
<br />deb http://mirrors.aliyun.com/ubuntu/ xenial universe
<br />deb http://mirrors.aliyun.com/ubuntu/ xenial-updates universe
<br />deb http://mirrors.aliyun.com/ubuntu/ xenial multiverse
<br />deb http://mirrors.aliyun.com/ubuntu/ xenial-updates multiverse
<br />deb http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse
<br />deb-src http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse #Added by software-properties
<br />deb http://archive.canonical.com/ubuntu xenial partner
<br />deb-src http://archive.canonical.com/ubuntu xenial partner
<br />deb http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted
<br />deb-src http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted multiverse universe #Added by software-properties
<br />deb http://mirrors.aliyun.com/ubuntu/ xenial-security universe
<br />deb http://mirrors.aliyun.com/ubuntu/ xenial-security multiverse
安装Xming 下载地址  
安装完直接打开Xming即可  
安装一个firefox测试  
apt-get install firefox  
运行(在程序指令前加上"DISPLAY=:0 ")  
DISPLAY=:0 firefox  
简化配置  
每次运行程序都要输入DISPLAY=:0挺累的，执行下列指令后重启bash即可省去这个步骤  
echo "export DISPLAY=:0.0" >> ~/.bashrc  
下载sublime  
cd /
 下载  
wget https://download.sublimetext.com/sublime-text_build-3126_amd64.deb  
安装  
dpkg -i sublime-text_build-3126_amd64.deb  
apt-get -y install libgtk2.0-0  
运行
subl

