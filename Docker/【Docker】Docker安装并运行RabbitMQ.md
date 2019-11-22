##### 1 进入docker hub镜像仓库地址：https://hub.docker.com/

```
搜索rabbitMq，进入官方的镜像，可以看到以下几种类型的镜像；我们选择带有“mangement”的版本（包含web管理页面）
```
##### 2 我们拉取这个rabbitmq镜像

```
docker pull docker.io/rabbitmq:3.7.7-management
```
##### 3 拉取到镜像之后，我们直接启动

```
docker run -d --name rabbitmq3.7.7 -p 5672:5672 -p 15672:15672   -e RABBITMQ_DEFAULT_VHOST=my_vhost  -e RABBITMQ_DEFAULT_USER=admin -e RABBITMQ_DEFAULT_PASS=admin rabbitmq:3.7.7-management



说明：

-d 后台运行容器；

--name 指定容器名；

-p 指定服务运行的端口（5672：应用访问端口；15672：控制台Web端口号）；

-e 指定环境变量；（RABBITMQ_DEFAULT_VHOST：默认虚拟机名；RABBITMQ_DEFAULT_USER：默认的用户名；RABBITMQ_DEFAULT_PASS：默认用户名的密码）
```

##### 4 最后我们可以使用 ip:15672访问我们的web后台。账号密码都是我们设置的admin
