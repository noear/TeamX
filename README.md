# TeamX

### 介绍

TeamX 是基于 SolonJT 平台构建的团队管理小工具，主要功能有：

* Wiki（团队词条，用于写MD格式接口文档也行...）
* Planned（项目计划 和 个人日志）
* Issues（问题管理，如缺陷、需求...）




引擎包及大小说明：
* bin/jt.jar （5m，服务器版，需要MySQL配合）
* bin/jtl.jar （6.3m，单机版）



支持环境：

* jdk9, jdk10, jdk11, jdk12, jdk13, jdk14



### 使用

#### 一、服务器模式安装和使用（即多人使用）

* 使用服务器版启用（需要Mysql 5.6+ 配合）

```
java -jar jt.jar -add=teamx.noear -home=/ -init=/teamx/__init
```

* 或，使用单机版的服务器模式启用（这个简单......!!!）

```
java -jar jtl.jar -add=teamx.noear -home=/ -init=/teamx/__init  -model=2 -server.port=8080
```

* 然后

1. 在浏览器里打开：http://x.x.x.x:8080
2. 按界面提示配置数据库（提前准备个空的库；账号要有建表权限）*** [单机版跳过]
3. 管理员账号：admin  密码：1234
4. 其它账号，可自行注册或在后台添加



#### 二、个人模式（即单人使用）

* 使用单机版的桌面模式启动（需要JavaFx支持）

```
#基于JavaFx运行，效果像本地应用
#
java -jar jtl.jar -add=teamx.noear -home=/teamx/ -title=TeamX

#jdk11+ 需要通过 --module-path --add-modules 添加JavaFx的包
```

* 或，使用单机版的浏览器模式启动

```
java -jar jtl.jar -add=teamx.noear -home=/teamx/ -title=TeamX -model=1
```

* 然后

> 个人模式启动后会自动打开首页；不需要账号，直接进入。



#### 三、其它

1. 源码在哪里？
   * SolonJT 是个另类的FaaS系统， 集成了包的管理和发布(代码存数据库里的)
   * TeamX 的源码，发布在 SolonJT 的中央仓库里

2. 演示地址
   * http://teamx.noear.org/
   * 测试账号：test  密码：1234 （也可以自己注册个）

