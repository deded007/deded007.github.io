push到Bitbucket通知Jenkins自動佈署
=========================== 

bitbucket 網站設定
----------------

### 1．bitbucket網站上設定hook：
(1)先找到目标项目的配置页面，然后在配置下看到 Webhooks，选择 “Add Webhooks"。
![image](https://deded007.github.com/img/bit_hook.png)

→URL 的格式是 YOUR_JENKINS_URL/bitbucket-hook/ (最后的这个斜杠不能省掉)。如此保存就可以了。(http://IP:8080/bitbucket-hook/)
→成功可試著push到bitbucket上，在bitbucket上在剛剛的webhook裡可以看傳送到url的歷史記錄，actions→view requests，以及
   在jenkins的/log/也可以看bigbucket推送過來的request
   
   
jenkins 設定
----------------
### 2．安裝外掛：Bitbucket Plugin

### 3．job中「原始碼管理」→「git」→「Repositories url」要設定要監聽的bitbucket url( https://bitbucket.org/USERNAME/PROJ.git )，如果是私有repository要設定credentials

### 4．job中「建置觸發程序」→「Build when a change is pushed to BitBucket」打勾，
之後jenkins收到bitbucket傳來的request會觸發有打勾的所有job並且job設定的repository url是監聽的url




