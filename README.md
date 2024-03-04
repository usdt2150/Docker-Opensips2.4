# Docker-Opensips2.4

使用说明
这是基于官方opensips 2.4镜像添加了mysql模块以及rest_client模块制作的镜像，用此镜像可以连接mysql控制opensip注册用户、查看通话记录以及通话时对INVITE（邀请）、ACK(接通)、BYE（挂断）、CANCEL（取消）事件进行监听调用http接口访问外部业务
配置文件opensips.cfg 内容如下，请保存到ubuntu位置/docker/opensips/opensips.cfg，搜索标签CUSTOMIZE ME定位到需要配置的地方，根据实际情况修改
