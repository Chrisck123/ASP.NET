上一篇我們完成了CentOS與Hyper-V的安裝

今天我們就開始Redis的安裝吧

要安裝Redis首先我們得先裝幾個工具

net-tools，wget，gcc，tcl

指令如下!!

`yum -y install net-tools wget gcc tcl`


![http://ithelp.ithome.com.tw/upload/images/20170107/20103426riOzT5PunA.jpg](http://ithelp.ithome.com.tw/upload/images/20170107/20103426riOzT5PunA.jpg)



安裝完畢後...我們就開始下載壓縮檔吧!!

`wget http://download.redis.io/releases/redis-3.0.7.tar.gz`


![http://ithelp.ithome.com.tw/upload/images/20170107/20103426cS1HupbJKT.jpg](http://ithelp.ithome.com.tw/upload/images/20170107/20103426cS1HupbJKT.jpg)



下載完成


![http://ithelp.ithome.com.tw/upload/images/20170107/20103426dlVATpscNT.jpg](http://ithelp.ithome.com.tw/upload/images/20170107/20103426dlVATpscNT.jpg)



再來就是解壓縮了

`tar xzf redis-3.0.7.tar.gz`


![http://ithelp.ithome.com.tw/upload/images/20170107/20103426yvhwvqPNp6.jpg](http://ithelp.ithome.com.tw/upload/images/20170107/20103426yvhwvqPNp6.jpg)



接著先進入Redis的目錄底下


![http://ithelp.ithome.com.tw/upload/images/20170107/20103426Yijcp3gZOv.jpg](http://ithelp.ithome.com.tw/upload/images/20170107/20103426Yijcp3gZOv.jpg)



編譯一下

`make`


![http://ithelp.ithome.com.tw/upload/images/20170107/20103426dihlTpl8M1.jpg](http://ithelp.ithome.com.tw/upload/images/20170107/20103426dihlTpl8M1.jpg)



接著我們先來測試一下(謎之音：還沒安裝就搞測試一定出錯)

`make test`


![http://ithelp.ithome.com.tw/upload/images/20170107/20103426wvHpXhp6Il.jpg](http://ithelp.ithome.com.tw/upload/images/20170107/20103426wvHpXhp6Il.jpg)



好...要先安裝他!!

`make install`


![http://ithelp.ithome.com.tw/upload/images/20170107/201034268vQAoeNcRs.jpg](http://ithelp.ithome.com.tw/upload/images/20170107/201034268vQAoeNcRs.jpg)



再來測試一次(謎之音：安裝好了會出錯就會很怪怪的唷!!)


![http://ithelp.ithome.com.tw/upload/images/20170107/20103426aA4alf6xDe.jpg](http://ithelp.ithome.com.tw/upload/images/20170107/20103426aA4alf6xDe.jpg)



先來建立個相關的目錄

```
mkdir /etc/redis
mkdir /var/redis
```

建立完畢後，再來複製設定檔!!

`cp ~/redis-3.0.7/redis.conf /etc/redis/redis_6379.conf`

複製完後我們來建立一下工作的目錄

`mkdir /var/redis/6379`

再來我們進去文件裡修改一下設置

`vi /etc/redis/redis_6379.conf`


![http://ithelp.ithome.com.tw/upload/images/20170107/20103426sXIsEswPFT.jpg](http://ithelp.ithome.com.tw/upload/images/20170107/20103426sXIsEswPFT.jpg)




![http://ithelp.ithome.com.tw/upload/images/20170107/20103426hW5qcFp4cN.jpg](http://ithelp.ithome.com.tw/upload/images/20170107/20103426hW5qcFp4cN.jpg)




![http://ithelp.ithome.com.tw/upload/images/20170107/20103426RxfAEIG3Jv.jpg](http://ithelp.ithome.com.tw/upload/images/20170107/20103426RxfAEIG3Jv.jpg)

再來我們重新設定一下防火牆

```
firewall-cmd --permanent --add-port=6379/tcp
firewall-cmd --reload
```


![http://ithelp.ithome.com.tw/upload/images/20170107/20103426EF0FmLD8YN.jpg](http://ithelp.ithome.com.tw/upload/images/20170107/20103426EF0FmLD8YN.jpg)



再來我們把redis設定為開機就啟始!!

先進去`vi /lib/systemd/system/redis_6379.service`接著照下圖設定


![http://ithelp.ithome.com.tw/upload/images/20170107/20103426wcmSNJCBYz.jpg](http://ithelp.ithome.com.tw/upload/images/20170107/20103426wcmSNJCBYz.jpg)



再來我們註冊Redis的服務

```
systemctl daemon-reload
systemctl enable redis_6379.service
```


![http://ithelp.ithome.com.tw/upload/images/20170107/20103426kvJLrXy2KM.jpg](http://ithelp.ithome.com.tw/upload/images/20170107/20103426kvJLrXy2KM.jpg)



再來啟用他!!

`systemctl start redis_6379.service`


![http://ithelp.ithome.com.tw/upload/images/20170107/20103426hTkzdTb71c.jpg](http://ithelp.ithome.com.tw/upload/images/20170107/20103426hTkzdTb71c.jpg)



再來ping一下看看有沒有成功!!

`redis-cli ping`


![http://ithelp.ithome.com.tw/upload/images/20170107/20103426LSSn57apu7.jpg](http://ithelp.ithome.com.tw/upload/images/20170107/20103426LSSn57apu7.jpg)



![http://ithelp.ithome.com.tw/upload/images/20170107/20103426VtZtEIC7gU.jpg](http://ithelp.ithome.com.tw/upload/images/20170107/20103426VtZtEIC7gU.jpg)



好了!!到這裡我們終於安裝完Redis了

下一篇就可以開始連線嚕!!
