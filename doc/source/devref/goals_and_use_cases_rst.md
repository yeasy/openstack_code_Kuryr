#### goals_and_use_cases.rst
包括 Kuryr 项目的目标和典型用例。

目标主要是作为一个 libnetwork 的 remote 类型的驱动 API 翻译器，将 libnetwork 过来的请求 API 翻译为 Neutron API。即让 libnetwork 支持的容器直接跑在 Neutron 上面。

未来还希望能支持其它种类的网络模型，包括 Kubernetes 中的等。也即让这些不同平台统统可以跑在 Neutron 上。

典型用例包括支持裸机上跑容器，虚机里面跑容器，支持 Magnum，支持已有资源通过标签指定分配等。
