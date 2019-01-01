# 如何安装Shadowsocks服务端
## 服务器购买
理论上各类独服、VPS、NAT-VPS均可安装Shadowsocks服务，但由于GFW、服务商带宽线路等问题会造成Shadowsocks服务连接速度较慢，选购服务器前需要提前了解一下服务器基本信息，可以参考本人的博客 [我的博客](http://blog.csdn.net/guodongxiaren "AFFVPS")


## Shadowsocks 一键安装脚本（四合一）
本脚本适用环境  
系统支持：CentOS 6+，Debian 7+，Ubuntu 12+  
内存要求：≥128M  
日期　　：2018 年 11 月 05 日  

关于本脚本  
1、一键安装 Shadowsocks-Python， ShadowsocksR， Shadowsocks-Go， Shadowsocks-libev 版（四选一）服务端；  
2、各版本的启动脚本及配置文件名不再重合；  
3、每次运行可安装一种版本；  
4、支持以多次运行来安装多个版本，且各个版本可以共存（注意端口号需设成不同）；  
5、若已安装多个版本，则卸载时也需多次运行（每次卸载一种）；  


默认配置
服务器端口：自己设定（如不设定，默认从 9000-19999 之间随机生成）  
密码：自己设定（如不设定，默认为 teddysun.com）  
加密方式：自己设定（如不设定，Python 和 libev 版默认为 aes-256-gcm，R 和 Go 版默认为 aes-256-cfb）  
协议（protocol）：自己设定（如不设定，默认为 origin）（仅限 ShadowsocksR 版）  
混淆（obfs）：自己设定（如不设定，默认为 plain）（仅限 ShadowsocksR 版）  
备注：脚本默认创建单用户配置文件，如需配置多用户，请手动修改相应的配置文件后重启即可。  

客户端下载  
常规版 Windows 客户端  
<pre>https://github.com/shadowsocks/shadowsocks-windows/releases</pre>

ShadowsocksR 版 Windows 客户端  
<pre>https://github.com/shadowsocksrr/shadowsocksr-csharp/releases</pre>

使用方法  
使用root用户登录，运行以下命令：  

<pre>wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh
chmod +x shadowsocks-all.sh
./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log</pre>
安装完成后，脚本提示如下
<pre>Congratulations, your_shadowsocks_version install completed!
Your Server IP        :your_server_ip
Your Server Port      :your_server_port
Your Password         :your_password
Your Encryption Method:your_encryption_method

Your QR Code: (For Shadowsocks Windows, OSX, Android and iOS clients)
ss://your_encryption_method:your_password@your_server_ip:your_server_port
Your QR Code has been saved as a PNG file path:
your_path.png

Welcome to visit:https://teddysun.com/486.html
Enjoy it!</pre>
卸载方法  
若已安装多个版本，则卸载时也需多次运行（每次卸载一种）  

使用root用户登录，运行以下命令：  

<pre>./shadowsocks-all.sh uninstall</pre>
启动脚本  
启动脚本后面的参数含义，从左至右依次为：启动，停止，重启，查看状态。  

Shadowsocks-Python 版：
<pre>/etc/init.d/shadowsocks-python start | stop | restart | status</pre>

ShadowsocksR 版：
<pre>/etc/init.d/shadowsocks-r start | stop | restart | status</pre>

Shadowsocks-Go 版：
<pre>/etc/init.d/shadowsocks-go start | stop | restart | status</pre>

Shadowsocks-libev 版：
<pre>/etc/init.d/shadowsocks-libev start | stop | restart | status</pre>

各版本默认配置文件  
Shadowsocks-Python 版：
<pre>/etc/shadowsocks-python/config.json</pre>

ShadowsocksR 版：
<pre>/etc/shadowsocks-r/config.json</pre>

Shadowsocks-Go 版：
<pre>/etc/shadowsocks-go/config.json</pre>

Shadowsocks-libev 版：
<pre>/etc/shadowsocks-libev/config.json</pre>


## 客户端使用教程请参考：  
* [Windows 下安装配置 Shadowsocks 使用教程](2-windows-setup-guide-cn.md)

* [macOS 下安装配置 Shadowsocks 使用教程](3-macos-setup-guide-cn.md)

* [iOS 下安装配置 Shadowsocks 使用教程](4-ios-setup-guide-cn.md)

* [Android 下安装配置 Shadowsocks 使用教程](5-android-setup-guide-cn.md)

* [Linux 下安装配置 Shadowsocks 使用教程](6-linux-setup-guide-cn.md)

* [Firefox 设置教程](7-1-firefox-setup-guide-cn.md)

* [Chrome 设置教程](7-2-chrome-setup-guide-cn.md)
