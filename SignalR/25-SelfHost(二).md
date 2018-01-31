首先!!上一篇我們使用了Self Host的方式

在console裡ON了一個Hub，再經由JavaScript Client去跟他做連接

那麼今天我們就來用Redis先來測試看看

到底...可不可以這樣搞在配上Redis!!作為Back plane!!

首先我們先在SignalR_Console專案裡安裝

`Microsoft.AspNet.SignalR.Redis`

由於之前有安裝過在SignalR的專案裡，所以直接到管理Nuget那邊去設定就好了

接著我們在Hub裡一樣的加上底下這一段

`GlobalHost.DependencyResolver.UseRedis(server, port, password, eventKey)`


![http://ithelp.ithome.com.tw/upload/images/20170111/20103426xy6Ns6hppV.jpg](http://ithelp.ithome.com.tw/upload/images/20170111/20103426xy6Ns6hppV.jpg)



當然如先前所說的...帳號密碼...服務名稱IP請隨意!!

再來把服務ON起來測試

先登入Redis


![http://ithelp.ithome.com.tw/upload/images/20170111/20103426QkuI4S2Fxt.jpg](http://ithelp.ithome.com.tw/upload/images/20170111/20103426QkuI4S2Fxt.jpg)



再來在專案中開始...對話吧!!


![http://ithelp.ithome.com.tw/upload/images/20170111/20103426vSNmH3ArXN.jpg](http://ithelp.ithome.com.tw/upload/images/20170111/20103426vSNmH3ArXN.jpg)



在這邊我們可以看到的確Redis有在動!!

然後我們的JavaScript Client也有反應

同理可証....

SQL Server 以及 Azure Service Bus也可以這樣玩!!
