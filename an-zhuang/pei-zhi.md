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

这个配置的文件格式为yml，主要存放环境变量，认证相关配置，并发配置以及日志以及发布等相关配置，你也可以自定义其他环境变量。

* 配置文件格式如下: 

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

* 主配置解释

```
   ##认证相关配置
   # key_auth=true时,为秘钥认证. pass_auth=true,为密码认证。秘钥认证和密码认证不能同时为真;
   # 当key_auth=true时,仅支持秘钥认证密码为空的情况
   # user:用户名 password:密码 private_key:私钥文件 public_key:公钥文件 
   # global_sudo:是否开启sudo,on为开启,off为关闭 sudo_password:sudo时密码 
   # timeout:SSH超时时间  
   # max_connect_retries:SSH失败时最大连接尝试次数 
   
   # logfile:日志文件
   # groups_file:IP分组文件 
   # parallelism:最大的并发数量
          
   # table:主机信息表(废弃)  
   # monitor_table:监控数据表(暂时不使用)  
   # rerite_info_table:是否写入json文件(暂时不使用)  
   # default_jsonfile:默认json串存储文件(暂时不使用) 
   
   ## 基于名字服务的自动发布相关配置项      
   # table_string:数据库初始化主机信息要查询的字段(不要轻易修改)  
   # softdir:待发布应用目录 
   # configuredir:待发布配置目录  
   # local_prodir:远程同步应用目录  
   # local_confdir:远程同步配置目录  
   # temp:应用发布时临时目录   
   # backup_dir:发布应用时,当数据库字段中backupdir_same_level为0时,且当配置目录在应用目录时,备份该应用程序的所在目录
   # baseapp_dir:发布应用时,当数据库字段中deploydir_same_level为0时,即是待发布目录的目录(发布目录不能和发布目录同层级),比如你的应用在webapp下,你的新的发布应用时不能再webapp下面,因为当你放在webapp下面时就相当于会启动2个app,所以需要另外的发布目录
   # download_all:是否下载所有的目录(暂时不使用,不能为空)  
   # is_link: 是否是软链接(暂时不使用,不能为空)  
   # is_stop:是否停止应用 (暂时不使用,不能为空)  
   # is_start:是否启动应用(暂时不使用,不能为空)  
   # download_record_log:下载应用的日志记录  
   # deploy_config_table:主机详细配置文件数据表(重要)  
   # deploy_record_table:发布时记录数据表 
   # deploy_status_table:发布时状态数据表  
   # external_status:是否开启外网表,当开启外网表时,需要你将新建 复制主机详细配置文件数据表,同时将内网地址和外网地址交换,当external_status为true时,deploy_config_table将不起作用,读取外网表
   # external_deploy_config_table:  主机详细配置文件数据表(外网表)
   # list_all_task_status:是否要打印所有的模块信息,如果不为false,则答应所有的模块信息。为false时,则打印list_task所列出的模块   
   # list_task:执行rex -T 要显示的模块  
   # service_start_retry:启动服务失败时的尝试次数  
   # rsync_log_stdout:是否显示传输包的进度和传输速度
```

### 分组配置文件: `config/ip_lists.ini`

## 数据库配置



