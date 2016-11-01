# 程序功能

从百度到的提供免费代理的网站上爬取免费代理，并通过访问静态资源的方式检测代理是否可用，将可用的代理存放到本地文件当中。

# 依赖库

+ request：发请求，下载网页用的，类似于python的urllib2
+ cheerio：解析网页用的，语法和jquery相似，类似于python的beautifulsoup。

直接用npm下载即可
```
npm install request --save
npm install cheerio --save
```



# 与python的不同

用python写过不少爬虫，本来以为这次会非常轻松的完成，不过失算了。

由于nodejs的单线程异步特性，如果不加思考直接像python那么写，那么request请求还没回来的时候下面的代码就已经执行完了，保存的总是空的。

所以得做一些小手脚让它等待异步函数执行完毕再运行剩下的代码。我采用的办法是用标志量。

更好的解决办法应该是用promise，不过我比较愚鲁，看了半天愣是没看懂，希望不久的将来能领悟吧……
