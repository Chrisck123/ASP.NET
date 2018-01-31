首先我們來看一下關於Client與Hub Server的連線

`$.connection.hub.start();`

本身是一個非同步的方法!

不信!?看下圖!!


![http://ithelp.ithome.com.tw/upload/images/20161226/20103426TSbMf8URfb.jpg](http://ithelp.ithome.com.tw/upload/images/20161226/20103426TSbMf8URfb.jpg)



所以當我們改用非同步的方法後一樣可以取到!!



![http://ithelp.ithome.com.tw/upload/images/20161226/20103426jOS8TLtxBd.jpg](http://ithelp.ithome.com.tw/upload/images/20161226/20103426jOS8TLtxBd.jpg)



接著我們再來加上失敗的方法!!


![http://ithelp.ithome.com.tw/upload/images/20161226/20103426llxIw2W5Ey.jpg](http://ithelp.ithome.com.tw/upload/images/20161226/20103426llxIw2W5Ey.jpg)



註解調當初`PostAuthenticateRequest`踹一下!!


![http://ithelp.ithome.com.tw/upload/images/20161226/20103426yzTaI7xf4l.png](http://ithelp.ithome.com.tw/upload/images/20161226/20103426yzTaI7xf4l.png)



接著我們也可以從JavaScript Client傳送QueryString給Hub Server

是在建立連線之前，如下圖~


![http://ithelp.ithome.com.tw/upload/images/20161226/201034265BO89dVhiK.jpg](http://ithelp.ithome.com.tw/upload/images/20161226/201034265BO89dVhiK.jpg)



測試一下，確實收到了!!


![http://ithelp.ithome.com.tw/upload/images/20161226/20103426XsU701co0f.png](http://ithelp.ithome.com.tw/upload/images/20161226/20103426XsU701co0f.png)



講到連線!!那當然一定要講一下如何設定SignalR JavaScript Client與Hub Server的連線模式

它們的連線模式一共有4種，分別是**"webSockets"，"foreverFrame"，"serverSentEvents"，"longPolling"**

設定連線模式就是在你連線時加入這四個內的參數(s)

`$.connection.hub.start({ transport: ['webSockets', 'longPolling'] })`

講到這邊我們順便來看看他預設的連線會用什麼!!


![http://ithelp.ithome.com.tw/upload/images/20161226/20103426q3YdWnU6WR.png](http://ithelp.ithome.com.tw/upload/images/20161226/20103426q3YdWnU6WR.png)



再來測試一下我們設定他的連線模式後


![http://ithelp.ithome.com.tw/upload/images/20161226/20103426tZ7P9gjCQC.png](http://ithelp.ithome.com.tw/upload/images/20161226/20103426tZ7P9gjCQC.png)



嗯看來多個的狀態下會選第一個!!

