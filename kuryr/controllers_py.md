## controllers.py
作为 libnetwork 的一个 remote 类型驱动的代理，定义响应 rest 请求的一系列入口函数。按照 [https://github.com/docker/libnetwork/blob/master/docs/remote.md](https://github.com/docker/libnetwork/blob/master/docs/remote.md) 中定义的请求和响应消息来实现。

主要包括：network_driver_create_endpoint、network_driver_create_network、network_driver_delete_endpoint、network_driver_delete_network、network_driver_discover_delete、network_driver_discover_new、network_driver_endpoint_operational_info、network_driver_join、network_driver_leave、plugin_activate、plugin_scope等。


### network_driver_create_endpoint
响应 POST 到 /NetworkDriver.CreateEndpoint，根据给定的 endpoint 来创建一个新的 Neutron 子网和接口。


### network_driver_create_network

### network_driver_delete_endpoint

### network_driver_delete_network

### network_driver_discover_delete

### network_driver_discover_new

### network_driver_endpoint_operational_info

### network_driver_join

### network_driver_leave

### plugin_activate
响应 POST 到 /Plugin.Activate，回复实现的驱动的类型列表。

### plugin_scope
响应 POST 到 /NetworkDriver.GetCapabilities，回复驱动的范围：local 或者 global。