Disque作为国外很出名一款第三方评论系统，之前一直想使用，因为体验和主题我都很喜欢。但是前一段时间disqus完全被墙了，没办法使用，于是继续使用多说下去。于是写了一个disqus评论框的样式，并把多说的所有css本地化。

<!--more-->

开源项目地址： [ihewro/Duoshuo-Disqus-theme](https://github.com/ihewro/Duoshuo-Disqus-theme)

## 使用说明

#### 评论加载的图片地址： ![loading](https://a.disquscdn.com/next/embed/assets/img/loader.5cc23909da9c4a9874500d7a85c4125f.gif)

建议存到你的空间上面去。在css里面搜索替换一下就好了！

#### 修改`comments.php`  

`var duoshuoQuery` 的选项里面增加一个`theme:"none"`的选项来禁止加载多说系统自带的css。

代码示例：

```JavaScript
var duoshuoQuery = {short_name:"hewro",theme:"none"};
```

#### 修改 `duoshuo-disqus.css`css文件

`.ds-header.ds-gradient-bg:after `里面的`width` 根据你的“热门评论”自定义文字的长度来设置。

#### 修改embed.js

* 搜索
`<form method="post">` 改成 `<form id="commenthw" method="post">`（加上id，我们才能对其进行加上css）

* 搜索

```javascript
	this.el.find(".ds-comments-tab-" + a).html(this.el.hasClass("ds-narrow") ? '<span class="ds-service-icon ds-' + a + '"></span>' + i: (i ? '<span class="ds-highlight">' + i + "</span>": "0") + s[a][1])
```

改成

 ```javascript
this.el.find(".ds-comments-tab-" + a).html(this.el.hasClass("ds-narrow") ? '<span class="ds-highlight">' + i + '</span>' + s[a][1]: (i ? '<span class="ds-highlight">' + i + "</span>": "0") + s[a][1])
```
(这个改动是让手机端显示`X条评论`的地方不是只显示评论数而是和电脑端一样的显示`x条评论`)

## 截图

![2016-10-22_112331.jpg](https://www.ihewro.com/usr/uploads/2016/10/1387593804.jpg)
