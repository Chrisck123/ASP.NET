這篇是要跟各位介紹SignalR的IPrincipal(身分認證)

首先筆者先來建立一筆假資料


![http://ithelp.ithome.com.tw/upload/images/20161224/20103426eqsqtbcfbU.jpg](http://ithelp.ithome.com.tw/upload/images/20161224/20103426eqsqtbcfbU.jpg)



接著再來建立個假驗證!!


![http://ithelp.ithome.com.tw/upload/images/20161224/20103426POjNs1cdJF.jpg](http://ithelp.ithome.com.tw/upload/images/20161224/20103426POjNs1cdJF.jpg)



這邊註解的部分...如果你是要玩真的話...~~我想應該不會很難找~~

那就別註解嘿...筆者只是懶惰= =

接著來測試一下~


![http://ithelp.ithome.com.tw/upload/images/20161224/20103426OabbUJEH1R.png](http://ithelp.ithome.com.tw/upload/images/20161224/20103426OabbUJEH1R.png)



測試成功!!


![http://ithelp.ithome.com.tw/upload/images/20161224/20103426VhObAO2nyA.png](http://ithelp.ithome.com.tw/upload/images/20161224/20103426VhObAO2nyA.png)



在這邊讓我們了解到，做了驗證!!更好用= =+

這邊在順便跟各位介紹一個好物!!

`IClientProxy`

當你在Hub Server中想要由塞入方法名稱字串的方式調用方法..

就可以使用這傢伙!!

`IClientProxy proxy = Clients.All;`

上面的`Clients.All`你可以隨你高興地去置換他!!

例如：`Clients.Others`,`Clients.Group("GroupName")`,etc.

`proxy.Invoke(string method, params object[] args);`

這東西真的在某些情況下非常好用....

測試結果如下!!


![http://ithelp.ithome.com.tw/upload/images/20161224/20103426JIN86ice1t.jpg](http://ithelp.ithome.com.tw/upload/images/20161224/20103426JIN86ice1t.jpg)


![http://ithelp.ithome.com.tw/upload/images/20161224/20103426zfOkRVAfpj.jpg](http://ithelp.ithome.com.tw/upload/images/20161224/20103426zfOkRVAfpj.jpg)


