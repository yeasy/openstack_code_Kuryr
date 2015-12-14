#### midonet
基于 midonet 实现的本地虚拟接口管理，包括
* bind_port()
* unbind_port()

```py
bind_port() {
    echo "Binding Neutron port $1 to the veth $2..."
    mm-ctl --bind-port $1 $2
}

unbind_port() {
    echo "Unbinding Neutron port $1..."
    mm-ctl --unbind-port $1
}

case $1 in
    "bind")
        shift
        bind_port "$@"
        exit 0
        ;;
    "unbind")
        shift
        unbind_port "$@"
        exit 0
        ;;
    *)
        echo >&2 "$0: Invalid command $1."
        exit 1
        ;;
esac
```
