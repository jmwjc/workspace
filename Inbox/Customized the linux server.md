---
icon: TiHelp
---
#Tutorial/Service  

# ssh

# [nfs(Debian)](https://wiki.debian.org/NFSServerSetup)
1. 安装**nfs**
```
sudo apt install nfs-kernel-server
```
2. 配置**exports**
```
echo "/example 192.168.1.0/255.255.255.0(rw,no_root_squash,subtree_check)" >> /etc/exports
/usr/sbin/exportfs -a
/etc/init.d/nfs-kernel-server reload
```
3. 客户端挂载
```
sudo mount -o nolocks -t nfs 192.168.1.101:/example ~/nfs
```
目前最新配置信息如下
```
sudo mount -o nolocks -t nfs 192.168.1.100:/home/wujc ~/workstation
```