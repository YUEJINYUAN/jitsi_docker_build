##视频服务

使用注意事项：


1、第一个是准备好的容器，复制到服务器之后【主机需要保证有docker服务】，使用命令docker-compose up -d。


2、创建好之后可以在https://localhost:8443或者http：//localhost:8000访问。{可能会有几分钟的无法响应，之后就能正常使用，部署成功之后重启服务器不会有几分钟无法响应的问题。}


3、使用下面的config.js 和 interface_config.js覆盖目录（上面的命令执行后会自动创建）~/.jitsi—meet-cfg/web/下的文件【这部分做了预先处理，消除服务端的水印和修改默认语言为中文】。


4、备份~/.jitsi—meet-cfg/到某个位置（为下一步服务）


5、重启事项：当服务端出现问题需要重启时，为了保证服务器不会有用户滞留痕迹问题【当用户在通话而服务器宕机了，服务器重启时该房间的数据使得用户仍然在房间里】，需要恢复第四步保存的文件夹（重置服务器房间内的数据）


6、开发事项：jitsi服务器全部由docker实现，如果有需要改动的部分，主要参考上述两个js文件（在~/.jitsi-meet-cfg的web目录下），有样式改变需求也可以进入web的容器（docker），而容器与宿主机的共享文件夹为~/.jitsi-meet-cfg，以提供修改css的可能。


7、外部调用：通常我们以外部调用的方式使用该web服务，外部调用的api网址为：
https://github.com/jitsi/jitsi-meet/blob/master/doc/api.md
以上提供的myextraweb是使用外部调用api的简单样例，需要查看效果的，可以键入命令docker run -it 1084372027/jitsi_testweb /bin/bash
【记得修改index.html的domain为服务的正确IP地址】
外部调用允许覆盖上述两个服务端的默认js配置，具体参考api或者样例。
有需要也可以直接修改上述两个js文件（记得备份保存）。


8、关于ios/android开发部分，请参考官方网站
https://github.com/jitsi/jitsi-meet
的介绍，以上全部基于服务器&pc+web客户端。


创建者：YUEJINYUAN



















