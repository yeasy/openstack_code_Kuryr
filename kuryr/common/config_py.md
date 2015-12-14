### config.py
基于 oslo.config 的配置信息读取。

跟 Kuryr 自身相关的配置项有四个。
```py
core_opts = [
    cfg.StrOpt('pybasedir',
               default=os.path.abspath(os.path.join(os.path.dirname(__file__),
                                                    '../../')),
               help=_('Directory where kuryr python module is installed.')),
    cfg.StrOpt('bindir',
               default='$pybasedir/usr/libexec/kuryr',
               help=_('Directory for kuryr vif binding executables.')),
    cfg.StrOpt('kuryr_uri',
               default='http://127.0.0.1:2377',
               help=_('Kuryr URL for accessing Kuryr through json rpc.')),
    cfg.StrOpt('capability_scope',
               default='global',
               choices=['local', 'global'],
               help=_('Kuryr plugin scope reported to libnetwork.')),
]
```

跟 Neutron 相关的配置项目前有两个：
```py
neutron_opts = [
    cfg.StrOpt('neutron_uri',
               default=os.environ.get('OS_URL', 'http://127.0.0.1:9696'),
               help=_('Neutron URL for accessing the network service.')),
    cfg.StrOpt('enable_dhcp',
               default='False',
               help=_('Enable or Disable dhcp for neutron subnets.')),
]
```

Keystone 相关的：
```py
keystone_opts = [
    cfg.StrOpt('auth_uri',
               default=os.environ.get('IDENTITY_URL',
                                      'http://127.0.0.1:35357'),
               help=_('The URL for accessing the identity service.')),
    cfg.StrOpt('admin_user',
               default=os.environ.get('SERVICE_USER'),
               help=_('The admin username.')),
    cfg.StrOpt('admin_tenant_name',
               default=os.environ.get('SERVICE_TENANT_NAME'),
               help=_('The admin username.')),
    cfg.StrOpt('admin_password',
               default=os.environ.get('SERVICE_PASSWORD'),
               help=_('The admin password.')),
    cfg.StrOpt('admin_token',
               default=os.environ.get('SERVICE_TOKEN'),
               help=_('The admin token.')),
]
```

其它的，还有跟 binding 相关的：
```py
binding_opts = [
    cfg.StrOpt('veth_dst_prefix',
               default='eth',
               help=('The name prefix of the veth endpoint put inside the '
                     'container.'))
]
```
