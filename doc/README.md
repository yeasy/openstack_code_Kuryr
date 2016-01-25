# doc
包括使用 Sphinx 生成文档的相关源码。

主要在 source 目录下。

在 doc 目录下执行
```sh
$ make html
```

会自动生成 html 格式的文档，放在新创建的 build 目录下面。

还可以用简单的 web 服务来查看文档，例如配置到本地的 8080 端口。

```sh
$ python -m SimpleHTTPServer 8080
```
