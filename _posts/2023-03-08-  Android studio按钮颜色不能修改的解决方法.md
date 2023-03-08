---
layout: post
title:  "Android studio按钮颜色不能修改的解决方法"
categories: android
tags:  android
author: HYcracker
---
# Android studio按钮颜色不能修改的解决方法

大家好 我是寒依 
不知道大家在学习Android studio 开发应用的时候有没有遇到过一个问题
就是Button 按钮的背景颜色无法修改的问题。通俗点说就是怎么设置背景颜色它这斯就是始终显示紫色。自己本来在按钮属性中设置啦bankdround 的值可颜色依然没有变化，是不是很难受，那恭喜你，你遇到啦我 我将让你不在难受。
当然我能提出这样一个问题说明我是遇到啦， 好像有点废话啦。
那下面就介绍一下怎么解决。不废话啦直接上教程。看下图

![在这里插入图片描述](https://img-blog.csdnimg.cn/2d5c7537a6424d3ca7f1022974152737.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5a-S5L6d56eR5oqA,size_20,color_FFFFFF,t_70,g_se,x_16)






打开 values 下面的themes.xml  文件  在`    <style name="Theme.MyAppCh5" parent="Theme.MaterialComponents.DayNight.DarkActionBar">`里面parent的值最后面加上     **.Bridge**
即改成
`    <style name="Theme.MyAppCh5" parent="Theme.MaterialComponents.DayNight.DarkActionBar.Bridge">`

这样的就可以随意修改我们的按钮背景颜色啦 想怎么改就怎么改啦 。是不是很简单。遇到问题不要慌 先喝杯茶。打开有搜索栏的工具搜一下看看有没有小伙伴分享解决办法 因为你可以这么想，你能遇到的问题别人肯定在你前面遇到啦。永远相信自己是最幸运的。
分享一下我在学习和使用中的问题 ，希望可以帮助到遇到同样问题的小伙伴。
每天站在镜子前对自己说一遍：一天不学习 ，混身难受。
感谢大家。

