---
layout: post
title: "rubylearning.com阶段学完纪念"
date: 2012-02-15 21:38
comments: true
categories: ruby,study,总结,学习
---
终于看完了rubylearning上的学习教程了，纪念一下。

ruby的加、减、乘和除都是对象的方法。

变量的作用域可以根据名称来判定，$开头的全局变量，@开头的实例变量（成员变量），@@开头的类变量。  
内置的全局变量？  
本地域？

获取输入 gets.chomp  
ruby的名称 名称有大小写、数字和下划线组成。？  
ruby的方法名规约是驼峰命名法。？  
方法的定义使用def...end，可以的方法后缀有 ！和？。！表明是破坏性方法，会改变消息接收着（ruby中调用方法被称作向对象发消息）。?表明方法是一个询问方法，通常会返回true或则false，但不是一定的，可以返回其他，比如*?.zero*。另外在ruby中除了false和nil之外都表示true（包括''和0）。

ri?
'string'.methods()
比较字符串是否相等和java正好相反，使用 = 比较内容，使用equals?检查是不是同一个对象。  
%w可以把对象转换为数组？  
utf中英文字符占一个字节，使得和asicc码一样。？？
ruby使用所在操作系统的编码
encoding class的使用？ 可以在文件的第一行使用coding=utf-8标识文件使用utf-8编码，如果第一行是 !/bin/bash之类的，可以将标识放到第二行。  
?:和java一样
nil是一个在ruby中表示nothing的对象。  
false和nil的不同是，false是一个?  
ruby的块(block)是一个优秀的语法，使用上他在方法所有的参数最后，使用{}或则 do...end包围，如 {|k, v| puts k + ':' + v}，闭包将会在接受消息的对象中调用，并且可以将参数传到闭包中。在定义方法时使用yeld？调用闭包。

a, b, c = 1, 2, 3, 4 将会给a,b,c依次赋值。首先将1，2，3，4放到一个数组里面，然后赋值给左边的变量。  
ENV.each{|k,v|puts k + ' : " + v}将环境变量打印出来。  
ARGS可以引用命令行参数。  
GetoptLong不是ruby的核心包？需要使用requre引入，是用来解析命令行的配置参数的。  
Range有两种..是闭区间, ...不包含最大的数，如(0..9)表示0到9，（0...9）表示0到8。  
Symbol是一个符号，他总是指向同一个对象？？，在hash中使用的比较多。 :name。 方法和类是Symbol






