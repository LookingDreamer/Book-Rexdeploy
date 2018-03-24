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

 3. 

