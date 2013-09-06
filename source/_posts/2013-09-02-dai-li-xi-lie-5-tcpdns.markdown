---
layout: post
title: "代理系列5-tcpdns"
date: 2013-08-30 22:47
comments: true
categories: 
---

	
	<?xml version="1.0" encoding="UTF-8"?>
	<!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN"
	        "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
	<plist version="1.0">
	<dict>
	        <key>Label</key>
	        <string>me.proxy.tcpdns</string>
	        <key>ProgramArguments</key>
	        <array>
		<string>python</string>
		<string>/Users/herosea/Dropbox/proxy/Tcp-DNS-proxy/tcpdns.py</string>
	        </array>
	        <key>RunAtLoad</key>
	        <true/>
		<key>WorkingDirectory</key>
		<string>/tmp/tcpdns</string>
		<key>StandardErrorPath</key>
		<string>/tmp/tcpdns.log</string>
		<key>StandardOutPath</key>
		<string>/tmp/tcpdns.log</string>
	</dict>
	</plist>
	