# TeamX
基于SolonJT 引擎构建的开发团队小工具，主要功能有：

* Wiki（企业词条）
* Planned（项目计划和个人日志）
* Issues（问题管理，如缺陷、需求...）




#### 服务器版（要求 Oracle JDK 9,10,11 和 Mysql 5.6+）

```
java -jar jt.jar -add=teamx.noear -home=/ -init=/teamx/__init

#
# 管理员账号：admin 密码：1234
#
```

#### 个人版（要求 Oracle JDK 9,10）

```
java -jar jtl.jar -add=teamx.noear -home=/teamx/ -title=TeamX

#
# 不需要账号，直接进入。算是个人版（可以写成脚本文件启动）
#
```

