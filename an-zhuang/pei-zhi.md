# 配置

配置主要分为2类，1类是文件类配置文件，1类是数据库配置

## 配置文件

配置文件主要有2个   `config/config.yml`和`config/ip_lists.ini`

```
(dev) ➜  RexDeployV3 git:(master) tree -L 2 config
config
├── config.yml
└── ip_lists.ini
```

### 主配置文件: `config/config.yml`

这个配置的文件格式为yml，主要存放环境变量，认证相关配置，并发配置以及日志以及发布等相关配置.

配置文件格式如下: 

```
#主配置文件
#环境变量设置,dev/uat/com等不同的环境变量设置
 db: #这个配置项暂未使用到
   dbname: "autotask"
   dbhost: "127.0.0.1"
   dbuser: "root"
   dbpassword: "root"
   dbport: "3306"
   apitable: "pre_host_zzb"
 env: #环境变量设置,当key设置为dev,则读取dev下的所有配置。当key设置为prod,则读取prod下的所有配置。
   key: "dev"
#开发环境配置
 dev:
   key_auth: "false"
   pass_auth: "true"  
   user: "autotask"
   password: "autotask"
   ......
#预生产环境配置
 uat:
   key_auth: "true"
   pass_auth: "false"  
   user: "autotask"
   password: ""
   ......
#生产环境配置
 prod:
   key_auth: "true"
   pass_auth: "false"  
   user: "autotask"
   password: ""
   ......
```

### 分组配置文件: `config/ip_lists.ini`

## 数据库配置



