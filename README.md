# TeamX
基于 SolonJT 平台构建的开发团队小工具，主要功能有：

* Wiki（企业词条）
* Planned（项目计划和个人日志）
* Issues（问题管理，如缺陷、需求...）


引擎包及大小说明：
* bin/jt.jar （5m，服务版，需要MySQL配合）
* bin/jtl.jar （6.3m，个人版）



#### 服务器版（要求 Oracle JDK 9,10,11 和 Mysql 5.6+）

```
java -jar jt.jar -add=teamx.noear -home=/ -init=/teamx/__init

#
# 1.然后在浏览器里打开：http://x.x.x.x:8080
# 2.按提示配置数据库（提前准备个空的库；账号要有建表权限）
#
# 管理员账号：admin 密码：1234
#
```

#### 个人版（要求 Oracle JDK 9,10）

```
java -jar jtl.jar -add=teamx.noear -home=/teamx/ -title=TeamX

#
# 启动后会自动打开首页；不需要账号，直接进入。
#
# 可以写成脚本文件启动
#
```

#### 源码在哪里？

* SolonJT 是个另类的FaaS系统， 集成了包的管理和发布
* TeamX 的源码，发布在 SolonJT 的中央仓库里


#### 演示地址

* http://teamx.noear.org/

