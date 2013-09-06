---
layout: post
title: "代理系列1-GoAgent"
date: 2013-08-28 23:26
comments: true
categories: proxy,代理,科学上网
---

用gae首先需要一个googleappengineer账号,在 https://appengine.google.com/ 
申请账号可能需要翻墙，可以临时使用在线代理、自由门、tor、免费vpn等等手段先翻墙获取账号。

然后就是下载goagent了，在google搜索可以搜到下载页和安装说明。
mac用户推荐直接下载GoAgentX，这个可以方便的部署服务端和启动客户端。并且有相关说明设置系统pac代理，简单快捷。

访问https网站需要导入证书，不过据说可能会遭受中间人攻击，先用着吧，等报道有中间人攻击了再说。

chrome插件switchSharp安装后会在浏览器地址栏后面有个一个配置和切换模式的小按钮，按说明导入在线配置，然后换成自动切换模式就可以穿大部分的墙了。 mac如果设置了全局代理，用系统代理也差不多够用了。当然switchSharp的智能切换在遇到没有在gfw.list里面的网站时手动添加是很好用的。

我没有使用goagentx，而是写了一个mac的自启动脚本，命名为 me.proxy.goagent.plist 放在~/Library/LaunchAgents下面。

	<?xml version="1.0" encoding="UTF-8"?>
	<!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN"
        "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
	<plist version="1.0">
		<dict>
	        <key>Label</key>
	        <string>me.proxy.goagent</string>
	        <key>ProgramArguments</key>
	        <array>
		<string>python</string>
		<string>/Users/herosea/Dropbox/proxy/goagent/local/proxy.py</string>
	        </array>
	        <key>RunAtLoad</key>
	        <true/>
		<key>WorkingDirectory</key>
		<string>/tmp/goagent</string>
		<key>StandardErrorPath</key>
		<string>/tmp/goagent.log</string>
		<key>StandardOutPath</key>
		<string>/tmp/goagent.log</string>
	</dict>
	</plist>

脚本会随系统启动。可以手动运行命令加载运行。

* 加载：launchctl load -w ~/Library/LaunchAgents/me.proxy.goagent.plist
* 启动：launchctl start me.proxy.goagent
* 停止：launchctl stop me.proxy.goagent  #貌似停不了
* 卸载：launchctl unload ~/Library/LaunchAgents/me.proxy.goagent.plist