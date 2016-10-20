## 一个关于仿disqus的多说风格css

## 使用说明

* 必须修改本地embed.js：搜索`<form method="post">` 改成 `<form id="commenthw" method="post">`
* 搜索
```javascript
this.el.find(".ds-comments-tab-" + a).html(this.el.hasClass("ds-narrow") ? '<span class="ds-service-icon ds-' + a + '"></span>' + i: (i ? '<span class="ds-highlight">' + i + "</span>": "0") + s[a][1])
```
修改成
```javascript
this.el.find(".ds-comments-tab-" + a).html(this.el.hasClass("ds-narrow") ? '<span class="ds-service-icon ds-' + a + '"></span>' + i: (i ? '<span class="ds-highlight">' + i + "</span>": "0") + s[a][1])
```

OK!

如果你还想表情框自定义修改，可以查看我的js:<http://www.ihewro.com/duoshuo/embedhw4.js>

