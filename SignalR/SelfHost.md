話說...我們大部分的範例幾乎都是把Hub放在Web Application上!!

看起來似乎要使用SignalR Host一定得在Web Application裡對吧...

其實不用

下面我們很快地做一個簡單的示範

首先我們先建立一個Console專案


![http://ithelp.ithome.com.tw/upload/images/20170111/20103426BmtGKXYTku.jpg](http://ithelp.ithome.com.tw/upload/images/20170111/20103426BmtGKXYTku.jpg)



再來...打開套件管理器主控台先來安裝：

`Install-Package Microsoft.AspNet.SignalR.SelfHost`

`Install-Package Microsoft.Owin.Cors`


接著我們在console專案中把服務給on起來


![http://ithelp.ithome.com.tw/upload/images/20170111/20103426abqbUCTv3F.jpg](http://ithelp.ithome.com.tw/upload/images/20170111/20103426abqbUCTv3F.jpg)



再來新增一個html檔案叫做Default(名字隨你爽就好)

我們調整一下他的內容(簡單的說就是做跟以前使用JascriptClient類似的事情)


![http://ithelp.ithome.com.tw/upload/images/20170111/20103426IcDs8U59cK.jpg](http://ithelp.ithome.com.tw/upload/images/20170111/20103426IcDs8U59cK.jpg)



再來on起來測試!!


![http://ithelp.ithome.com.tw/upload/images/20170111/20103426yLTvjJA3AR.png](http://ithelp.ithome.com.tw/upload/images/20170111/20103426yLTvjJA3AR.png)![http://ithelp.ithome.com.tw/upload/images/20170111/201034262MDvIHoB82.jpg](http://ithelp.ithome.com.tw/upload/images/20170111/201034262MDvIHoB82.jpg)



成功!!

最後...恭喜你看完這篇!!



![http://ithelp.ithome.com.tw/upload/images/20170111/20103426uwCipWqDtZ.jpg](http://ithelp.ithome.com.tw/upload/images/20170111/20103426uwCipWqDtZ.jpg)

