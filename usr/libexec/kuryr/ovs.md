#### ovs
基于 ovs 实现的本地虚拟接口管理，包括
* bind_port()
* unbind_port()


```py
INT_BRIDGE="br-int"

bind_port() {
    echo "plugging veth $2 (Neutron port $1)..."
    mac=`ip link show dev $2 | tail -1 | awk '{print $2}'`
    sudo ovs-vsctl add-port $INT_BRIDGE $2
    sudo ovs-vsctl set interface $2 external_ids:attached-mac=$mac \
        external_ids:iface-id=$1 external_ids:vm-id=$3 \
        external_ids:iface-status=active
}

unbind_port() {
    echo "unplugging veth $1..."
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
