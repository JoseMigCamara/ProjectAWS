## Setting up the Machines
### INOVA
```
sudo hostnamectl set-hostname control.inova.pt
```
```
sudo su -
```
```
apt install -y easy-rsa openvpn bind9 iptables-persistant netfilter-persistant
```
```
cp -r /usr/share/easy-rsa/ /etc/
```
```
ip a
```
```
nano /etc/netplan/50-cloud-init.yaml
```

### ENTA
```
sudo hostnamectl set-hostname control.enta.pt
```
```
sudo su -
```
```
amazon-linux-extras install epel
```
```
yum install -y easy-rsa openvpn bind iptables-services
```
```
mkdir /etc/easy-rsa/
```
```
cp -r /usr/share/easy-rsa/3/* /etc/easy-rsa/
```
```
ip a
```

### Remote Client
```
sudo hostnamectl set-hostname remote.client.pt
```
```
sudo su -
```
```
amazon-linux-extras install epel
```
```
apt install -y easy-rsa openvpn
```
```
mkdir /etc/easy-rsa/
```
```
cp -r /usr/share/easy-rsa/3/* /etc/easy-rsa/
```
