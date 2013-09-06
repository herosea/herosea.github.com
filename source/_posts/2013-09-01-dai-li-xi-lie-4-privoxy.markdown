---
layout: post
title: "代理系列4-privoxy"
date: 2013-08-30 22:46
comments: true
categories: 
---


	<?xml version="1.0" encoding="UTF-8"?>
	<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
	<plist version="1.0">
	<dict>
	    <key>Label</key>
	    <string>me.proxy.privoxy</string>
	    <key>ProgramArguments</key>
	    <array>
	        <string>/usr/local/sbin/privoxy</string>
	        <string>--no-daemon</string>
	        <string>/usr/local/etc/privoxy/config</string>
	    </array>
	    <key>RunAtLoad</key>
	    <true/>
	    <key>KeepAlive</key>
	    <true/>
	    <key>WorkingDirectory</key>
	    <string>/tmp/privoxy</string>
	    <key>StandardErrorPath</key>
	    <string>/tmp/privoxy.log</string>
	    <key>StandardOutPath</key>
	    <string>/tmp/privoxy.log</string>
	</dict>
	</plist>
	