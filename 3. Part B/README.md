## Setting up the machines

### INOVA

```
sudo hostnamectl set-hostname dmz.inova.pt
```
```
sudo su -
```
```
nano /etc/netplan/50-cloud-init.yaml
```
```
dhcp4-overrides:
    use-dns:false
    use-routes:false
```
```
nameservers:
    addresses: [ 172.31.0.100 ]
```
```
routes:
    - to: 0.0.0.0/0
      via: 172.31.110.100
      on-link: true
```
```
netplan try
```
```
apt-get update && apt -y upgrade
```
```

```
### ENTA
```
sudo hostnamectl set-hostname dmz.enta.pt
```
```
sudo su -
```
```
nano /etc/sysconfig/network-scripts/ifcfg-eth0
```
```
GATEWAY=172.31.110.100
DNS1=172.31.0.100
```
```
systemctl restart network
```
```
yum -y update
```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

```

