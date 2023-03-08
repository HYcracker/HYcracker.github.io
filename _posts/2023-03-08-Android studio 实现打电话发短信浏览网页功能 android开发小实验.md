---
layout: post
title:  "Android studio 实现打电话发短信浏览网页功能"
categories: android
tags:  android java
author: HYcracker
---
#  Android studio 实现打电话发短信浏览网页功能 android开发小实验
**目标：**
              android studio 实现打电话 发短信 浏览网站的功能
            
先在布局里面定义几个按钮 分别为 
打电话 发短信 浏览网页  三个按钮  ，当我们点击相应的按钮 就能执相应的工作  
先看一下效果图
![在这里插入图片描述](https://img-blog.csdnimg.cn/6cec6895cac64df1b4f4b12e8aa17c77.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASFlKb25lcw==,size_20,color_FFFFFF,t_70,g_se,x_16)
打电话
![在这里插入图片描述](https://img-blog.csdnimg.cn/cbfa8c46d35e4ffbbccbca57cb95b977.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASFlKb25lcw==,size_20,color_FFFFFF,t_70,g_se,x_16)
**发短信**

![在这里插入图片描述](https://img-blog.csdnimg.cn/2c93a507023c45c58adda3cb9aa10461.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASFlKb25lcw==,size_20,color_FFFFFF,t_70,g_se,x_16)
浏览网页 
![在这里插入图片描述](https://img-blog.csdnimg.cn/61ab83b6d8e9428384c615ad2f8e0265.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASFlKb25lcw==,size_20,color_FFFFFF,t_70,g_se,x_16)




布局源码

**activity_call_browser_msg.xml**

```java
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:tools="http://schemas.android.com/tools"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:context=".CallBrowserMsgActivity">
<LinearLayout
        android:orientation="horizontal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        tools:ignore="MissingConstraints">

    <Button
            android:background="@drawable/button_bg"
            android:id="@+id/button1"
            android:textSize="20dp"
            android:layout_weight="1"
            android:text="btunex"
            android:layout_width="match_parent"
            android:layout_height="wrap_content">
    </Button>
    <Button
            android:background="@drawable/button_bg"
            android:id="@+id/call"
            android:textSize="20dp"
            android:layout_weight="1"
            android:text="打电话"
            android:layout_width="match_parent"
            android:layout_height="wrap_content">
    </Button>
    <Button
            android:background="@color/teal_200"
            android:id="@+id/browser"
            android:textSize="20dp"
            android:layout_weight="1"
            android:text="浏览网页"
            android:layout_width="match_parent"
            android:layout_height="wrap_content">
    </Button>
    <Button
            android:background="@color/purple_200"
            android:id="@+id/message"
            android:textSize="20dp"
            android:layout_weight="1"
            android:text="发短信"
            android:layout_width="match_parent"
            android:layout_height="wrap_content">
    </Button>
</LinearLayout>
</androidx.constraintlayout.widget.ConstraintLayout>
```

**活动类**
CallBrowserMsgActivity.java

```java
package com.example.myappch5;
import android.content.Intent;
import android.net.Uri;
import android.view.View;
import android.widget.Button;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
public class CallBrowserMsgActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_call_browser_msg);
//
        Button but = findViewById(R.id.button1);
        but.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Intent intent = new Intent("com.example.myappch5.ACTION_START");
                intent.addCategory("com.example.myappch5.HY_CATEGRORY");
                startActivity(intent);
            }
        });
        // 调用接口打电话
        Button call = findViewById(R.id.call);  // 获取控件
        call.setOnClickListener(new View.OnClickListener() {    //设置监听
            @Override
            public void onClick(View view) {
                Intent intent = new Intent();
                intent.setAction(Intent.ACTION_DIAL);  // 调用电话接口
                intent.setData(Uri.parse("tel:100000"));
                startActivity(intent);
            }
        });
        // 调用接口发短信
        Button Msg = findViewById(R.id.message);
        Msg.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Intent intent = new Intent();
                intent.setAction(Intent.ACTION_SENDTO);  // 调用短信接口
                intent.setData(Uri.parse("smsto:100000"));
                intent.putExtra("msg_boddy","I LOVE YOU");
                startActivity(intent);
            }
        });
        // 调用接口浏览网页
        Button brow = findViewById(R.id.browser);
        brow.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Intent intent = new Intent();
                intent.setAction(Intent.ACTION_VIEW);    // 调用浏览网页接口
                intent.setData(Uri.parse("http://www.baidu.com"));
                startActivity(intent);
            }
        });
    }
}
```
设置运行页面

**AndroidManifest.xml**

```java
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
          package="com.example.myappch5">

    <application
            android:allowBackup="true"
            android:icon="@mipmap/ic_launcher"
            android:label="@string/app_name"
            android:roundIcon="@mipmap/ic_launcher_round"
            android:supportsRtl="true"
            android:theme="@style/Theme.MyAppCh5">
        <activity
                android:name=".CallBrowserMsgActivity"
                android:exported="true">
            <intent-filter>
                <action android:name="com.example.myappch5.ACTION_START"/>

                <category android:name="com.example.myappch5.HY_CATEGRORY"/>

                <action android:name="android.intent.action.MAIN"/>

                <category android:name="android.intent.category.LAUNCHER"/>
            </intent-filter>
        </activity>
    </application>

</manifest>
```
