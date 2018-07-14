---
categories: [essay]
author: [baixiyang]
---

#### 1、没有c++环境的话需要先装c++
```
yum install -y gcc gcc-c++
```

#### 2、安装pcre软件包
centos:
```
yum install -y pcre-devel
```
ubuntu:
```
sudo apt-get update 
sudo apt-get install libpcre3 libpcre3-dev
```
#### 3、从apache官网下载源码压缩包，apr, apr-util, apache
```
wget http://www-eu.apache.org/dist//apr/apr-1.6.3.tar.gz
wget http://www-eu.apache.org/dist//apr/apr-util-1.6.1.tar.gz
wget http://www-eu.apache.org/dist//httpd/httpd-2.4.33.tar.gz
```

#### 4、解压编译(一行一行执行)

```
// 解压
tar zxvf apr-1.6.3.tar.gz
tar zxvf apr-util-1.6.1.tar.gz
tar zxvf httpd-2.4.33.tar.gz

// 安装apr
cd apr-1.6.3
./configure
make
sudo make insall

// 安装apr-util
cd ../apr-util-1.6.1
./configure --prefix=/usr/local/apr-util/ --with-apr=/usr/local/apr/  
make  
sudo make install

// 安装apache
cd ../httpd-2.4.33
./configure --prefix=/usr/local/apache/  --with-apr-util=/usr/local/apr-util/
make
sudo make install
```

#### 5、修改配置文件
```
vim /usr/local/apache/conf/httpd.conf
```
listen 后面的为端口号默认是80
去掉ServerName 注释 改成ServerName localhost:80
其他详细配置可查看官方文档

#### 6、将前端要部署的文件放到 /usr/local/apache/htdocs 下

#### 7、启动apache
```
/usr/local/apache/bin/apachectl start
```
