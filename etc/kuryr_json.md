## kuryr.json
配置服务信息，Docker libnetwork 需要这个配置。

```json
{
    "Name": "kuryr",
    "Addr": "http://127.0.0.1:2377"
}
```

安装后会被放到 `/usr/lib/docker/plugins/kuryr` 目录下。
