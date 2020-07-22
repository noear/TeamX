
## TeamX 使用docker进行部署

#### 一、创建持久化目录，并放置文件

```shell
$ mkdir -p /data/sss/teamx

$ # 然后把 jtl.jar 或 jt.jar 放到 /data/sss/teamx/ 下面
```



#### 二、拉取 docker openjdk11 镜像

```shell
$ docker pull adoptopenjdk/openjdk11
```

#### 三、运用 docker run

```shell
$ docker run -d \                  # 将 -d  换成 -it --rm 可用于测试
    --name teamx \                 # 命名
    --privileged=true \            # 避免防火墙问题
    -v /data/sss/teamx:/teamx  \   # 持久化映射
    -p 8080:8080 \                 # 端口映射
    adoptopenjdk/openjdk11 \       # 使用镜像
    java -jar /teamx/jtl.jar \     # 运行java -jar 命令
    -add=teamx.noear \         # solonjt 要安装的插件，即 TeamX
    -init=/teamx/__init \      # solonjt 要运行的初始化脚一
    -model=2 \                 # solonjt 要运行的模式
    -server.port=8080          # solonjt 要运行的端口
            
$ # 运行上面命令前：1.要把注释去掉；2.把多行前面的空隔去掉。

$ # 成功运行后，等个10秒；可以在浏览器里打开首页：http://x.x.x.x:8080

```

附：单行运行代码

```shell
$ docker run -it --rm --name teamx  -v /data/sss/teamx:/teamx  --privileged=true   -p 8080:8080   adoptopenjdk/openjdk11  java -jar /teamx/jtl.jar -add=teamx.noear -home=/ -init=/teamx/__init -model=2 -server.port=8080
```

