OpenStack Kuryr 源码分析
============
[Kuryr](https://wiki.openstack.org/wiki/Kuryr) 是 OpenStack 项目中负责提供容器网络服务的项目，它作为 libnetwork 的一个 remote 类型的驱动，可以连接 [libnetwork](https://github.com/docker/libnetwork) 支持的 CNM（Container Network Model） 和 Neutron 所提供的网络服务。

本书将剖析 Kuryr 组件的代码。

最新版本在线阅读：[GitBook](https://www.gitbook.io/book/yeasy/openstack_code_Kuryr)。

本书源码在 Github 上维护，欢迎参与： [https://github.com/yeasy/openstack_code_Kuryr](https://github.com/yeasy/openstack_code_Kuryr)。

感谢所有的 [贡献者](https://github.com/yeasy/openstack_code_Kuryr/graphs/contributors)。

## 更新历史:
* V0.2: 2015-12-07
 	* 根据最新代码更新结构。
	* 添加更多核心代码分析。
* V0.1: 2015-11-02
	* 初始化基本结构。


## 参加步骤
* 在 GitHub 上 `fork` 到自己的仓库，如 `user/openstack_code_Kuryr`，然后 `clone` 到本地，并设置用户信息。
```
$ git clone git@github.com:user/openstack_code_Kuryr.git
$ cd openstack_code_Kuryr
$ git config user.name "User"
$ git config user.email user@email.com
```

* 修改代码后提交，并推送到自己的仓库。
```
$ #do some change on the content
$ git commit -am "Fix issue #1: change helo to hello"
$ git push
```

* 在 GitHub 网站上提交 pull request。
* 定期使用项目仓库内容更新自己仓库内容。
```
$ git remote add upstream https://github.com/yeasy/openstack_code_Kuryr
$ git fetch upstream
$ git checkout master
$ git rebase upstream/master
$ git push -f origin master
```
