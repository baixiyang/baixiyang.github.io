---
categories: [python]
---
## python 安装
### 下载python安装包
```
　wget https://www.python.org/ftp/python/3.6.0/Python-3.6.0a1.tar.xz
```
### 解压
```
  tar zxf Python-3.6.0a1.tar.xz
```
### 编译安装
```
./configure --prefix=<安装路径>
make && make install
```
### 软链接
```
ln -s ./bin/python3 <安装路径>/bin/python3
```

## pip安装
###
```
wget  https://bootstrap.pypa.io/get-pip.py
python3 get-pip.py
```

## django 安装
###
```
pip install Django==2.0.2
```