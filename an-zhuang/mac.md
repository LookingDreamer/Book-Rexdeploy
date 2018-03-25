# Mac平台安装

1. 第一步 安装rex依赖

* 方法一

```
$ sudo port install libssh2 perl5
$ curl -L https://get.rexify.org | perl - --sudo -n Rex
```

* 方法二 

```
$ sudo brew install libssh2 perl5
$ curl -L https://get.rexify.org | perl - --sudo -n Rex
```

* 方法三

```
cpanm Rex
```

 2. 第二步 安装相关依赖

```
cpanm DBI DBD::mysql Mojo::JSON JSON:PP
```

 3. 初始化模块

```
# git clone https://gitee.com/lookingdreamer/RexDeployV3.git

# perldoc -l Rex::Commands #查询Rex模块安装路径
/usr/local/Cellar/perl518/5.18.2/lib/site_perl/5.18.2/Rex/Commands.pm
对应Rex模块的路径为 /usr/local/Cellar/perl518/5.18.2/lib/site_perl/5.18.2/Rex
# cd RexDeployV3
# \cp src/Rex/* /usr/local/Cellar/perl518/5.18.2/lib/site_perl/5.18.2/Rex/ -ar
```



