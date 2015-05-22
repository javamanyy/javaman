---
layout: post
title: Jekyll中添加评论系统
cover: cover.jpg
date:   2015-05-23 12:00:00
categories: others
---

创建Disqus账号
----------


注册disqus账号https://disqus.com 并登陆。<br/>
点击右上角头像边上的settings按钮。弹出菜单选择'Add Disqus To site'<br/>
打开Add Disqus to your site的页面： <br/>
`Site Name `<br/>
随便填一个名字就好了<br/>
`Choose your unique Disqus URL`<br/>
这里就是后面引用的名字啦。例如：javaman.disqus.com<br/>
点击Finish就好。<br/>


添加到Jekyll中
-------------

- _config.yml中添加 disqussite: javaman

- _includes目录下新建comments.ext文件

```
	<script type="text/javascript">
		var disqus_shortname = '{{site.disqussite}}';
		(function() {
			var dsq = document.createElement('script');
		dsq.type = 'text/javascript';
		dsq.async = true;
			dsq.src = '//' + disqus_shortname + '.disqus.com/embed.js';
			(document.getElementsByTagName('head')[0] || document.getElementsByTagName('body'[0]).appendChild(dsq);
			}
		)();
	</script>
```

- 内容显示页面添加评论


```
	<section class="comments">
		{% if page.comments %}
			{% include comments.ext %}
		{% endif %}`
	</section>
```
