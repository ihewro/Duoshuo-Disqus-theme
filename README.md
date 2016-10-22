## 一个关于仿disqus的多说风格css

## 使用说明

* comment.php 

`var duoshuoQuery` 的选项里面增加一个`theme:"none"`的选项，这样css完全由我们接管啦！
也就是这样的效果

```JavaScript
var duoshuoQuery = {short_name:"hewro",theme:"none"};
```

* css文件里面的
`.ds-header.ds-gradient-bg:after `
里面的`width` 根据你的“热门评论”自定义文字的长度来设置。

* 更改embed.js

	* 搜索`<form method="post">` 改成 `<form id="commenthw" method="post">`（加上id，我们才能对其进行加上css）
	* 搜索
	```javascript
	this.el.find(".ds-comments-tab-" + a).html(this.el.hasClass("ds-narrow") ? '<span class="ds-service-icon ds-' + a + '"></span>' + i: (i ? '<span class="ds-highlight">' + i + "</span>": "0") + s[a][1])
```
改成
	```javascript
this.el.find(".ds-comments-tab-" + a).html(this.el.hasClass("ds-narrow") ? '<span class="ds-highlight">' + i + '</span>' + s[a][1]: (i ? '<span class="ds-highlight">' + i + "</span>": "0") + s[a][1])
```
(这个改动是让手机端的几条评论的地方不是只有数字而是和电脑端一样的显示)


OK!

如果你还想表情框自定义修改，可以查看我的js:<http://www.ihewro.com/duoshuo/embedhw4.js>

