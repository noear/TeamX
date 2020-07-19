# TeamX 专为中小团队思考的...团队协作工具

### 一、介绍

TeamX，功能不强但绝对小巧；基于 SolonJT 平台构建。主要功能有：

* Wiki（团队词条，用于写接口文档也行...）
* Planned（项目计划 和 个人日志）
	* 比较兄弟产品，区别会很大；基于表格组件定制
* Issues（问题管理，如缺陷、需求...）
	* 比BugFree还要简单，更清爽
* 通知（需要一定的设置）
  * 支持钉钉或QQ



引擎包及大小说明：
* bin/jt.jar （5m，服务器版，需要MySQL配合）
* bin/jtl.jar （6.3m，单机版）



支持环境：

* jdk9, jdk10, jdk11, jdk12, jdk13, jdk14



体验地址：

* http://teamx.noear.org/
* 测试账号：test  密码：1234 （也可以自己注册个）



### 二、安装

#### （一）服务器模式安装和使用（即多人使用）

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



#### （二）个人模式（即单人使用）

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



### 三、使用与教程视频

* 1.安装：[https://www.bilibili.com/video/BV1Tz4y1Q7YF/](https://www.bilibili.com/video/BV1Tz4y1Q7YF/)
* 2.Wiki的使用：[https://www.bilibili.com/video/BV1vk4y1B7qr/](https://www.bilibili.com/video/BV1vk4y1B7qr/)
* 3.Planned的使用：[https://www.bilibili.com/video/BV1si4y137QP/](https://www.bilibili.com/video/BV1si4y137QP/)
* 4.Issues的使用：[https://www.bilibili.com/video/BV1k54y1S7wZ/](https://www.bilibili.com/video/BV1k54y1S7wZ/)





### 四、其它

1. 源码在哪里？
   * SolonJT 是个另类的FaaS系统， 集成了包的管理和发布（代码存数据库里的）
   * TeamX 的源码，发布在 SolonJT 的中央仓库里（安装即是拉取）

2. 启动参数都是什么意思？
   * -add= 启动后加载的插件（第一次，会从中央仓库获取）
   * -init= 启动后执行的初始化代码（需要插件开发方提供，也可以不需要）
   * -home= 启动后或安装后打开的地址
   * -title= 设定系统标题
   * -model= 运行模式：0,1,2（单机版专属）
     * 0 个人桌面模式，默认
     * 1 个人浏览器模式
     * 2 多人模式
   * -rem= 启动后移除插件（单机版专属，服务器版可进入扩展中心手动管理）
   * -udp= 启动后更新插件（单机版专属）