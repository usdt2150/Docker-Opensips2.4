# Docker-Opensips2.4

使用说明
这是基于官方opensips 2.4镜像添加了mysql模块以及rest_client模块制作的镜像，用此镜像可以连接mysql控制opensip注册用户、查看通话记录以及通话时对INVITE（邀请）、ACK(接通)、BYE（挂断）、CANCEL（取消）事件进行监听调用http接口访问外部业务
配置文件opensips.cfg 内容如下，请保存到ubuntu位置/docker/opensips/opensips.cfg，搜索标签CUSTOMIZE ME定位到需要配置的地方，根据实际情况修改


数据库文件
其中表acc为通话成功记录表，记录成功的INVITE和BYE。
missed_calls记录失败的INVITE记录，可以是拨打方Cancel的和忙线（具体看sip_reason）。

subscriber表记录用户名和密码，在这可以手动新增客户
数据库文件下载：[opensips2.4_db](https://raw.githubusercontent.com/atorzhang/Document/main/DB/db_opensips2.4_mysql57.nb3)

获取镜像
>docker pull 459741134/opensips2.4_with_mysql_rest

运行镜像
>docker run -d -it --name sip -p 5060:5060/udp -v /docker/opensips/opensips.cfg:/etc/opensips/opensips.cfg opensips/opensips
