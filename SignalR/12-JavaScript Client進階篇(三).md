這篇我們就來說說Error Handle以及Log紀錄

首先先來搞錯誤handle

首先先針對Hub連線事件做Error Handle


![http://ithelp.ithome.com.tw/upload/images/20161229/20103426GwCL7WNHoz.jpg](http://ithelp.ithome.com.tw/upload/images/20161229/20103426GwCL7WNHoz.jpg)



首先加入下列這一段一定會出錯的方法在`OnConnected`事件中

`string aa = null;aa.ToString();`

測試一下


![http://ithelp.ithome.com.tw/upload/images/20161229/20103426BuID8tmuIm.jpg](http://ithelp.ithome.com.tw/upload/images/20161229/20103426BuID8tmuIm.jpg)



再來是調用Hub方法時發生例外錯誤的Handle

首先我們先在方法中插入一個一定會跳出Exception的程式碼(同上)

接著JavaScript Client上加上事件，這邊得用```fail```就是之前也有用過的


![http://ithelp.ithome.com.tw/upload/images/20161229/20103426QGs6KIWN5h.jpg](http://ithelp.ithome.com.tw/upload/images/20161229/20103426QGs6KIWN5h.jpg)



再來測試一下


![http://ithelp.ithome.com.tw/upload/images/20161229/20103426rtih5ll24O.jpg](http://ithelp.ithome.com.tw/upload/images/20161229/20103426rtih5ll24O.jpg)



再來弄Log紀錄部分

其實這東西很簡單...

我們只需要加一行Code就可以了!!

`$.connection.hub.logging = true;`

測試一下!! 嗯很清楚!! GOOD


![http://ithelp.ithome.com.tw/upload/images/20161229/20103426v0a1OtZtD4.png](http://ithelp.ithome.com.tw/upload/images/20161229/20103426v0a1OtZtD4.png)
