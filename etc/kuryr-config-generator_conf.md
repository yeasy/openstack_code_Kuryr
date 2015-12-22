## kuryr-config-generator.conf
tox 将基于本模板内容执行 `oslo-config-generator` 命令来生成 Kuryr 的示例配置文件，官方推荐使用这种方式的 bp 在 [https://blueprints.launchpad.net/neutron/+spec/autogen-neutron-conf-file](https://blueprints.launchpad.net/neutron/+spec/autogen-neutron-conf-file)。

内容很简单

```py
[DEFAULT]
output_file = etc/kuryr.conf.sample
wrap_width = 79
namespace = kuryr
```

*ps，始终觉得有点多此一举，原先直接给出示例配置文件的方式没啥不好的……*
