---
layout: post
title:  "android studio实现小吃商城，android课程设设计"
categories: android 
tags:  idea android java
author: HYcracker
---
# Android移动开发 课程设计
# 项目名称：小吃云商城（云小吃app）
<font color=red size=5>源码文末获取</font>
@[TOC]
# 1．任务要求
## 1.1 设计任务
本门课程的目的是训练运用移动开发技术，独立设计和开发APP的能力。本课程设计在完成移动开发技术等基础课程之后，集中一周时间让学生选择特定设计方案与内容独立完成Android APP设计与编程工作，以巩固和提高相关语法和相关应用技术。
## 1.2 设计要求
设计简单的APP。APP中至少包括5个以上的Activity页面。要求有数据库连接，并进行简单的交互。至少包括以下控件和元素：文本框、按钮、下拉列表、单选按钮、复选按钮、文本、ListView或GridView等。







# 2．APP功能
该APP包含个10个Activity，每个Activity的功能（附运行图）及写Activity的操作说明。
## 2.1、登录页面
登录活动的运行结果如图2.1所示。在文本框里填写密码后，如果账号与数据库账号匹配，对应的密码与数据库密码相匹配，则进入主页面。否则，提示密码用户名或者密码错误。
![!\[在这里插入图片描述\](https://img-blog.csdnimg.cn/1d8bc16](https://img-blog.csdnimg.cn/b5b6932092bf4bbf9033ff38dde7c8fb.png)
cdcfa4ce080c3fc40281a9bf8.png)


## 2.2、注册页面

用户点击新用户按钮来到软件注册页面，用户输入自己的注册信息，
当输入的用户名小于4位数时 将弹出提示用户名必须大于4 请重新输入，如图2.2-1
当用户输入的手机号步符合手机号标准时将弹出提示请输入11位手机号，如图2.2-2
当输入的密码少于6位数时将弹出提示密码为6-12位。同时将密码归空，如图2.2-3
当选择性别后将弹出提示所选中的性别如 图2.2-4
选择城市的方式为下拉列表，选中即可见 如 图2.2-5、 
当信息已在数据库中已经注册过提示用户已存在如 图2.2-6
后端程序将对比两次密码是否一致 一致则才能注册成功

![在这里插入图片描述](https://img-blog.csdnimg.cn/b3cc4d3abd8a406a9ec5fd3de921b20a.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/a845b5efd235451589ee8e43ee86cb2c.png)

当输入信息正确后点击注册按钮 ，后端代码将注册信息写入数据库user表储存。用来记录用户信息和登录，浏览，下单操作。注册成功后将弹出提示注册册成功同时直接跳到登录页面如 图2.2-7
![在这里插入图片描述](https://img-blog.csdnimg.cn/fc1ec060aa404a29a9b9dbf80f918497.png)
## 2.3、密码修改页面
当用户忘记自己的登录密码可以点击忘记密码按钮前往密码修改页面进行密码修改操作2.3-1
 	如果输入的信息在数据库中，并且用户输入符合的信息修改 密码修改成功后将弹出提示 修改成功同时自动跳回到登录页面 如图 2.3-2
 	![在这里插入图片描述](https://img-blog.csdnimg.cn/170d002c6f6e4cb0af9f36000e3cb20e.png)
如果修改用户步存在 弹出提示 用户名手机不匹配修改失败如图 2.3-3
在输入修改信息的时候页需要验证两次密码 如果账号存在输入的密码确认正确 则才能注册成功，如果两次密码不一致，则弹出提示两次密码不一致 修改失败 如图 2.3 -4 
![在这里插入图片描述](https://img-blog.csdnimg.cn/1db6915338d943c2960f4147e9b4f722.png)
## 2.4、app 欢迎界面 
当我们打开app 并非直接进入app 首页 而是先来到app 的欢迎页面。
这时一个app 最基本要有的功能。App欢迎页面如图 2.4-1
![在这里插入图片描述](https://img-blog.csdnimg.cn/1ccde59b3f994d0daf8d983022cc8177.png)
## 2.5、app首页

App首页 有小吃搜索功能 有广告轮播图 有小吃推荐序列 首页如图 2.5-1
可以点击浏览商品 并将收藏小吃和将小吃加入购物车 浏览完可以返回到上一页如图 2.5-2
![在这里插入图片描述](https://img-blog.csdnimg.cn/8300063f77ca48ac92415c8b04532299.png)
## 2.6、小吃点分类点菜页 
点击点菜页之后可以来到 分类点菜页面。 
页面给将小吃按照城市分类，将全国各地有名小吃， 以列表的形式分类展现在用户面前。用户可以随意点击自己喜爱的城市的小吃， 页可以点击小吃进行详情浏览， 或直接点击有加号并将其加入到购入车内方便统一下单 。小吃分类浏览页面如图 2.6-1、2.6-3

![在这里插入图片描述](https://img-blog.csdnimg.cn/1b7054330e25421b801de81130e533f3.png)
## 2.7、购物车页面及功能
在购物车系统页面如果监测到购物查没有小吃上坪则显示 显示空空页的下单提示页 如图2.7-1
将小吃商品添加到购物车后，在购物车系统页面监测到有小吃数据，可以通过点击小吃页面上的 加号 和减号 改变小吃下单数量 ，购物车后端程序将自动计算出购物车的商品小吃价格合计并显示在页面上。 2.7-2
![在这里插入图片描述](https://img-blog.csdnimg.cn/e1dc60dc19d54a629666679da4ec4a74.png)
## 2.8、删除购物车页面下
进入购物车页面可以看到自己添加的小吃数据，接下来可以删除购物车数据，点击右下角的删除按钮将弹出弹窗提示删除确认，点击确认删除后可以删除购物车数据，当数据删除成功后，系统将弹出提示已清空数据库。然后回到空购物车页面。如图 2.8-1删除购物车数据确认图示   、2.8-2 购物车删除完成提示返回空页面图示
![在这里插入图片描述](https://img-blog.csdnimg.cn/a1ad6b102fdd422192f7437f7760c53c.png)



## 2.9、购物车单下单付款页面 
进入购物车页面可以清晰的看到已经添加到购物车的数据，后端将计算出所有商品的价格合计。当用户点击用户下单支付后会跳出支付确认页面。在支付确认页面 用户可以添加备注信息，选择支付方式进行支付，app 将提供多种支付方式供用户选择。当用户支付成功后，系统后端程序将下单数据逐条添加到数据库中，作为用户下单凭据，和数据的保存方便，后续查看， 修改，删除等操作。同时下单成功后下单完成的数据也将从购物车数据中清楚。页面将提示下单成功。并且回到未下单或者空购物车显示页面给。
支付确认图如图 2.9-1   支付成功后提示与跳转页面给图示如图 2.9-2
![在这里插入图片描述](https://img-blog.csdnimg.cn/309dc0785c3a4db897a4fb51fb981f23.png)

## 2.10、“我的”个人中心页面
个人中心页面。个人中心是一个app必须应该具备的页面。在我们的云小吃app来到个人中心页面可以看到自己的账号信息（用户名，和id,头像信息）。在我的页面有查看订单，查看待付款，查看待评价，查看退款、支付设置地址管理修改地址通用设置 、退出登录 等功能。“我的”页面如图 2.10-1
在“我的”页面，如果你是未登录状态。将不能看到自己的个人信息，页面账号信息处将提示为未登录。如果点击页面上的功能入口后，后端程序将先判断当前是否为账号登录状态，如果未登录状态，系统将提示 当前未登录 并且不能进入查看相关内容。因为点击功能模块是查看和操作与账号相关的内容，未登录状态系统找不到要执行用户的操作，就将提示“未登录”。如图2.10-2
如果用户已经登录后将查看到自己的信息内容。后端程序将登录信息持久化并返回islogin 当需要执行操作时会先判断当前是否为登录状态。在登录状态下用户点击头像是将弹出提示：“已登录”。并能点击相关功能入口，查看和操作相关数据内容。
登录状态如图 2.10-3 。登录后可以点击页面相关功能入口查看相关和操作相关内容，如图2.10-4点击我的订单页面。登录成功后点击退出登录将退回到未登录状态页面。
![在这里插入图片描述](https://img-blog.csdnimg.cn/386e446a7de54e2399af3ce7201e8570.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/9e24328c57bc436cb80839ac4f1bdf4b.png)

## 2.11、我的订单页面
我的订单页面是查看我们下单成功后的小吃页面。当用户点击“我的订单”后后端程序将根据当前登录用户的账号查询数据库中该用户的订单记录显示到订单页面上。顶订单页面可查看订单信息。搜索查找订单信息。可以对订单进行相关删除、退款等管理操作。在订单页面点击左上角返回按钮将返回到上一个页面。订单页面如图 2.11-1
![在这里插入图片描述](https://img-blog.csdnimg.cn/7215d92c1b304e7fba61effa7838f24e.png)
## 2.12、地址管理页面
在“我的”页面点击地址管理将跳转到地址管理页面，后端程序根据当前用户名查询用户的地址信息并将用户的地址信息显示到地址管理页面。用户可以点击地址信息进行地址管理的修改和删除操作。在地址管理页面点击添加地址将进入地址添加页面。
地址管理页面如图：2.12-1，点击地址跳转删除确认如图 2.12-2.

![在这里插入图片描述](https://img-blog.csdnimg.cn/c79062e907204811afef4b4ba6939be6.png)


## 2.13、添加地址页面
在地址管理页面点击添加地址进入地址增加页面。用户在地址添加页面输入地址信息后，点击添加按钮，后端程序将地址信息添加到数据库地址表（address）中存储，添加成功后页面将弹出提示“添加成功”并返回到查看页面。方便地址的管理。
添加地址页面如图 2.13-1，地址添加成功如图 2.13-2。

![在这里插入图片描述](https://img-blog.csdnimg.cn/99acd2b7800f4e90b56b0a865ef0eb61.png)
## 2.14、删除地址页面
 在地址管理中点击相应的低画质 可以进入到删除地址界面。用户可以点击删除确认 删除自己不用的地址信息。后台将根据地址id 删除对应的数据库中的内容。
地址删除如图 2.14-1  删除后成功提示 如图 2.14-2.
![在这里插入图片描述](https://img-blog.csdnimg.cn/5a6de46b12de47bc98dc933b1d2eb128.png)
# 3．数据库设计
Sqlite数据库名为OrderStore.db。共有3个表，表名分别为：user(用户数据表)、orders（订单数据面表）、address（地址数据表）。
## 3.1、user表
usert表记录用户注册信息，表结构如下表3.1所示。
![在这里插入图片描述](https://img-blog.csdnimg.cn/643a5b942fd1405ea6386966216f47c0.png)
## 3.2、orders表
orders表记录用户订单信息，表结构如图3.2-1
![在这里插入图片描述](https://img-blog.csdnimg.cn/6c2109b5b2704945bd9de2e9bb205029.png)
## 3.3、address表
address表记录用户地址信息。表结构如图3.3-1
![在这里插入图片描述](https://img-blog.csdnimg.cn/955ece50b11c49e3ae128cf5fb0a409f.png)
# 4．特色创意
## 5.1、清晰的程序结构
![在这里插入图片描述](https://img-blog.csdnimg.cn/8925ffd656aa4f9ab4621ad6fd7c384c.png)


## 5.2、轮播图
主要代码
乱播控件布局
```xml
<ViewFlipper
        android:id="@+id/flipper"
        android:layout_width="match_parent"
        android:layout_height="200dp"
        android:outAnimation="@anim/left_in"
        android:inAnimation="@anim/right_out"
        tools:ignore="MissingConstraints">
    <ImageView
            android:id="@+id/imageView1"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:background="#ffffff"
            android:src="@drawable/lunbotu3" />

    <ImageView
            android:id="@+id/imageView2"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:background="#ffffff"
            android:src="@mipmap/orderguanggao" />
    <ImageView
            android:id="@+id/imageView3"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:background="#ffffff"
            android:src="@drawable/sack" />
    <ImageView
            android:id="@+id/imageView4"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:background="#ffffff"
            android:src="@drawable/lunbotu2" />
</ViewFlipper>
```

Java中的主要代码
```java
ViewFlipper flipper;
flipper = findViewById(R.id.flipper);
flipper.startFlipping();
```
资源文件
设置轮播效果进出方向及时间

```xml
left_in.xml
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate
            android:duration="1000"
            android:fromXDelta="100%p"
            android:toXDelta="0" />

</set>
```
```xml
right_out.xml
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate
            android:duration="1000"
            android:fromXDelta="0"
            android:toXDelta="-100%p"/>

</set>
```

## 5.3、ui设计
![在这里插入图片描述](https://img-blog.csdnimg.cn/e3ac8275b1fa4f6fab4d206e9632b199.png)



## 5.4、登录持久化

主要代码

```java
* 登录状态
 */
private static boolean isLogin;

public static MyApplication getInstance() {
    return appContext;
}

public static List<Snack> getCartSnacks() {
    return cartSnacks;
}

public static User getUser() {
    return user;
}

public static void setUser(User user) {
    MyApplication.user = user;
}

/**
 * 是否登录
 *
 * @return <tt>true</tt>: 已经登录, <tt>false</tt>: 未登录
 */
public static boolean isLogin() {
    return isLogin;
}

public static void isLogin(boolean isLogin) {
    MyApplication.isLogin = isLogin;
}


// 登录运行 
private void checkLogin() {
    // 检查持久化的数据
    if (UserDao.isLogin()) {
        // 已登录
        MyApplication.isLogin(true);
        MyApplication.setUser(UserDao.getUser());
    } else {
        // 未登录
        MyApplication.isLogin(false);
        MyApplication.setUser(null);
    }
}
```

## 5.5、清晰的层次图如图 5.5-1

										图5.6-1、层次图
![在这里插入图片描述](https://img-blog.csdnimg.cn/21ac106738764af4b275608c0d46cb91.png)

## 5.6、数据库ER图如图5.7-1


![图5.6-1数据库ER图](https://img-blog.csdnimg.cn/ad1b731d3a164f64879d2aa18078cf1c.png)          		图5.6-1数据库ER图

# 5．程序代码
代码太长 我已打包到云端

<font color=red size=5>下载源码



