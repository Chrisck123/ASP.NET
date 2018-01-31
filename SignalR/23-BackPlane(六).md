今天...我們就來使用非常親民的Azure Service Bus

來實現我們SignalR的Scaleout

首先我們先打開[Azure](https://azure.microsoft.com/zh-tw/)的網站


![http://ithelp.ithome.com.tw/upload/images/20170109/20103426t8k1syCupp.jpg](http://ithelp.ithome.com.tw/upload/images/20170109/20103426t8k1syCupp.jpg)



接著登入後就可以看到歡迎我們的儀表板了!!


![http://ithelp.ithome.com.tw/upload/images/20170109/20103426XxPzk6fQMe.jpg](http://ithelp.ithome.com.tw/upload/images/20170109/20103426XxPzk6fQMe.jpg)



再來我們建立一個新的Service Bus，這邊選的是日本東部


![http://ithelp.ithome.com.tw/upload/images/20170110/20103426fDajDLBPL9.png](http://ithelp.ithome.com.tw/upload/images/20170110/20103426fDajDLBPL9.png)



接著我們點選共用的存取原則後，去複製連接字串


![http://ithelp.ithome.com.tw/upload/images/20170110/20103426s9vpsGMvD1.jpg](http://ithelp.ithome.com.tw/upload/images/20170110/20103426s9vpsGMvD1.jpg)



再來我們又得打開Startup.cs這個檔案

去設定`GlobalHost.DependencyResolver`使用UseServiceBus，並填入剛剛的連接字串以及你希望在紀錄中看到的名稱


![http://ithelp.ithome.com.tw/upload/images/20170110/2010342680SPU8uNLy.jpg](http://ithelp.ithome.com.tw/upload/images/20170110/2010342680SPU8uNLy.jpg)



接著....測試一下!!


![http://ithelp.ithome.com.tw/upload/images/20170110/20103426PF16X8wYHy.jpg](http://ithelp.ithome.com.tw/upload/images/20170110/20103426PF16X8wYHy.jpg)




![http://ithelp.ithome.com.tw/upload/images/20170110/20103426WxjTXlePjc.jpg](http://ithelp.ithome.com.tw/upload/images/20170110/20103426WxjTXlePjc.jpg)




YA成功!!

然後我們再來點選一下剛剛建立的Service Bus(AzureSignalr)的概觀


![http://ithelp.ithome.com.tw/upload/images/20170110/20103426q0BfyqM3pT.jpg](http://ithelp.ithome.com.tw/upload/images/20170110/20103426q0BfyqM3pT.jpg)



就可以看到底下那排紀錄，這時候我們來點選最後一條紀錄


![http://ithelp.ithome.com.tw/upload/images/20170110/20103426WN2qTJfXKP.jpg](http://ithelp.ithome.com.tw/upload/images/20170110/20103426WN2qTJfXKP.jpg)



是不是就看到了...訊息記數是1!!


![http://ithelp.ithome.com.tw/upload/images/20170110/20103426QFD7JLfIYf.jpg](http://ithelp.ithome.com.tw/upload/images/20170110/20103426QFD7JLfIYf.jpg)
