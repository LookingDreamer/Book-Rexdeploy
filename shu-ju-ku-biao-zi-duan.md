# 数据库表约束和解释

数据库表主要包含以下7个表

| 表名 | 说明 |
| :--- | :--- |
| pre\_auto\_configure | 配置模板关联表 |
| pre\_auto\_template\_vars | 配置模板表 |
| pre\_bwzzbmonitor | 监控信息表 |
| pre\_deploy\_manage | 自动发布信息记录表 |
| pre\_deploy\_status | 自动发布状态表 |
| pre\_external\_server\_detail | CMDB主机配置外网表 |
| pre\_server\_detail | CMDB主机配置表 |



这7个表中最关键的是CMDB主机配置表，所有名字服务关联的自动发布等都从这个表中取关键信息。

