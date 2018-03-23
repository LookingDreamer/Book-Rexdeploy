# windows平台安装

> rexdeploy原则上只要支持perl语言，就能直接使用。但我在Windows7上测试，在安装IO::Pty模块，安装失败。从官方的解析说该模块不支持Windows平台，所以在windows本机平台安装失败。Windows平台提供三种安装体验方式: `docker方式安装`，`Virtualbox+Vagrant`，`Virtualbox`。Virtualbox+Vagrant和Virtualbox差不多是一种安装方式，只是使用Virtualbox+Vagrant的安装方式便于在windows下进行二次开发。

相关工具和软件下载:
vagrant_2.0.2: https://download.osichina.net/tools/vagrant_2.0.2_x86_64.msi
Git-2.16.1.2: https://download.osichina.net/tools/Git-2.16.1.2-64-bit.exe
VirtualBox-5.2.6-120293: https://download.osichina.net/tools/VirtualBox-5.2.6-120293-Win.exe

## Docker方式安装

docker环境的安装，这里就不过过多介绍，不知道安装docker环境请撮: [https://get.daocloud.io/](https://get.daocloud.io/)

