在前面幾篇裡我們有提到在JavaScriptClient中宣告連線時

(`var core = $.connection.core;`)

第一個字母要小寫

但如果我們在Hub上加上`HubNameAttribute`，如下圖


![http://ithelp.ithome.com.tw/upload/images/20161221/20103426CmSFFG1R3t.jpg](http://ithelp.ithome.com.tw/upload/images/20161221/20103426CmSFFG1R3t.jpg)



這時我們就可以使用大寫的名稱了

`var core = $.connection.Core;`


測試一下，成功!!


![http://ithelp.ithome.com.tw/upload/images/20161221/20103426gqVP2Jtjoc.png](http://ithelp.ithome.com.tw/upload/images/20161221/20103426gqVP2Jtjoc.png)




接著在JavaScriptClient調用方法時

原本也是第一個字母要小寫

但同樣的如果我們在該HubMethod加上`HubMethodNameAttribute`，如下圖


![http://ithelp.ithome.com.tw/upload/images/20161221/20103426cxHFUlCKAy.jpg](http://ithelp.ithome.com.tw/upload/images/20161221/20103426cxHFUlCKAy.jpg)




同樣的也搞定了!!


![http://ithelp.ithome.com.tw/upload/images/20161221/20103426LqzSEJKurF.png](http://ithelp.ithome.com.tw/upload/images/20161221/20103426LqzSEJKurF.png)



當然...Hub也可以配合interface一起用

就只是把原本的dynamic改為interface使用，如下圖


![http://ithelp.ithome.com.tw/upload/images/20161221/201034260qnMNY5tvM.jpg](http://ithelp.ithome.com.tw/upload/images/20161221/201034260qnMNY5tvM.jpg)



但這樣就只能使用介面有宣告的方法

講到這邊一定會有人好奇可不可以放類別呢!?

答案是當然不行...雖然如下圖看起來好像可以


![http://ithelp.ithome.com.tw/upload/images/20161221/20103426qbpcRsjgOC.jpg](http://ithelp.ithome.com.tw/upload/images/20161221/20103426qbpcRsjgOC.jpg)



**BUT** **BUT** **BUT** **!!**

當你執行時會遇到下面這個


![http://ithelp.ithome.com.tw/upload/images/20161221/201034269Z60OJIxwN.jpg](http://ithelp.ithome.com.tw/upload/images/20161221/201034269Z60OJIxwN.jpg)



套一段MSDN上寫的


![http://ithelp.ithome.com.tw/upload/images/20161221/20103426UxJSeZBE3v.jpg](http://ithelp.ithome.com.tw/upload/images/20161221/20103426UxJSeZBE3v.jpg)


`where T : class`在這邊指的應該是介面而已

玩到這邊一定還有人好奇....

那SignalR的方法可以傳遞物件嘛!?

來來來!!馬上做個匿名物件傳遞給你看!!，方法如下圖


![http://ithelp.ithome.com.tw/upload/images/20161221/20103426xsh5afz1Wn.jpg](http://ithelp.ithome.com.tw/upload/images/20161221/20103426xsh5afz1Wn.jpg)



測試一下，成功!!


![http://ithelp.ithome.com.tw/upload/images/20161221/201034263n62JGI35D.png](http://ithelp.ithome.com.tw/upload/images/20161221/201034263n62JGI35D.png)
