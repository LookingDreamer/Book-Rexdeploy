# Vagrant常用命令

* `vagrant box add` 添加box的操作
* `vagrant init` 初始化box的操作
* `vagrant up` 启动虚拟机的操作
* `vagrant ssh` 登录虚拟机的操作

Vagrant还包括如下一些操作：

* `vagrant box list`

	显示当前已经添加的box列表

		$ vagrant box list
		base (virtualbox)

* `vagrant box remove`

	删除相应的box

		$ vagrant box remove base virtualbox
		Removing box 'base' with provider 'virtualbox'...

* `vagrant destroy`

	停止当前正在运行的虚拟机并销毁所有创建的资源

		$ vagrant destroy
		Are you sure you want to destroy the 'default' VM? [y/N] y
		[default] Destroying VM and associated drives...

* `vagrant halt`  

	关机

		$ vagrant halt
		[default] Attempting graceful shutdown of VM...

* `vagrant package`

	打包命令，可以把当前的运行的虚拟机环境进行打包

		$ vagrant package
		[default] Attempting graceful shutdown of VM...
		[default] Clearing any previously set forwarded ports...
		[default] Creating temporary directory for export...
		[default] Exporting VM...
		[default] Compressing package to: /Users/astaxie/vagrant/package.box

* `vagrant plugin`

	用于安装卸载插件

* `vagrant provision`

	通常情况下Box只做最基本的设置，而不是设置好所有的环境，因此Vagrant通常使用Chef或者Puppet来做进一步的环境搭建。那么Chef或者Puppet称为provisioning，而该命令就是指定开启相应的provisioning。按照Vagrant作者的说法，所谓的provisioning就是"The problem of installing software on a booted system"的意思。除了Chef和Puppet这些主流的配置管理工具之外，我们还可以使用Shell来编写安装脚本。

	例如： `vagrant provision --provision-with chef`

* `vagrant reload`  

	重新启动虚拟机，主要用于重新载入配置文件

		$ vagrant reload
		[default] Attempting graceful shutdown of VM...
		[default] Setting the name of the VM...
		[default] Clearing any previously set forwarded ports...
		[default] Creating shared folders metadata...
		[default] Clearing any previously set network interfaces...
		[default] Preparing network interfaces based on configuration...
		[default] Forwarding ports...
		[default] -- 22 => 2222 (adapter 1)
		[default] Booting VM...
		[default] Waiting for VM to boot. This can take a few minutes.
		[default] VM booted and ready for use!
		[default] Setting hostname...
		[default] Mounting shared folders...
		[default] -- /vagrant

* `vagrant resume`

	恢复前面被挂起的状态

		$vagrant resume
		[default] Resuming suspended VM...
		[default] Booting VM...
		[default] Waiting for VM to boot. This can take a few minutes.
		[default] VM booted and ready for use!

* `vagrant ssh-config`

	输出用于ssh连接的一些信息

		  $vagrant ssh-config
		  Host default
		  HostName 127.0.0.1
		  User vagrant
		  Port 2222
		  UserKnownHostsFile /dev/null
		  StrictHostKeyChecking no
		  PasswordAuthentication no
		  IdentityFile "/Users/astaxie/.vagrant.d/insecure_private_key"
		  IdentitiesOnly yes
		  LogLevel FATAL

* `vagrant status`

	获取当前虚拟机的状态

		$vagrant status
		Current machine states:
		default running  (virtualbox)
		The VM is running. To stop this VM, you can run `vagrant halt` to
		shut it down forcefully, or you can run `vagrant suspend` to simply
		suspend the virtual machine. In either case, to restart it again,
		simply run `vagrant up`.

* `vagrant suspend`

	挂起当前的虚拟机

		$ vagrant suspend
		[default] Saving VM state and suspending execution...
