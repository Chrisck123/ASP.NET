今天就來帶大家了解一下在**SignalR**使用**Asynchronous**

我們先建立一個**async & await**的方法，如下


![http://ithelp.ithome.com.tw/upload/images/20161224/20103426hOXchG5Wqt.jpg](http://ithelp.ithome.com.tw/upload/images/20161224/20103426hOXchG5Wqt.jpg)



接著來測試一下....


![http://ithelp.ithome.com.tw/upload/images/20161224/20103426UKFNIQE2r4.png](http://ithelp.ithome.com.tw/upload/images/20161224/20103426UKFNIQE2r4.png)



m很好!!調用完後才回來~繼續!!

測試成功!!


![http://ithelp.ithome.com.tw/upload/images/20161224/201034268w8aFTLLOo.png](http://ithelp.ithome.com.tw/upload/images/20161224/201034268w8aFTLLOo.png)



在這裡順便介紹一下連線的**lifetime event**

Client端連線成功


![http://ithelp.ithome.com.tw/upload/images/20161224/20103426FIctW9SBO8.jpg](http://ithelp.ithome.com.tw/upload/images/20161224/20103426FIctW9SBO8.jpg)



Client端斷線


![http://ithelp.ithome.com.tw/upload/images/20161224/20103426ty0TvWMHGj.jpg](http://ithelp.ithome.com.tw/upload/images/20161224/20103426ty0TvWMHGj.jpg)



Client端重新連線成功


![http://ithelp.ithome.com.tw/upload/images/20161224/20103426rL2FuwxXoT.jpg](http://ithelp.ithome.com.tw/upload/images/20161224/20103426rL2FuwxXoT.jpg)



這裡介紹一下SignalR用來儲存自定義data的state

首先，先在你需要呼叫的方法前加上`core.state.userName = "你要丟的東西";`如下圖


![http://ithelp.ithome.com.tw/upload/images/20161224/201034265sgowkypA4.jpg](http://ithelp.ithome.com.tw/upload/images/20161224/201034265sgowkypA4.jpg)



再來測試一下


![http://ithelp.ithome.com.tw/upload/images/20161224/20103426WEy1HV7RXe.jpg](http://ithelp.ithome.com.tw/upload/images/20161224/20103426WEy1HV7RXe.jpg)



成功!!

BTW 這東西在.NET Client叫做**CallerState**


