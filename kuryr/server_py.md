## server.py
启动一个 kuryr 服务，监听本地的 2377 端口。

```python
from kuryr import app


def start():
    app.debug = True
    app.run("0.0.0.0", port=2377)
```