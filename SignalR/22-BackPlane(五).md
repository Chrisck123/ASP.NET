今天我們要啟用Redis來作為我們實現Scaleout機制的方法

承上篇我們已經安裝好Redis了

現在我們需要的只是在....`Startup.cs`裡面加上這短短的一行就結束了!!

`GlobalHost.DependencyResolver.UseRedis(server, port, password, eventKey);`

上述的eventKey=設定的名稱(迷之音：你爽就好!!)


![http://ithelp.ithome.com.tw/upload/images/20170109/20103426E6ck5g3nay.jpg](http://ithelp.ithome.com.tw/upload/images/20170109/20103426E6ck5g3nay.jpg)



成功嚕!!


![http://ithelp.ithome.com.tw/upload/images/20170109/20103426CLzkVl0ANI.png](http://ithelp.ithome.com.tw/upload/images/20170109/20103426CLzkVl0ANI.png)



打開一下Redis查詢一下Log

我們輸入下列來進入Redis

`redis-cli -a password`

再來輸入`SUBSCRIBE Redis`來查詢`eventKey`為Redis的紀錄，結果如下圖



![http://ithelp.ithome.com.tw/upload/images/20170109/20103426yp5QZuApLU.jpg](http://ithelp.ithome.com.tw/upload/images/20170109/20103426yp5QZuApLU.jpg)



接著我們再多發送幾次的訊息(謎之音：你明明就只有....F5重整頁面而已 偷懶的傢伙)

就可以看到下面的成果了!!



![http://ithelp.ithome.com.tw/upload/images/20170109/20103426wCcdQS9tTG.jpg](http://ithelp.ithome.com.tw/upload/images/20170109/20103426wCcdQS9tTG.jpg)

好了!!我們辦到了!!
