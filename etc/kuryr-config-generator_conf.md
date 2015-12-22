## kuryr-config-generator.conf
tox 将基于本模板内容生成 Kuryr 的示例配置文件。

内容很简单

```py
[DEFAULT]
output_file = etc/kuryr.conf.sample
wrap_width = 79
namespace = kuryr
```

*ps，始终觉得有点多此一举，原先直接给出示例配置文件的方式没啥不好的……*
