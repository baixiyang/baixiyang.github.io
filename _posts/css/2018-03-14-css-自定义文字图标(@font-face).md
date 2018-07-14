---
categories: [css]
---
## 使用文字图标的好处
对比与图片类型,问题图标可以使用css为其设置样式,例如font-size,font-weight,color等,也可以直接在文本中使用,提高开发效率
文件大小也比图片小
## @font-face 用法
为了浏览器的兼容性需要引入4中格式的字体文件
{% highlight css %}
//css
@font-face {
  font-family: 'icomoon';
  src:  url('fonts/icomoon.eot');
  src:  url('fonts/icomoon.eot') format('embedded-opentype'),
    url('fonts/icomoon.ttf') format('truetype'),
    url('fonts/icomoon.woff') format('woff'),
    url('fonts/icomoon.svg') format('svg');
  font-weight: normal;
  font-style: normal;
}
{% endhighlight %}
## 字体文件生成方法
因为有类似icomoon这种的网站,所以不需要去深究eot,ttf,woff,svg的格式了,我们只需要每个文字对应的svg格式的文件.
+ 打开网站[https://icomoon.io/app/#/select](https://icomoon.io/app/#/select)
+ 选择左上角菜单**new set from selection点击** 然后**import icons**按钮依次导入全部svg文件
+ 选中所有需要生成字体的图标,点击网页下方的**generate font**,然后在点击下方的**font download**

```
.
├── demo-files
│   ├── demo.css
│   └── demo.js
├── demo.html
├── fonts
│   ├── icomoon.eot
│   ├── icomoon.svg
│   ├── icomoon.ttf
│   └── icomoon.woff
├── Read Me.txt
├── selection.json
└── style.css

```

+ 下载完后,我们只需要上述文件中的style.css 和 fonts 文件夹就可以了.然后在我们的项目中引如style.css