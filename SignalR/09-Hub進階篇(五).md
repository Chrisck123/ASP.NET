SignalR本身也容許我們依照需求去客製**pipeline**

之前我們提到的身分驗證，也可以跟客製pipeline混著用唷!!

首先我們先自定義一個`HubPipelineModule`如下圖


![http://ithelp.ithome.com.tw/upload/images/20161225/201034262LnFVYAfP2.jpg](http://ithelp.ithome.com.tw/upload/images/20161225/201034262LnFVYAfP2.jpg)



接著我們在設定一下SignalR的`Startup`如下圖

![http://ithelp.ithome.com.tw/upload/images/20161225/20103426Er8675i9MT.jpg](http://ithelp.ithome.com.tw/upload/images/20161225/20103426Er8675i9MT.jpg)



再來我們來看看到底`IHubIncomingInvokerContext`有那些東西


![http://ithelp.ithome.com.tw/upload/images/20161225/20103426f39hDUM8F2.png](http://ithelp.ithome.com.tw/upload/images/20161225/20103426f39hDUM8F2.png)



哇...有我在JavaScriptClient回CALL的方法ㄟ


![http://ithelp.ithome.com.tw/upload/images/20161225/20103426oatnzp31Wy.png](http://ithelp.ithome.com.tw/upload/images/20161225/20103426oatnzp31Wy.png)



並且連參數也有


![http://ithelp.ithome.com.tw/upload/images/20161225/20103426cH7yUOTcpO.png](http://ithelp.ithome.com.tw/upload/images/20161225/20103426cH7yUOTcpO.png)



來點看看Hub看看裡面有些甚麼!!


![http://ithelp.ithome.com.tw/upload/images/20161225/20103426aWrXwzdNST.png](http://ithelp.ithome.com.tw/upload/images/20161225/20103426aWrXwzdNST.png)



看到Context... 裡面看來應該有identity唷!!


![http://ithelp.ithome.com.tw/upload/images/20161225/2010342674wdAGElhY.png](http://ithelp.ithome.com.tw/upload/images/20161225/2010342674wdAGElhY.png)



很好..之前的東西都還在!!

在JavaScriptClient加入個斷線方法...


![http://ithelp.ithome.com.tw/upload/images/20161225/20103426CXV4MPVadP.jpg](http://ithelp.ithome.com.tw/upload/images/20161225/20103426CXV4MPVadP.jpg)



再來看一下斷線後回傳的`IHubOutgoingInvokerContext`


![http://ithelp.ithome.com.tw/upload/images/20161225/20103426J6hYJ7MpRx.png](http://ithelp.ithome.com.tw/upload/images/20161225/20103426J6hYJ7MpRx.png)



這裡可以看到是在哪個方法裡呼叫斷線


![http://ithelp.ithome.com.tw/upload/images/20161225/20103426SnhpUrgowy.png](http://ithelp.ithome.com.tw/upload/images/20161225/20103426SnhpUrgowy.png)



甚至連參數都有了!!


![http://ithelp.ithome.com.tw/upload/images/20161225/20103426wvmFCMeZ1b.png](http://ithelp.ithome.com.tw/upload/images/20161225/20103426wvmFCMeZ1b.png)



大家剛剛有看到`hu-Core.九千勝`吧

沒錯!!他就是...那個...Identy的名稱!!

只是前面冠夫姓了!!

阿不對!!是冠上HubName了...
