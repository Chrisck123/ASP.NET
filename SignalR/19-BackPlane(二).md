這篇我們就開始實作吧!!

為了實現測試...我們需要使用多台的Server或是....你可以考慮使用VMware...

那看起來就會像這樣


![http://ithelp.ithome.com.tw/upload/images/20170105/20103426HxPNHDkxl6.jpg](http://ithelp.ithome.com.tw/upload/images/20170105/20103426HxPNHDkxl6.jpg)



如果想要使用SQL Server來實現Scaleout，首先你必須得有大於等於SQL Server 2005以上的版本

第一步...我們先確認是否安裝完成

請檢查一下是否有看到下圖的組件出現在參考中!!


![http://ithelp.ithome.com.tw/upload/images/20170105/20103426fa37SEu7wu.jpg](http://ithelp.ithome.com.tw/upload/images/20170105/20103426fa37SEu7wu.jpg)



記得要先去SQL Server開一個你想要的資料庫

再來我們先打開`Startup.cs`

在`Configuration`中先加入引用


![http://ithelp.ithome.com.tw/upload/images/20170106/20103426JMlH2RcnPa.jpg](http://ithelp.ithome.com.tw/upload/images/20170106/20103426JMlH2RcnPa.jpg)



接著我們繼續執行下去

執行完畢後，我們打開資料庫來檢查


![http://ithelp.ithome.com.tw/upload/images/20170106/20103426gPWwdumneq.jpg](http://ithelp.ithome.com.tw/upload/images/20170106/20103426gPWwdumneq.jpg)



SignalR會自動幫我們建立3張資料表

分別來看看裡面紀錄些甚麼


![http://ithelp.ithome.com.tw/upload/images/20170106/201034266IreHU095N.jpg](http://ithelp.ithome.com.tw/upload/images/20170106/201034266IreHU095N.jpg)




![http://ithelp.ithome.com.tw/upload/images/20170106/20103426uovlRAcBDN.jpg](http://ithelp.ithome.com.tw/upload/images/20170106/20103426uovlRAcBDN.jpg)




![http://ithelp.ithome.com.tw/upload/images/20170106/20103426XLsQEUm0CA.jpg](http://ithelp.ithome.com.tw/upload/images/20170106/20103426XLsQEUm0CA.jpg)




據傳聞...

[這個連結似乎是他在DB做的操作唷](https://github.com/SignalR/SignalR/blob/dev/src/Microsoft.AspNet.SignalR.SqlServer/send.sql#L34)

請安心服用!!

下一篇我們繼續來講....Redis...

不熟悉Linux操作的朋友們...可以先去稍微研究一下唷!!

不過如果你堅持不想研究...那也沒關係

因為我會從安裝Redis Server開始說起= =+

但..在下對Linux不太熟...所以如果觀念上有誤差的話，還請各位大大們....多多海涵!!
