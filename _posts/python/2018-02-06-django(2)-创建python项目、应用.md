---
categories: [python]
---
## 创建项目
```
django-admin startproject <项目名>
```
### 进入目录,目录结构如下:
```
├── manage.py
└── testdjango
    ├── __init__.py
    ├── settings.py
    ├── urls.py
    └── wsgi.py

```


## 目录结构介绍
### manage.py
与项目交互的命令行工具入口
### testdjango
项目目录,包含项目基本配置,不建议修改名称因为项目配置文件大量包含了该名称,牵一发动全身
### wsgi.py
Python Web Server Gateway Interface (python服务器网关接口) <br></br>
python应用与web服务器之前的接口
### urls.py
url配置文件
### settings.py
项目总配置文件 <br></br>
包含数据库、web应用、时间等各种配置：<br></br>
<table>
<tr><td>BASE_DIR</td><td>项目根路径配置</td></tr>
<tr><td>SECRET_KEY  </td><td>安全码：项目启动必须要有它自动生成 </td></tr>
<tr><td>DEBUG  </td><td>是否启动调试模式,例：启动后会把异常抛给前端等</td></tr>
<tr><td>ALLOWED_HOSTS  </td><td>允许访问的host,例：谢了localhost,那么本地127.0.0.1将不能访问  </td></tr>
<tr><td>INSTALLED_APPS  </td><td>服务的应用名,如果我们创建了自己的引用需要吧应用名添加到这个数组里  </td></tr>
<tr><td>MIDDLEWARE  </td><td>中间件,django自带的一些工具  </td></tr>
<tr><td>ROOT_URLCONF  </td><td>url根文件配置,默认值指向自带的urls.py  </td></tr>
<tr><td>TEMPLATES  </td><td>django模板配置  </td></tr>
<tr><td>WSGI_APPLICATION  </td><td>wsgi相关  </td></tr>
<tr><td>DATABASES  </td><td>数据库配置默认使用自带sqlite3,其他配置可参考<a link='https://docs.djangoproject.com/en/2.0/ref/settings/#databases'>https://docs.djangoproject.com/en/2.0/ref/settings/#databases</a>  </td></tr>
<tr><td>AUTH_PASSWORD_VALIDATORS  </td><td>密码认证相关  </td></tr>
<tr><td>LANGUAGE_CODE  </td><td>国际化配置: 语言  </td></tr>
<tr><td>TIME_ZONE  </td><td>国际化配置: 时区  </td></tr>
<tr><td>USE_I18N  </td><td>国际化配置  </td></tr>
<tr><td>USE_L10N  </td><td>国际化配置  </td></tr>
<tr><td>USE_TZ  </td><td>国际化配置  </td></tr>
<tr><td>STATIC_URL  </td><td>静态文件的地址  </td></tr>
</table>

### __init__.py
python 声明模块的文件,有了它项目可当成模块直接引用

## 创建应用
进入 manage.py 同级目录
```
python3 manange.py startapp <应用名>
```
添加应用名到settings.py 的INSTALLED_APPS 里
现在目录结构如下
```
├── manage.py
├── testapp
//新增目录
│   ├── admin.py //当前应用的后台管理系统的文件
│   ├── apps.py //当前应用的一些配置 django1.9之后有
│   ├── __init__.py
│   ├── migrations //数据迁移模块
│   │   └── __init__.py
│   ├── models.py //数据模型模块 创建数据表（orm系统）
│   ├── tests.py //自动化测试模块
│   └── views.py //执行响应的逻辑代码,项目大部分代码都在这里
└── testdjango
    ├── __init__.py
    ├── __pycache__
    │   ├── __init__.cpython-35.pyc
    │   └── settings.cpython-35.pyc
    ├── settings.py
    ├── urls.py
    └── wsgi.py
```