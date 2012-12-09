---
layout: post
title: "ubuntu安装记录"
date: 2012-12-09 17:16
comments: true
categories: [ubuntu,study,linux]
---

拷贝前一个系统用户下的文件，脚本配置，svn配置，maven配置到新系统

###固态硬盘优化（机械硬盘可以参考）###
* 安装[profile-sync-daemon](http://ubuntuforums.org/showthread.php?t=1921800)将浏览器临时文件放入缓存中 
* 修改fstab文件挂载参数
* /etc/rc.local 中 添加 `echo /sys/block/sda/queue/scheduler`,优化固态硬盘

###32位兼容包###
    sudo apt-get install ia32-libs #32位兼容包
###安装wine（要使用vpn或者代理）###
    sudo add-apt-repository ppa:ubuntu-wine/ppa
    sudo apt-get update
    sudo apt-get install wine1.5
####wine扩展####
    sudo apt-get install wine-gecko1.8
    sudo apt-get install wine-mono0.0.8
###QQ###
参考[longene qq](http://www.longene.org/forum/viewtopic.php?f=6&t=4700)
###新浪微薄###
    sudo apt-get install gwibber-service-sina #新浪微博
###gim图像####
    sudo apt-get install gimp
安装 digiKan 处理相机图片（处理单反相机的图片）
###skype###
参考[https://help.ubuntu.com/community/Skype](https://help.ubuntu.com/community/Skype)
    sudo add-apt-repository "deb http://archive.canonical.com/ $(lsb_release -sc) partner"
    sudo apt-get update &&     sudo apt-get install skype
###安装虾米###
[详细](http://forum.ubuntu.org.cn/viewtopic.php?f=74&t=380947)
    sudo apt-add-repository ppa:timxx/xmradio
    sudo apt-get update
    sudo apt-get install xmradio
###安装kugoo###
[详细](http://forum.ubuntu.org.cn/viewtopic.php?f=73&t=382232)
###安装小企鹅输入法###
    sudo apt-get remove ibus-* -y
    sudo apt-get  install  fcitx-pinyin  fcitx-table-wbpy im-switch -y
    sudo im-switch -s fcitx  -z default -y
###安装mac主题###
参考[Make ubuntu become Mac Lion](http://blog.csdn.net/liuyanzhi08/article/details/7748903)
    sudo add-apt-repository ppa:tualatrix/ppa -y
    sudo add-apt-repository ppa:noobslab/themes -y
    sudo apt-get update
    sudo apt-get install mac-os-lion-cursors mac-os-lion-icons mac-os-lion-theme ubuntu-tweak cairo-dock -y
使用ubuntu-tweak添加软件源
###右键打开命令行###
    sudo apt-get install nautilus-open-terminal #右键打开命令行
将自建脚本放入bin目录中并加入.bashrc文件中 PATH=$PATH:~/bin
###安装jdk###
    sudo apt-get install openjdk-6-jdk openjdk-6-source openjdk-6-doc -y
###安装mysql和mysql工具###
    sudo apt-get install mysql-server -y
    sudo apt-get install mysql-workbench -y
安装受限程序、安装filezila、添加chrome源，安装chrome。
导入switch sharp 配置。
###安装svn###
eclipse中使用的是1.7版本，ubuntu的比较旧，需要使用额外的源。
    sudo apt-add-repository ppa:dominik-stadler/subversion-1.7 -y
    sudo apt-get update -y
    sudo apt-get install libsvn-java -y
    sudo apt-get install subversion -y
下载eclipse，安装maven，svn插件
###安装maven、vim、graphicsmagick（图片压缩）、memcached和git###
    sudo apt-get install maven -y
    sudo apt-get install git -y
    sudo apt-get install vim
    sudo apt-get install memcached
    sudo apt-get install graphicsmagick
###路由跟踪###
    sudo apt-get install traceroute #路由跟踪
###ssh自动交互（可用于本地shell自动交互）###
    sudo apt-get install expect #ssh交互自动输入密码
    sudo apt-get install autossh #可带密码的ssh链接，并会自动重连
###dnsmasq本地dns优化###
[参考](http://www.snowhawkyrf.name/2012/05/ubuntu-1204dnsmasqdnsmasq.html)
####假如你想要使用自己的dnsmasq配置####
* 请先注释掉：`sudo vi /etc/NetworkManager/NetworkManager.conf`里面的`dns=dnsmasq`
* 然后重启NM：`sudo restart network-manager`
* 之后重启你事先设置好的dnsmasq，你的配置将生效
      sudo apt-get install dnsmasq
      sudo service dnsmasq restart
* 可以用dig google.com测试，如果SERVER是127.0.0.1即可
####自己的dns配置####
修改*/etc/dnsmasq.conf*添加如下
      address '/s.nexttv.com.tw/203.69.138.24'
      address '/api.tcloudapp.cn/101.68.210.11'
      address '/web.tcloudapp.cn/101.68.210.11'
      server '/google.com/8.8.8.8'
      server '/appspot.com/8.8.8.8'
      server '/facebook.com/8.8.8.8'
      server '/fbcdn.net/8.8.8.8'
      server '/twitter.com/8.8.8.8'
      server '/youtube.com/8.8.8.8'
      server '/ytimg.com/8.8.8.8'
      server '/imageshack.us/8.8.8.8'
      server '/books.com.tw/8.8.8.8'
      server '/book.com.tw/8.8.8.8'
      server '/nownews.com/8.8.8.8'
      server '/gov.tw/8.8.8.8'
      server '/google.com.hk/8.8.8.8'
      server '/vimeo.com/8.8.8.8'
      server '/fbsbx.com/8.8.8.8'
      server '/boxun.com/8.8.8.8'
      server '/appengine.google.com/221.12.1.227'

###Nexus7###
  * `sudo apt-get install libmtp-dev`
  * [AUTOMOUNT NEXUS 7 IN MTP MODE](http://bernaerts.dyndns.org/linux/247-ubuntu-automount-nexus7-mtp)
  * [Root nexus 7 with ubuntu linux（测试未成功）](http://bernaerts.dyndns.org/android/246-ubuntu-root-nexus-7-tablet)
###ruby###
参考[ruby-china的wiki](http://ruby-china.org/wiki/install_ruby_guide)
####octopress（个人日志）####
`git remote add octopress https://github.com/imathis/octopress.git` #不能找到octopress仓库时执行
