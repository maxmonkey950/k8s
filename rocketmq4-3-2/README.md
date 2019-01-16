# README
## please README
## This is my k8s config!
### auther hxx
- 2019.1.16 add the rocketmq config for k8s. 
- 增加brokerIP选项,在本地显式的指定brokerIP与listen的端口。可解决本地测试时不能连接到broker的真实ip问题,通常会出现在云环境与虚拟环境中,broker会注册自己的私有网络ip以致于开发测试连接失败
## 你可以通过web UI查看rocketmq的状态,启动命令如下

```docker run -e "JAVA_OPTS=-Drocketmq.namesrv.addr=xxx.xxx.xxx.xxx:9876 -Dcom.rocketmq.sendMessageWithVIPChannel=false" -p 8088:8080 -d --name rmq-dashboard2 styletang/rocketmq-console-ng```

运行之后请再浏览器中查看  http://localhost:8088

注:localhost为宿主机ip,xxx.xxx.xxx.xxx请填写namesrv的地址，只要是broker能访问到的地址。此容器只包含webUI

- how to run it?

```kubectl apply -f rocketmq4-3-2.yaml```

if you want use the special port, you need configure "rocketmq4-3-2.yaml" with svc.

