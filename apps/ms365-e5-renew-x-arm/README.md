# 使用说明
Email通知功能(推荐,20230402更新。)

   - email通知版本主要实现了检测部署的账号是否全部都正常运行。该版本会每天定时发送邮件来通知是否账号全部运行。
   
   - 该版本内测使用了一个月，目前没发现什么太大的问题。
   
   - 关于修改通知邮箱。推荐使用163邮箱。修改-e后面的内容，其中 sender = '123456@163.com'为发送邮件的邮箱。
      receiver = '789456@qq.com'为接收邮件的邮箱。其中pwd为发送邮箱的授权码。授权码获取方式为，进入网页版163邮箱，点击设置，点击POP3/SMTP/IMAP，点击授权密码管理，新增授权码即可。
      adminpwd为web界面的登录密码。
   
   - 关于版本。已发布x86机器和arm64v8，其他版本需要可以发issue，会尽快补充。
   - 发送邮件的日志的位置:/opt/test.log
   - 发送邮件的时间为每天18点。可以通过crontab命令修改。
   
   - x86版本：


    docker run -d -p 1066:1066 -e TZ=Asia/Shanghai -e sender="by123@163.com" -e pwd="UNxxxxxxxxN" -e receiver="4dddqqq9dd6@qq.com"  -e adminpwd="123456" hanhongyong/ms365-e5-renew-x:pubemail

   - arm64v8版本：


    docker run -d -p 1066:1066 -e TZ=Asia/Shanghai -e sender="byxxx@163.com" -e pwd="UxxxxWWN" -e receiver="41xxxxx@qq.com" -e adminpwd="123456" hanhongyong/ms365-e5-renew-x:arm64v8


# 原始相关
***
本文是基于作者SundayRX提出的E5 调用API续订服务：Microsoft 365 E5 Renew X的基础上提出的Docker版本的E5调用API续订服务。

基础的账号注册等过程见SundayRX的博客：https://blog.csdn.net/qq_33212020/article/details/119747634


**本项目主要为学习Dockerfile和Docker的部署使用，禁止将此项目进行商业化，仅推荐学习使用。**


## 支持版本

|    CPU架构     | 是否支持 |
| :------------: | :------: |
|  linux/amd64   |    是    |
|  linux/arm64   |    是    |
|  linux/arm/v7  |    是    |
|  linux/arm/v5  |    是    |
|  Linux/arm64/v7  |    是    |
