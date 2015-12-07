# 整体结构

源代码主要分为 8 个目录和若干文件：
contrib、devstack、doc、etc、kuryr、scripts、tools 和 usr。
除了些目录外，还包括一些说明文档、安装需求说明文件等。

## contrib
主要包括一个 vagrant 目录，给出了基于 vagrant 快速搭建一个测试环境例子。

## devstack
目前 Kuryr 还没有完成集成，因此使用的时候可能需要一些订制工作。本目录下包括了一些 devstack 相关的配置和脚本，方便使用 devstack 来搭建启用了 Kuryr 的环境。

## doc
包括使用 Sphinx 生成文档的相关源码。

## etc
跟服务和配置相关的文件。

比较有用的，可以通过下面的命令来生成样例配置文件。
```sh
tox -egenconfig
```

## kuryr
项目核心的代码实现都在这个目录下。
可以通过下面的命令来统计主要实现的核心代码量。
```
find kuryr  -name "*.py" | xargs cat | wc -l
```
目前版本，约为 3k 行。

## scripts
本地启动 Kuryr 服务的脚本。

`run_kuryr.sh` 脚本会创建 `/usr/lib/docker/plugins/kuryr` 和 `/usr/lib/docker/plugins/kuryr/kuryr.json`。

## tools
一些相关的代码格式化检测、环境安装的脚本。

## usr
一些外部的库支持，目前包括调用 midonet 的命令等。

## 其它文档
* README.rst：介绍了项目的情况和一些有用连接。
* TESTING.rst：介绍如何进行开发后的测试。官方配置的 jenkins 当 gerrit 上有代码提交 review 的时候会触发 tox 测试。实际上，OpenStack 中的项目基本都使用 [tox](http://tox.readthedocs.org/en/latest/) 来管理测试的虚拟环境，使用 [testr](https://wiki.openstack.org/wiki/Testr) 来管理运行测试案例的顺序。
