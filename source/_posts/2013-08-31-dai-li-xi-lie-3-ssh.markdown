---
layout: post
title: "代理系列3-ssh"
date: 2013-08-30 22:46
comments: true
categories: 
---
测
	<?xml version="1.0" encoding="UTF-8"?>
	<!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN"
	        "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
	<plist version="1.0">
	<dict>
	        <key>Label</key>
	        <string>me.proxy.chudong</string>
	        <key>ProgramArguments</key>
	        <array>
		<string>/usr/local/bin/autossh</string>
		<string>-M</string>
		<string>7071</string>
		<string>-qTfnN</string>
		<string>-D</string>
		<string>7070</string>
		<string>-p</string>
		<string>23555</string>
		<string>username@address</string>
	        </array>
	        <key>RunAtLoad</key>
	        <true/>
		<key>KeepAlive</key>
	      	<true/>
		<key>WorkingDirectory</key>
	        <string>/tmp/chudong</string>
	        <key>StandardErrorPath</key>
	        <string>/tmp/chudong.channel.log</string>
	        <key>StandardOutPath</key>
	        <string>/tmp/chudong.channel.log</string>
	</dict>
	</plist>
	