---
layout: post
title:  "Jsp实现图书售卖商城 jsp课程设计javaWeb图书商城"
categories: tomcat
tags:  jsp javaweb
author: HYcracker
---
# 前言
记录一下一次简单的课程设计，前台页面是用几个页面再加上自己的修改拼凑而成，后台管理是自己写的。虽然写得简洁，对于作为课程设计的要求已经够用啦。

# 目录
@[TOC](文章目录)








# 《JSP程序设计》课 程 设 计 报 告


课程设计题目：	图书网上商城


# 1.课程设计任务及要求
## 1.1 设计任务
通过本次课程，进一步掌握利用已学的编程知识和编程技巧，通过具体项目的分析、设计和开发，掌握开发web 应用项目过程中所需要的开发方法并熟悉相应开发软件的应用，实现从项目选题、论证、开发、实施等综合应用能力的提高。
## 1.2 设计要求
主要利用Java、JSP、MySQL等技术，结合图像处理技术进行Web应用程序的开发，要求所设计的网站功能完善。通过查阅相关文献与资料，进行开发前的必要准备；掌握软件开发的一般方法和步骤；提高撰写技术文档的能力。

# 2.总体设计
## 2.1 技术可行性
依靠Tomcat服务器建立运行环境，使用IntelliJ IDEA可视化工具进行代码书写和编译文件，使用JSP、MySQL、JS、HTML、CSS、JAVA等技术支持进行实现该系统的建立。
## 2.2 开发环境及工具介绍
### 2.2.1、 编译环境
#### 2.2.1.1、 IntelliJ IDEA 2021.3 
IntelliJ IDEA的每个方面都专门设计用于最大限度地提高开发人员的工强大的静态代码分析和符合人体工程学的设计使开发不仅具有高效性，而且还具有令人愉悦的体验。
在IntelliJ IDEA为您的源代码编制索引之后，它通过在每个上下文中提供相关建议提供了快速而智能的体验：即时和巧妙的代码完成，动态代码分析和可靠的重构工具。
WebStorm 是jetbrains公司旗下一款JavaScript 开发工具。被广大中国JS开发者誉为“Web前端开发神器”、“最强大的HTML5编辑器”、“最智能的JavaScript IDE”等。与IntelliJ IDEA同源，继承了IntelliJ IDEA强大的JS部分的功能。
####   2.2.1.2、 Apache Tomcat v8.0
Tomcat是Apache 软件基金会（Apache Software Foundation）的Jakarta 项目中的一个核心项目，由Apache、Sun 和其他一些公司及个人共同开发而成。由于有了Sun 的参与和支持，最新的Servlet 和JSP 规范总是能在Tomcat 中得到体现，Tomcat 5支持最新的Servlet 2.4 和JSP 2.0 规范。因为Tomcat 技术先进、性能稳定，而且免费，因而深受Java 爱好者的喜爱并得到了部分软件开发商的认可，成为目前比较流行的Web 应用服务器。
Tomcat 服务器是一个免费的开放源代码的Web 应用服务器，属于轻量级应用服务器，在中小型系统和并发访问用户不是很多的场合下被普遍使用，是开发和调试JSP 程序的首选。
#### 2.2.1.3、 mysql-8.0.26-winx64
MySQL是一个关系型数据库管理系统，由瑞典MySQL  AB公司开发，目前属于 Oracle 旗下产品。MySQL 最流行的关系型数据库管理系统，在 WEB 应用方面MySQL是最好的 RDBMS应用软件之一。由于其社区版的性能卓越，搭配 PHP 和 Apache 可组成良好的开发环境。
## 2.3、 编程语言
JSP、HTML、CSS、Javascipt、Java

## 2.4 系统总体设计
### 2.4.1 系统的总体结构图
![在这里插入图片描述](https://img-blog.csdnimg.cn/f7a2d827ed5940d79b4bc4c3e28c18f1.png)

图2.1 网站功能结构图


### 2.4.2 业务流程图
![在这里插入图片描述](https://img-blog.csdnimg.cn/21c49ee38a224839923b351ee7c2bea1.png)


图2.2 用户登陆流程图
![](https://img-blog.csdnimg.cn/5d75caf853f24cb08db251d6be2d2166.png)

图2.3 主页面功能图

![在这里插入图片描述](https://img-blog.csdnimg.cn/351d47d63f5b48fba1992810b55a1b3c.png)

图2.4 管理员页面功能图



# 3.详细设计
## 3.1 网站数据库设计
数据库库（book）中包括：用户信息表（user）、管理员信息表（admin）、书籍信息表（book）、订单信息表（ordercarts）等。以下是数据库中各个表的结构：
表3.1 user信息表
![在这里插入图片描述](https://img-blog.csdnimg.cn/fc6b6ba7b92b4f0aa9b034b5189c3756.png)

表3.2 admin信息表
![在这里插入图片描述](https://img-blog.csdnimg.cn/77a840054132491c9a1f0cf7e7b6b078.png)
表3.3 book信息表
![在这里插入图片描述](https://img-blog.csdnimg.cn/44014066baf14c268ccd1ac2b7f4edeb.png)


表3.4 ordercart信息表
![在这里插入图片描述](https://img-blog.csdnimg.cn/d0eb647b5f4e41c184ed3ee98abff2d3.png)



## 3.2目录和包结构设计
### 3.2.1 用户视图层
用户视图层由jSP页面组成，其中主界面为index.jsp文件, 通过框架引入header.jsp(头部)、 foot. jsp(底部)和centeLeft. jsp(中左部)，储存结构如图3.1。

![在这里插入图片描述](https://img-blog.csdnimg.cn/e7dc596dbeca447eacfeb02ade4554f9.png)

图3.1 视图层储存结构构成图
### 3.2.2 管理员视图层
管理员视图层有JSP页面组成，
视图层由jSP页面组成，其中主界面为index.jsp文件, 通过框架引入top.jsp(头部)、 main. jsp(主要部分)和left. jsp(左部)，AdminBookMeg.jsp(书籍管理)，AdminOrderMeg.jssp(订单管理), AdminUserMeg.
jsp(用户)储存结构如图3.1。

![在这里插入图片描述](https://img-blog.csdnimg.cn/f715a858270642ce8275a25899d2ac40.png)
图3.1 视图层储存结构构成图

（1）servlet层
servlet层接收和发送前端页面的数据请求
![在这里插入图片描述](https://img-blog.csdnimg.cn/2fdc08b6d0324a90a3d5248ab2999167.png)

图3.2 servlet层

（2）mapper层
Mapper层响应数据库相关操作

![在这里插入图片描述](https://img-blog.csdnimg.cn/c9317ff8d440483e89dd348d91f83c7f.png)

图3.3 mapper层

（3）entity层
用于存放bean模型
![在这里插入图片描述](https://img-blog.csdnimg.cn/61a0039288744684b7dee384eb6dafa4.png)

图3.4 entity层

### 3.2.3 修饰层
修饰层有JS、CSS组成，其中js文件有bookstrap.js、slide.js、jquery.js、uerckeck.js等。CSS文件有font-awesome.css、font-awesome.min.css、addresstyle.css、bootstrap.css、login.css、login1.css、regist.css、slide.css、style.css等，其储存结构如下。


（1）JS层
用于存放js文件
![在这里插入图片描述](https://img-blog.csdnimg.cn/49a18fbb11b34b5f8c61d06d5081edde.png)
图3.5 js层储存结构构成图
（2）CSS层
![在这里插入图片描述](https://img-blog.csdnimg.cn/8456d9d981c74bac818db7a01c193717.png)

图3.6 CSS层储存结构构成图


## 3.3 系统调试
### 3.3.1.网站前台
1.网站主页index.sjp    （主页面和素材借用啦一位博主链接找不到啦）
![在这里插入图片描述](https://img-blog.csdnimg.cn/bf620d970d19498ab3658424530077e1.png)

图3.7 主页面图
![在这里插入图片描述](https://img-blog.csdnimg.cn/e763e4e9988c4ed5aebd35cd4c3d15bc.png)

（1）书籍类

图3.8 浏览书籍页面


# 2.注册首页
![在这里插入图片描述](https://img-blog.csdnimg.cn/5c3953071c6e4631981053a7b518ad13.png)


图3.9 注册页面

# 3.登录首页
![在这里插入图片描述](https://img-blog.csdnimg.cn/2b4cb062706a414389b8f7334110fda1.png)
图3.10 登陆页面

# 4.我的账户页
![在这里插入图片描述](https://img-blog.csdnimg.cn/eca87013ba7f499db37c5b4dd53f4605.png)

图3.11 个人账户页面

# 5.我的订单页
![在这里插入图片描述](https://img-blog.csdnimg.cn/d2c5e6d3a3a84d7fba34b7d791f6ff74.png)

图3.12 订单页面

# 6.我的购物车
![在这里插入图片描述](https://img-blog.csdnimg.cn/cc798b01dbf34952a71fcdf2c82a1ae6.png)

图3.13 购物车页面

（1）支付成功
![在这里插入图片描述](https://img-blog.csdnimg.cn/8307e652bacc473b9fc3a7f79d1a5e2f.png)

图3.14支付成功页面


# 7.收获地址
![在这里插入图片描述](https://img-blog.csdnimg.cn/d993fa8664b5495abe624992bd61564e.png)

图3.15 收货地址页面


### 3.3.2、网站后台
1. 配置数据库
![在这里插入图片描述](https://img-blog.csdnimg.cn/db19933dcfa0471d8a53b85338f42bdc.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/41310439ffcf4ff686c92f3782346d29.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/aaeca60855f14e86bde504e0c0118ee6.png)

图3.16 配置数据库页面

# 1. 后台登录
![在这里插入图片描述](https://img-blog.csdnimg.cn/4a24ebbfeb104f748ed8356b966c0674.png)


图3.17 后台登陆页面

# 2.后台首页
![在这里插入图片描述](https://img-blog.csdnimg.cn/cc29171ec20343b59c2473cd20ca176c.png)


图3.18 后台首页

# 3.用户管理
![在这里插入图片描述](https://img-blog.csdnimg.cn/44c93bd173284f61833a304607834c09.png)



图3.19 后台用户管理

(1)修改用户：
![在这里插入图片描述](https://img-blog.csdnimg.cn/d02901b4fbd04b8ea31f1deb6d7d7f15.png)

图3.20 修改用户信息

(2)删除用户：
![在这里插入图片描述](https://img-blog.csdnimg.cn/1003bcc7bec848fe9164d5dca3178078.png)

图3.21 删除用户信息

4.商品管理
![在这里插入图片描述](https://img-blog.csdnimg.cn/efb65e08d2b64dd1a4bb074446e7a8fc.png)

图3.22 商品管理

5.订单管理
![在这里插入图片描述](https://img-blog.csdnimg.cn/95267d20cfae4c429f3ac2fe77a1b689.png)



图3.23 订单管理

3.3.3.代码实现（主要代码）
（1）index.jsp

```jsp
<body>
   <!-- header -->
    <jsp:include page="header.jsp" />

   <!-- content -->
   <jsp:include page="centreLeft.jsp"/>
         <!-- 幻灯片 -->
         <div id="slide">
            <ul>
            <li>
               <div style="left:0;top:0;"><a href="#"><img width="780" height="420" src="images/01.jpg" alt="" /></a></div>
            </li>
            <li>
               <div style="left:0;top:0;"><a href="#"><img width="780" height="420" src="images/02.jpg" alt="" /></a></div>
            </li>
            </ul>
         </div>
    <!-- 人气推荐 -->
         <div class="goodsbar">
            <span class="goodsbar-title">人气图书</span>
            <div class="goodsbar-content">
             <c:forEach var="book" items="${hotBList }" begin="0" end="3">
                  <dl class="bookBlock">
                     <dd class="img"><a href="  "><img src="images/book.png" class="" /></a></dd>   <!-- href 连接servlet -->
                     <dt><a href=" ">${book.title}</a></dt>  <!-- href 连接servlet -->
                  <dd class="price">单价:￥<span class="unitprice">${price}</span><span class="pull-right">浏览&nbsp;</span></dd>
                  </dl>
               <dl class="bookBlock">
                  <dd class="img"><a href="  "><img src="images/book.png" class="" /></a></dd>   <!-- href 连接servlet -->
                  <dt><a href=" ">${book.title}</a></dt>  <!-- href 连接servlet -->
                  <dd class="price">单价:￥<span class="unitprice">${price}</span><span class="pull-right">浏览&nbsp;</span></dd>
               </dl>
               <dl class="bookBlock">
                  <dd class="img"><a href="  "><img src="images/book.png" class="" /></a></dd>   <!-- href 连接servlet -->
                  <dt><a href=" ">${book.title}</a></dt>  <!-- href 连接servlet -->
                  <dd class="price">单价:￥<span class="unitprice">${price}</span><span class="pull-right">浏览&nbsp;</span></dd>
               </dl>
               <dl class="bookBlock">
                  <dd class="img"><a href="  "><img src="images/book.png" class="" /></a></dd>   <!-- href 连接servlet -->
                  <dt><a href=" ">${book.title}</a></dt>  <!-- href 连接servlet -->
                  <dd class="price">单价:￥<span class="unitprice">${price}</span><span class="pull-right">浏览&nbsp;</span></dd>
               </dl>
            </c:forEach>
            </div>
         </div>
      </div>
   </div>
   <!-- footer -->
       <jsp:include page="footer.jsp" />
</body>
```

（2）login.jsp

```java
     <form action="UsrServlet?action=login&u_type=0" method="post">
        <p class="name">
        <i></i>
        <input type="text" name="userName"  class="userName" placeholder="请输入用户名">
        </p>
        <p class="password">
        <i></i>
        <input type="password" name="password" class="pwd" placeholder="请输入密码"></p>
         <p class="password"> <i></i> <input type="text" name="rnd"  placeholder="请输入验证码" style="width: 139px;heigth:20px;" maxlength="4">
      <img src="Random.jsp" style="height: 35px; width: 97px;"></p>
<input type="submit" class="loginsss"   value="登录">
         <a href="admin_login.jsp"><input type="button" value="我是管理员"></a></br>
        <p class="remember"><input type="checkbox" name="remember">记住密码</p>
        <p class="regist"><span>没有账号?</span><a href="register.jsp">立即注册</a></p>
        <div class="clear"></div>
    </form>
```
register.jsp

```jsp
<article>
    <h1><span style="color:#000;font-size:40px;">注册图书网上商城</span></h1>
    <div class="main">
        <form action="UsrServlet?action=register" method="post">
            <div class="tel">
                <input type="text" name="username_register" placeholder="用户名"><em>由5-8个字符组成！</em>
            </div>
            <div class="userName">
                <input type="password" name="register_mima" placeholder="密码"><em>使用字母数字或者下划线，8-12个字符</em>
            </div>
            <div class="userName">
                <input type="text" name="address" placeholder="地址"><em>只用写市级即可。</em>
            </div>
            <div class="password">
                <input type="text" name="tel" placeholder="手机号"><em>由11个字符组成！</em>
            </div>
            <div class="againpwd">
                <input type="text" name="email" placeholder="请输入邮箱！">
            </div>
            <button>注册</button>
        </form>
    </div>
```
Index3.jsp
```java
<%
    BookDao bdao = new BookDao();
    ArrayList<BookModel> books = bdao.findAllBooks();
    for (int i = 0; i < books.size(); i++) {
        BookModel bm = books.get(i);
%>
<tr>
    <td><%=bm.getId()%>
    </td>
    <td><%=bm.getName()%>
    </td>
    <td><%=bm.getAuthor() %>
    </td>
    <td><%=bm.getPrice()%>
    </td>
    <td><%=bm.getCounts()%>
    </td>
    <td><img alt="src=<%=bm.getImage()%>  style="width:100px;height:130px;"></td>
    <p>
    <td><%=bm.getDescripte() %>
    </td>
    </p>
    <td><%=bm.getType() %>
    </td>
    <td><%=bm.getCategory_description() %>
    </td>
<td style="text-align:center;margin:0auto;"><a href="CartServlet?id=<%=bm.getId() %>"
     style="font-size:20px;">加入购物车</a></td>
</tr>
<%}%>
```
Userinfor.jsp
```java
<!--修改信息-->
<div class="alterinfor">
    <form action="UserServlet?opt=updateUser" method="post">
        <input type="hidden" name="id" value="${user.id }" />
        <label>姓名</label>
        <input type="text" class="form-control" name="name" placeholder="真实姓名" value="${username}"/>
        <label>*电子邮箱</label>
        <input type="text" class="form-control" name="mail" placeholder="邮箱" value="${email}"/>
        <label>*手机号码</label>
        <input type="text" class="form-control" name="phone"  placeholder="手机号码" value="${phone }"/>
        <label>*联系地址</label>
        <textarea rows="3" cols="" class="form-control" name="address" placeholder="联系地址"> ${address}</textarea>
        <br>
        <button class="btn btn-default" type="submit">修改资料</button>
    </form>
</div>
```

订单管理
```java
    out.print("<table border=1 align=eenter >");
    out.print("<tr>");
    out.print("<th align=eenter>"+"订单号 "+"</th>");
    out.print("<th>"+"用户名"+"</th>");
    out.print("<th>"+"书名"+"</th>");
    out.print("<th>"+"价格"+"</th>");
    out.print("<th>"+"数量"+"</th>");
    out.print("<th>"+"地址"+"</th>");
    out.print("<th>"+"联系电话"+"</th>");
    out.print("<th>"+"状态"+"</th>");
    out.print("<th>"+"用户id"+"</th>");
    out.print("<th>"+"操作订单"+"</th>");
    out.print("</tr>");
    //连接数据库
    try{con = DriverManager.getConnection(url,user,password);
        sql=con.createStatement();
        String SQL=null;
        if(submit.contains("username")){
            SQL="SELECT * FROM orders WHERE username='"+mess+"'";
        }
        rs=sql.executeQuery(SQL);
        while(rs.next()){
            out.print("<tr>");
            out.print("<td id=tom>"+rs.getString(1)+"</td>");
            out.print("<td id=tom>"+rs.getString(2)+"</td>");
            out.print("<td id=tom>"+rs.getString(3)+"</td>");
            out.print("<td id=tom>"+rs.getString(4)+"</td>");
            out.print("<td id=tom>"+rs.getString(5)+"</td>");
            out.print("<td id=tom>"+rs.getString(6)+"</td>");
            out.print("<td id=tom>"+rs.getString(7)+"</td>");
            out.print("<td id=tom>"+rs.getString(8)+"</td>");
            out.print("<td id=tom>"+rs.getString(9)+"</td>");
            out.print("<td id=tom> <form action='https://www.kuaidi100.com/?from=openv'> <select><option>"+"删除订单"+"</option><option>"+"取消订单"+"</option><option>"+"物流查询"+"</option></select></td><td><input type='submit' value='确定'/></form></td>");
            out.print("</tr>");
        }
        out.print("</table>");
        con.close();
    }
    catch(SQLException e){
        out.print("<h3>"+e+"</h3>");
    }
%>
```
Showcarts.jsp
```java
    <table class="table table-hover">
        <thead>
        <tr>
            <th>书本编号</th>
            <th>书本名称</th>
            <th>书本单价</th>
            <th>书本数量</th>
            <th>书本小计</th>
        </tr>
        </thead>
        <%
            //1:将添加到购物车里面的物品显示出来
            Map<Integer, CartItem> map = (Map<Integer, CartItem>) session.getAttribute("cart");
            if (map == null) {
            } else {
                //2:将购物车里面的内容遍历出来
                double count = 0;//显示出总价格
                for (Map.Entry<Integer, CartItem> entry : map.entrySet()) {
                    //计算出每一样的书籍一共花了多少钱
                    double price = entry.getValue().getBook().getPrice() * entry.getValue().getQuantity();
                    //计算出一共花了多少钱
                    count = count + price;
        %>
        <tr align="left">
            <td><%=entry.getKey() %>
            </td>
            <td><%=entry.getValue().getBook().getName() %>
            </td>
            <td><%=entry.getValue().getBook().getPrice() %>
            </td>
            <td><%=entry.getValue().getQuantity() %>
            </td>
            <td><%=entry.getValue().getBook().getPrice() * entry.getValue().getQuantity()%>
            </td>
        </tr>
        <form action="Insertcart.jsp?username=${sessionScope.u_name}&bookname=<%=entry.getValue().getBook().getName()%>&price=<%=entry.getValue().getBook().getPrice() %>&counts=<%=entry.getValue().getQuantity() %>" method="post">
        <%} %>
        <tr>
            <td colspan="4" align="right"><span style="color: #921e12;font-size: 18px" >价格总计</span></td>
            <td ><span style="color: #921e12;font-size: 18px" > <%=count %> </span>&nbsp;&nbsp;

<input type="submit" name="submit" value="支付" style="width: 60px;font-size: 18px" >
 </form>

            </td>
        </tr>
        <%} %>
    </table>
```
Insertcart.jsp
```java
<%   //获取提交的属性值
    request.setCharacterEncoding("utf-8");
    String username=request.getParameter("username");
    username=username.trim();
    String bookname=request.getParameter("bookname");
    bookname=bookname.trim();
    String price=request.getParameter("price");
    price=price.trim();
    String counts=request.getParameter("counts");
    counts=counts.trim();
    String submit=request.getParameter("submit");
    if(bookname.length()==0){
        response.sendRedirect("inputNumber.jsp");
        return;
    }
    String url="jdbc:mysql://localhost:3306/book?"+
            "useSSL=false&serverTimezone=CST&characterEncoding=utf-8";
    String user="root";
    String password="hhhhhh";

    //连接数据库
    try{con = DriverManager.getConnection(url,user,password);
        sql=con.createStatement();
        String SQL=null;
        String query=null;
        if(submit.contains("支付")){
            query="SELECT * FROM user WHERE username='"+username+"'";
        }
        else if(submit.contains("username")){
            out.print("支付失败");
        }
        cx = sql.executeQuery(query);

        while(cx.next()){
            request.setAttribute("user_id", cx.getString(1));

            request.setAttribute("username", cx.getString(2));

            request.setAttribute("pwd", cx.getString(3));

            request.setAttribute("phone", cx.getString(4));

            request.setAttribute("email", cx.getString(5));

            request.setAttribute("address", cx.getString(6));
            out.print("</tr>");
        }
        if(submit.contains("支付")){
            SQL="INSERT INTO orders(username,bookname,price,counts,address,phone,state,user_id) VALUES('"+username+"','"+bookname+"','"+price+"','"+counts+"','"+request.getAttribute("address")+"','"+request.getAttribute("phone")+"','0','"+request.getAttribute("user_id")+"')";
        }
        else if(submit.contains("username")){
            out.print("支付失败");
        }
        rs=sql.executeUpdate(SQL);
        out.print(rs+"恭喜您购买成功，欢迎下次购买");
        con.close();
    }
    catch(SQLException e){
        out.print("<h3>"+e+"</h3>");
    }

%>
```



