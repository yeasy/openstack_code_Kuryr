#### libnetwork_remote_driver_design.rst
作为 libnetwork remote 驱动的核心设计。

主要功能：

* 映射 API 为到 Neutron 的调用；
* 绑定本地的 veth 虚接口到对应网桥。

主要过程：

* 探测并注册插件为 NetworkDriver 和 IpadmDriver，并获取 capacity 和 default 地址空间；
* 用户执行 docker 命令的时候带上 --driver=kuryr 和 --ipam-driver=kuryr；
* 命令通过 libnetwork 转化为对 Kuryr 的 API 调用；
* Kuryr 收到 API，转化并通过 neutron client 发给 Neutron；
* Kuryr 根据收到的 Neutron 响应，返回 libnetwork 的响应；
* libnetwork 根据收到响应更新本地键值数据库；
