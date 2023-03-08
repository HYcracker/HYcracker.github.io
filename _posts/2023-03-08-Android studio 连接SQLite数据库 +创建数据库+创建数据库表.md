---
layout: post
title:  "Android studio 连接SQLite数据库 +创建数据库+创建数据库表"
categories: android
tags:  android java   SQLite
author: HYcracker
---
# Android studio 之数据库的使用 连接创建SQLite   


大家好，欢迎来到寒依。
**相信看啦我的教程    当老师问你在学习Android studio 数据库使用过程中遇到什么困难，分享一下你的感悟和解决方法 的时候，你可以直接大胆的说出来： “老师我没有遇到问题，看啦寒依的教程 畅行无阻”**

我使用的工具是 Intillij idea 专业版 但是方法都一样 因为 Intellij idea 是Android studio 的祖宗  方法都是一样

Intellij idea专业版 yyds

相信你能看到这篇文章 肯定是在学习Android studio 连接数据库时遇到啦问题。哪恭喜你，你今生都很幸运，不然也不可能你遇到我，哪下面呢就让我给下面带来最精彩都得教程。相信你也会觉得非常的简单。
如果你是大佬就单纯想来看看我，那就当我没说，还请大佬来指点指点，必将感激不敬。
不废话啦， 傻瓜式教程马上开始。小板凳坐好啦，下面才是学习Android 开发正确的打开方式。







SQLite 为Android studio 自带   无需下载

Android studio 接数据库(SQLite)，创建数据库

第一步  新建一个新的Android 项目  不会看图 
![在这里插入图片描述](https://img-blog.csdnimg.cn/77665d72980344b7bf8667446faeb896.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5a-S5L6d56eR5oqA,size_20,color_FFFFFF,t_70,g_se,x_16)
新建Android    选择一个空的（Empty Activity）项目 接着点击 下一步
![在这里插入图片描述](https://img-blog.csdnimg.cn/343ba3a696294b74969a7708df660914.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5a-S5L6d56eR5oqA,size_20,color_FFFFFF,t_70,g_se,x_16)
Name 自己取就ok      语言Language 选择 java   点击完成 
![在这里插入图片描述](https://img-blog.csdnimg.cn/e4f594f6a2d04c95add62ff5f8e95fa6.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5a-S5L6d56eR5oqA,size_20,color_FFFFFF,t_70,g_se,x_16)

 接下来才是最精彩的时刻  竖起小耳朵 张大眼睛盯好啦   （新建一个类  ）
![在这里插入图片描述](https://img-blog.csdnimg.cn/f31274e6540f45cf962ce8bcb1a73ea2.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5a-S5L6d56eR5oqA,size_20,color_FFFFFF,t_70,g_se,x_16)
DbContect.java

```java
package com.example.dbproject;
import android.content.Context;
import android.database.sqlite.SQLiteDatabase;
import android.database.sqlite.SQLiteOpenHelper;
import android.widget.Toast;
public class DbContect extends SQLiteOpenHelper {
    private static final int VERSION=1;
    private static final String DBNAME="Users.db";   //  创建数据库名叫 Users
    private Context mContext;

    public DbContect(Context context){
        super(context,DBNAME,null,VERSION);
        mContext = context;
    }
    //创建数据库
    public void onCreate(SQLiteDatabase db){
        //创建密码表  pwd_tb
        db.execSQL("create table pwd_tb (pwd varchar(20) primary key)");
        //创建收入表    user_tb
        db.execSQL("create table user_tb(_id integer primary key autoincrement, money decimal," +
                " time varchar(10),type varchar(10),handler varchar(100),mark varchar(200))");
    }
    //数据库版本更新
    public void onUpgrade(SQLiteDatabase db,int oldVersion,int newVersion)
    {
        db.execSQL("drop table if exists pwd_tb");
        db.execSQL("drop table if exists user_tb");
        onCreate(db);
    }


}

```
再来到 activate_main.xml  
![在这里插入图片描述](https://img-blog.csdnimg.cn/4ec2d754e90c4814b57bb04d23e411b6.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5a-S5L6d56eR5oqA,size_20,color_FFFFFF,t_70,g_se,x_16)
activaty_main.xml  

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:tools="http://schemas.android.com/tools"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:context=".MainActivity">
    <LinearLayout android:layout_width="match_parent"
                  android:layout_height="match_parent">
        <Button
                android:id="@+id/create"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:background="#00BCD4"
                android:textSize="22dp"
                android:text="点击创建Users数据库"
        >
        </Button>
    </LinearLayout>

</androidx.constraintlayout.widget.ConstraintLayout>
```
再打开 MainActivaty .java 

MainActivaty .java 

```java
package com.example.dbproject;

import android.database.sqlite.SQLiteDatabase;
import android.view.View;
import android.widget.Button;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;

public class MainActivity extends AppCompatActivity {
    DbContect helper;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

            helper=new DbContect(  MainActivity.this);
            Button btn=findViewById(R.id.create);
            btn.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View V) {
                    SQLiteDatabase db=helper.getWritableDatabase();
                }
            });
        }
    }
```
 好啦 代码完事 刚才是最精彩的时刻 现在到啦激动人心的时候 
 测试一下是否成功 和数据可视化  精彩即将呈现
运行项目  
![在这里插入图片描述](https://img-blog.csdnimg.cn/d4a1462d540d4a3ba6239bfb40cf331d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5a-S5L6d56eR5oqA,size_20,color_FFFFFF,t_70,g_se,x_16)
点开模拟器 小手机
![在这里插入图片描述](https://img-blog.csdnimg.cn/62fc5157f15d494facf1f29e34133d56.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5a-S5L6d56eR5oqA,size_20,color_FFFFFF,t_70,g_se,x_16)
别急 还没完事 结果还没出呢  再来到
![在这里插入图片描述](https://img-blog.csdnimg.cn/3edb8bff46cf4d4d933f26f5e4b8987b.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5a-S5L6d56eR5oqA,size_20,color_FFFFFF,t_70,g_se,x_16)
 此时在右下角会跳出一个东西
 
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/157c3d30fb3e45898898cd8db4c80a07.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5a-S5L6d56eR5oqA,size_20,color_FFFFFF,t_70,g_se,x_16)


  到第二个data 下面找到  
  直接看图吧 不想打字啦
  
![在这里插入图片描述](https://img-blog.csdnimg.cn/cb48088aec9648a1a529c0d880b81de3.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5a-S5L6d56eR5oqA,size_20,color_FFFFFF,t_70,g_se,x_16)  Users.db 就是我们创建的数据库  
接下来可视化  
方法一 ：
![在这里插入图片描述](https://img-blog.csdnimg.cn/786de426054147768855ea3da81a9d49.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5a-S5L6d56eR5oqA,size_20,color_FFFFFF,t_70,g_se,x_16)
![在这里插入图片描述](https://img-blog.csdnimg.cn/5ac86c45f38c4f129fe4f58ad619f3f3.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5a-S5L6d56eR5oqA,size_20,color_FFFFFF,t_70,g_se,x_16)

嘿嘿 出来啦 激动不激动 

![在这里插入图片描述](https://img-blog.csdnimg.cn/b42e2ae6953e4f5080687650c1a69429.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5a-S5L6d56eR5oqA,size_20,color_FFFFFF,t_70,g_se,x_16)

可视化方式二：
将数据库保持下来  用其他的可视化工具打开 直接将 保存的 Users.db 托到  Navicat  
![在这里插入图片描述](https://img-blog.csdnimg.cn/7b60939eb362499bad5cc0bedbebe2e3.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5a-S5L6d56eR5oqA,size_20,color_FFFFFF,t_70,g_se,x_16)
直接托进去 就ok 
![在这里插入图片描述](https://img-blog.csdnimg.cn/c2a4d8d553764a5a907c843fce766524.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5a-S5L6d56eR5oqA,size_20,color_FFFFFF,t_70,g_se,x_16)

**好啦 老师再敢问你学习Android studio数据库的使用中有没有什么困难的时候就可以很有底气的跟她说 “老师我没有遇到问题 ，学习中畅行无阻”**


教程完毕  欢迎 投稿提问 
也欢迎大佬指导
谢谢大家  ！
