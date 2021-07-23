# Welcome to GitHub Pages





## mac OS下使用JSP+Tomcat+mysql+navicat链接数据库过程

### 第一步：下载并安装Tomcat

1. 下载

   下载地址：https://tomcat.apache.org/download-90.cgi

   <img src="/Users/serein/Library/Application Support/typora-user-images/image-20210723004050680.png" alt="image-20210723004050680" style="zoom: 25%;" />

2. 验证是否安装成功

   2.1. 打开终端，输入cd+空格、再把bin文件夹直接拖拉到终端

   2.2. 输入sudo chmod 755 *.sh，输完回车

   2.3. 输入root用户密码

   2.4. 输入sudo sh ./startup.sh，输完回车

   2.2. 在浏览器内输入网址localhost:8080,能正常显示如下页面则说明Tomcat服务器安装成功

   <img src="/Users/serein/Library/Application Support/typora-user-images/image-20210723004455790.png" alt="image-20210723004455790" style="zoom:25%;" />

   

### 第二步：下载并安装mysql

1. 下载

   下载版本号为5.6.35的mysql

   下载地址：https://downloads.mysql.com/archives/community/

   下载完成后按照提示，一直点击下一步即可安装成功

   <img src="/Users/serein/Library/Application Support/typora-user-images/image-20210723005020986.png" alt="image-20210723005020986" style="zoom:25%;" />

2. 修改密码

   2.1. 执行 cd /usr/local/mysql/bin

   2.2. 回车后，登录管理员权限 sudo su

   2.3. 输入密码并回车后输入以下命令来禁止mysql验证功能 ./mysqld_safe --skip-grant-tables &

   2.4. 输入命令 ./mysql
   2.5. 回车后，输入命令 FLUSH PRIVILEGES;
   2.6. 回车后，输入命令 SET PASSWORD FOR 'root'@'localhost' = PASSWORD('你设置的新密码');

   2.7. 重新打开新的终端，执行 mysql -uroot -p 回车，输入所设置的密码并回车

   出现如下页面则代表成功

   <img src="/Users/serein/Library/Application Support/typora-user-images/image-20210723010032272.png" alt="image-20210723010032272" style="zoom: 50%;" />

   

### 第三步：下载并安装navicat

1. 下载

   下载Navicat Premium试用版以连接mysql数据库

   下载地址：https://www.navicat.com.cn/download/navicat-premium

   选择macOS对应版本下载并安装

<img src="/Users/serein/Library/Application Support/typora-user-images/image-20210723010532840.png" alt="image-20210723010532840" style="zoom:25%;" />

### 第四步：连接mysql数据库

1. 下载完毕后打开navicat，点击左上角“连接”图标以新建mysql数据库链接

<img src="/Users/serein/Library/Application Support/typora-user-images/image-20210723010846634.png" alt="image-20210723010846634" style="zoom: 50%;" />

2. 输入连接名（简单易记）+密码（所设置的数据库密码）

<img src="/Users/serein/Library/Application Support/typora-user-images/image-20210723011227410.png" alt="image-20210723011227410" style="zoom:33%;" />

3. 点击测试连接，出现如下页面则说明连接成功

<img src="/Users/serein/Library/Application Support/typora-user-images/image-20210723011147555.png" alt="image-20210723011147555" style="zoom:33%;" />

4. 点击右下角“保存”按钮

5. 右键新建的连接，然后点击新建数据库，设置数据库名为“dict”

<img src="/Users/serein/Library/Application Support/typora-user-images/image-20210723011937216.png" alt="image-20210723011937216" style="zoom:50%;" />

<img src="/Users/serein/Library/Application Support/typora-user-images/image-20210723012017617.png" alt="image-20210723012017617" style="zoom: 50%;" />

6. 直接将map_enword.sql拖拉进新建的dict数据库中

<img src="/Users/serein/Library/Application Support/typora-user-images/image-20210723012214323.png" alt="image-20210723012214323" style="zoom:33%;" />



### 第五步：通过JSP网页连接MySQL数据库，从MySQL数据库中读出表并显示在JSP网页中

1. 将下载下来的mysql-connector-java-5.0.4.jar文件移动到/apache-tomcat-10.0.8/lib目录下，然后重启Tomcat服务器（重启后重复第一步的操作，使其运行）

   <img src="/Users/serein/Library/Application Support/typora-user-images/image-20210723012702778.png" alt="image-20210723012702778" style="zoom: 33%;" />

2. 修改index.jsp文件并将其放入vis2021文件夹中

   2.1. 修改index.jsp文件

   修改密码（userPasswd）为你所设置的密码：

   <img src="/Users/serein/Library/Application Support/typora-user-images/image-20210723013155647.png" alt="image-20210723013155647" style="zoom: 50%;" />

   修改数据库名（dbName）为“dict”：

   <img src="/Users/serein/Library/Application Support/typora-user-images/image-20210723013303222.png" alt="image-20210723013303222" style="zoom: 50%;" />

   2.2. 移动文件

   <img src="/Users/serein/Library/Application Support/typora-user-images/image-20210723013019482.png" alt="image-20210723013019482" style="zoom: 33%;" />

3. 在浏览器内输入 localhost:8080/vis2021/index.jsp ，出现如下页面，成功！

   <img src="/Users/serein/Library/Application Support/typora-user-images/image-20210723013549235.png" alt="image-20210723013549235" style="zoom: 25%;" />

   



For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).


