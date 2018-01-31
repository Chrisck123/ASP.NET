基本上**SiganlR**在於**JavaScriptClient**與**Hub**有**兩種**連線模式

一種是透過**generated proxy**來連線

另一種是透過**createHubProxy**來連接

**1.generated proxy**

這也是一般最普遍的連接方式

只要引用了上一篇所引用的

`<script type="text/javascript" src="@Url.Content("~/signalr/hubs")"></script>`

就可以使用上一篇所講述的方法進行連線

但...他似乎有一個限制條件

那就是必須在同一個Domaim內


**2.createHubProxy**

筆者會用到這個也是因為當初開了兩個專案

之間再互相溝通

但....沒辦法連接

所以後來才使用了這個方法

首先打開我們萬用的...Nuget ，接著....


![http://ithelp.ithome.com.tw/upload/images/20161219/20103426j5PiLpPjD6.jpg](http://ithelp.ithome.com.tw/upload/images/20161219/20103426j5PiLpPjD6.jpg)



再來引用Cors


![http://ithelp.ithome.com.tw/upload/images/20161219/201034269SQOPlxb30.jpg](http://ithelp.ithome.com.tw/upload/images/20161219/201034269SQOPlxb30.jpg)



接著把原本的`app.MapSignalR();`

修改為下圖


![http://ithelp.ithome.com.tw/upload/images/20161219/20103426wtvtCHfbaW.jpg](http://ithelp.ithome.com.tw/upload/images/20161219/20103426wtvtCHfbaW.jpg)



再來頁面上的連接與調用方法


![http://ithelp.ithome.com.tw/upload/images/20161219/20103426sVUDrndYOE.jpg](http://ithelp.ithome.com.tw/upload/images/20161219/20103426sVUDrndYOE.jpg)



測試一下


![http://ithelp.ithome.com.tw/upload/images/20161219/20103426lKxskjuH7X.png](http://ithelp.ithome.com.tw/upload/images/20161219/20103426lKxskjuH7X.png)




大功告成!!
