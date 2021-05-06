# 体验html页面的DOM结构和节点数据

```javascript
{
  _id: '860f191e810c19729de974ea',
  title: '制作梯度下降实验的实体模型',
  showImage: '/images/experiments/数学/制作梯度下降实验的实体模型.png',
  url: 'https://gitee.com/quanbinn/Learn-Mathematical-Olympiad-The-Interactive-Way/blob/master/chapters/%E5%BE%AE%E5%88%86/%E5%88%B6%E4%BD%9C%E6%A2%AF%E5%BA%A6%E4%B8%8B%E9%99%8D%E5%AE%9E%E9%AA%8C%E7%9A%84%E5%AE%9E%E4%BD%93%E6%A8%A1%E5%9E%8B.md',
  buyUrl: {
     京东: 'https://item.jd.com/45225868113.html#crumb-wrap',
     淘宝: 'https://item.taobao.com/item.htm?spm=a230r.1.14.16.1c8354f4Ig6vLs&id=595424471145&ns=1&abbucket=9#detail'
  },  
  tags: ['数学','深度学习','机器学习'],
  createdAt: 'Wed Sep 23 2020 17:22:29 GMT+0800 (中国标准时间)', // new Date()
  creator: 'QwkSmTCZiw5KDx3L6'  // userId() 
}
```

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>DDHuman.me</title>
</head>
<body>
	<H1>制作梯度下降实验的实体模型</H1>
		<img src="/images/experiments/数学/制作梯度下降实验的实体模型.png">

	<p><a href="https://gitee.com/quanbinn/Learn-Mathematical-Olympiad-The-Interactive-Way/blob/master/chapters/%E5%BE%AE%E5%88%86/%E5%88%B6%E4%BD%9C%E6%A2%AF%E5%BA%A6%E4%B8%8B%E9%99%8D%E5%AE%9E%E9%AA%8C%E7%9A%84%E5%AE%9E%E4%BD%93%E6%A8%A1%E5%9E%8B.md">单击教程链接，开始做实验</a>
	</p>	

	<p>实验道具购买链接：
		<ul>
			<li><a href="https://item.jd.com/45225868113.html#crumb-wrap">京东</a></li>
			<li><a href="https://item.taobao.com/item.htm?spm=a230r.1.14.16.1c8354f4Ig6vLs&id=595424471145&ns=1&abbucket=9#detail">淘宝</a></li>
		</ul>
	</p>

	<p>
		<a href="/images/experiments/math/index.html">数学</a> | <a href="/images/experiments/deeplearning/index.html">深度学习</a> | 	<a href="/images/experiments/mathinelearning/index.html">机器学习</a>
	</p>

</body>
</html>
```

![](/images/用Javascript-CRUD-DOM的Tree节点/体验html页面的DOM结构和节点数据/1a.png)

![](/images/用Javascript-CRUD-DOM的Tree节点/体验html页面的DOM结构和节点数据/1b.jpg)

![](/images/用Javascript-CRUD-DOM的Tree节点/体验html页面的DOM结构和节点数据/1c.jpg)

## Reference

1. [Examples of Trees](https://runestone.academy/runestone/books/published/pythonds/Trees/ExamplesofTrees.html) 



