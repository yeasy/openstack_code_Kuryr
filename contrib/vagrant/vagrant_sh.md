### vagrant.sh
基础 vm 启动后执行的安装脚本。

```sh
#!/bin/sh

export OS_USER=vagrant
export OS_HOST_IP=172.68.5.10

# run script
bash /vagrant/devstack.sh "$1"

#set environment variables for kuryr
su "$OS_USER" -c "echo 'source /vagrant/config/kuryr_rc' >> ~/.bashrc"
```
