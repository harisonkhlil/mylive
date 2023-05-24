# 关闭 Linux 防火墙

#Linux #防火墙

## UFW

```shell
sudo ufw disable # Ubuntu 和 Debian
```

## Firewalld

```shell
sudo systemctl stop firewalld
```

## iptables

```shell
sudo iptables -F
sudo iptables -X
sudo iptables -t nat -F
sudo iptables -t nat -X
sudo iptables -t mangle -F
sudo iptables -t mangle -X
sudo iptables -P INPUT ACCEPT
sudo iptables -P FORWARD ACCEPT
sudo iptables -P OUTPUT ACCEPT
```





