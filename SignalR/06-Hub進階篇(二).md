在這一篇來跟各位介紹一下

我們該如何決定要傳給那些Client(總不能每次都全部發送吧....)

我們先預設目前要呼叫的方法是 `.Alert(msg)`


`Clients.All.Alert(msg)` 

=> 這東西...就是全部發送!!先前的範例都是使用他~


`Clients.Caller.Alert(msg)` 

=> 這東西...就是誰調用hub method就傳給誰!!


`Clients.Others.Alert(msg)` 

=> 這東西...就是除了調用hub method以外的都發


`Clients.Client(Context.ConnectionId).Alert(msg)` 

=> 某個特定的ConnectionId(但這例子是指...誰呼叫hub就誰)


`Clients.AllExcept(params string[] excludeConnectionIds).Alert(msg)` 

=> 除了excludeConnectionIds以外都發


`Clients.Group(groupName).Alert(msg)` 

=> 發給某個特定的群組



但...這邊要說一下你得先使用下面的方法 把群組加進去...才能啟用

`Groups.Add(string connectionId, string groupName)`



`Clients.Group(string groupName, params string[] excludeConnectionIds).Alert(msg)` 

=> 就是發給某個群組，但是卻不要發給群組內的excludeConnectionIds的


`Clients.OthersInGroup(groupName).Alert(msg)`

=> 就是某個群組內除了調用hub method其他的都發


`Clients.User(userid).Alert(msg)` 

=> 這裡的userid就是`IPrincipal.Identity.Name` 這個我們會在下一篇討論


`Clients.Clients(IList<string> connectionIds).Alert(msg)` 

=> 發給很多個ConnectionId!!


`Clients.Groups(GroupIds).Alert(msg)` 

=> 類似上面....傳給很多個群組!!

經過上述的說明.....希望各位對於SignalR Hub在於該發送訊息給那些Client可以有初步的了解!!





