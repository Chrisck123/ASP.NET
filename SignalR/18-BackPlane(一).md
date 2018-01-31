今天我們就來提一下之前提過的**backplane**

就是所謂的**ScaleOut**

為什麼我們會需要**ScaleOut**?

試想一下當你的**Hub Server**不只一台的時候...

你該如何去知道那些**Client**有連線!?

因為也許...經過**Load Balancing**後

你不知道到底哪些Client跑去了哪台...

所以也許你在A台要發送訊息給連接到B台的Client...

這時候就會很無言了

還好!!SignalR有ScaleOut!!

使用了ScaleOut後看起來就會像是這樣!!


![http://ithelp.ithome.com.tw/upload/images/20170105/20103426GtKVIpLdnx.jpg](http://ithelp.ithome.com.tw/upload/images/20170105/20103426GtKVIpLdnx.jpg)



目前SignalR有3種支援的ScaleOut

分別是SQL Server，Redis Server，當然還有我們的Azure

接下來我們就來安裝這三種組件吧!!

分別是

`Install-Package Microsoft.AspNet.SignalR.SqlServer -Version 2.2.1`


![http://ithelp.ithome.com.tw/upload/images/20170105/20103426CoW1JFgPVX.jpg](http://ithelp.ithome.com.tw/upload/images/20170105/20103426CoW1JFgPVX.jpg)




`Install-Package Microsoft.AspNet.SignalR.Redis`


![http://ithelp.ithome.com.tw/upload/images/20170105/20103426ZrjIzLoV5U.jpg](http://ithelp.ithome.com.tw/upload/images/20170105/20103426ZrjIzLoV5U.jpg)




`Install-Package Microsoft.AspNet.SignalR.ServiceBus`


![http://ithelp.ithome.com.tw/upload/images/20170105/20103426j6QISMaclY.jpg](http://ithelp.ithome.com.tw/upload/images/20170105/20103426j6QISMaclY.jpg)
