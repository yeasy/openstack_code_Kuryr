## run_kuryr.sh
目前运行 kuryr 的入口脚本，主要完成：

* 检查 libnetwork plugin 目录 /usr/lib/docker/plugins/kuryr 和配置文件，不存在则常见目录，并复制 /etc/kuryr.json 文件过去；
* 检查 kuryr 的配置目录 /etc/kuryr/ 和配置文件  /etc/kuryr/kuryr.conf，不存在则创建并通过 tox -egenconfig 命令，基于 tox.ini 来生成一个默认配置文件；
* 执行 scripts/run_server.py --config-file /etc/kuryr/kuryr.conf 命令来启动 Kuryr 服务。

相关的，tox.ini 中有对应生成配置文件的段：
```py
[testenv:genconfig]
commands = oslo-config-generator --config-file=etc/kuryr-config-generator.conf
```
