### constants.py
一些常量，包括 libnetwork 中定义的返回结构等。
```py
SCHEMA = {
    "PLUGIN_ACTIVATE": {"Implements": ["NetworkDriver"]},
    # TODO(tfukushima): This is mocked and should be replaced with real data.
    "ENDPOINT_OPER_INFO": {"Value": {}},
    "SUCCESS": {}
}

DEVICE_OWNER = 'kuryr:container'
```
