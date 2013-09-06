---
layout: post
title: "代理系列2-shadowsocks"
date: 2013-08-30 22:17
comments: true
categories: 科学上网,翻墙
---
shadowsocks是一个可自由部署的优秀代理服务，需要自己有独立的vps运行服务端。shadowsocks源代码在github上，有python、go、nodejs等等各种语言的版本，协议通用。

如果要使用更保密的通讯协议，客户端和服务器都需要额外安装加密库，新手不推荐安装，如果对保密性要求高则推荐安装。

按照官方教程部署服务端，客户端mac下推荐goagentX的shadowsocks模式。

这里给出mac下的示例自启动文件。 ~/Library/LaunchAgents/me.proxy.shadowsocks.plist

	<?xml version="1.0" encoding="UTF-8"?>
	<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
	<plist version="1.0">
	<dict>
		<key>Label</key>
		<string>me.proxy.shadowsocks</string>
		<key>ProgramArguments</key>
		<array>
			<string>/usr/local/bin/sslocal</string>
			<string>-c</string>
			<string>/Users/herosea/Dropbox/proxy/shadowsocks/config.json</string>
		</array>
		<key>RunAtLoad</key>
		<true/>
		<key>UserName</key>
		<string>herosea</string>
		<key>KeepAlive</key>
		<true/>
		<key>WorkingDirectory</key>
		<string>/tmp/shadowsocks</string>
		<key>StandardErrorPath</key>
		<string>/tmp/shadowsocks.log</string>
		<key>StandardOutPath</key>
		<string>/tmp/shadowsocks.log</string>
	</dict>
	</plist>

和goagent一样，可以加载、卸载、启动和停止。

我是把这些plist文件都放置在dropbox的一个目录下，然后链接到 ~/Library/LaunchAgents 目录下的