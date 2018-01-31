這邊來跟大家分享一些**JavaScript Client**上的事件



首先第一個是`starting`當連線剛開始的時候


![http://ithelp.ithome.com.tw/upload/images/20161227/20103426RzmYiCSaki.jpg](http://ithelp.ithome.com.tw/upload/images/20161227/20103426RzmYiCSaki.jpg)




再來是`received`只要收到DATA後就會觸發


![http://ithelp.ithome.com.tw/upload/images/20161227/20103426h3DoJNC0nA.jpg](http://ithelp.ithome.com.tw/upload/images/20161227/20103426h3DoJNC0nA.jpg)



![http://ithelp.ithome.com.tw/upload/images/20161227/20103426kR6bROWfKY.jpg](http://ithelp.ithome.com.tw/upload/images/20161227/20103426kR6bROWfKY.jpg)




接著是`connectionSlow`如其名，會在連線變慢時觸發

```
$.connection.hub.connectionSlow(function () {
    //簡單明瞭的方法名稱吧!!這很難測...所以略過!!
});
```



`reconnecting`意外斷線時會觸發


![http://ithelp.ithome.com.tw/upload/images/20161227/20103426CVKvkrOxw9.jpg](http://ithelp.ithome.com.tw/upload/images/20161227/20103426CVKvkrOxw9.jpg)



`reconnected` 重新連接上後會觸發


![http://ithelp.ithome.com.tw/upload/images/20161227/20103426YzNC7cZlyl.jpg](http://ithelp.ithome.com.tw/upload/images/20161227/20103426YzNC7cZlyl.jpg)



`stateChanged`只要狀態有改變就會觸發


`disconnected`只要斷線就會被觸發


![http://ithelp.ithome.com.tw/upload/images/20161227/20103426zLEEeHEi6z.jpg](http://ithelp.ithome.com.tw/upload/images/20161227/20103426zLEEeHEi6z.jpg)


