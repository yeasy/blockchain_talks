## 答疑解惑

**问：预入库模式下，共识的内容是 DB 日志?**

答：不是。预入库还是我们接口的定义的格式，预入库主要解决的时有些时候sql 版本问题会失败，所以算是尝试下。

**问：是否支持事务？如何解决 SQL 类似回滚这样操作的？**

答：是有条件的，必须配置本地传统数据库，不能有其他分区节点有对同样数据进行修改的请求。我们会在单个的 SQL 操作后附加一个合并的一组操作来通知传统数据库一个事务的 commit 或者没有 commit。

**问：区块链平台和共识算法采用的是哪种？**

答：目前我们采用的是 ripple 的 RPCA。共识算法我们提供模块化，供用户选择。