## NFS
### Server
```
apt install -y nfs-kernel-server
```
```
nano /etc/exports
```
```
/mnt/raid5_homes *(rw,sync,no_subtree_check,no_root_squash)
```
```
exportfs -a
```
```
systemctl enable --now nfs-kernel-server
```
```
adduser rose --home /mnt/raid5_homes/rose
```
### Client Sales and Marketing
To see the configuration of the client go [HERE](https://github.com/rodrigobosilva/ProjectAWS/tree/main/7.%20Part%20F)
```
apt install -y nfs-common
```
```
mkdir /mnt/raid5_homes
```
```
mount -t nfs 172.31.210.101:/mnt/raid5_homes
```
```
cat /etc/mtab
```
```
nano /etc/fstab
```
## NIS
### Server
```
apt install -y nis
```
⚠️This might take some time
```
nano /etc/default/nis
```
* line 6, change to `NISSERVER=master`
* line 9, change to `NISCLIENT=false`
```
nano /etc/ypserv.securenets
```
* line 16, comment
* add to the bottom `255.255.255.0 172.31.210.0`
```
nano /var/yp/Makefile
```
* line 52, change to `MERGE_PASSWD=true`
* line 56, change to `MERGE_GROUP=true`
```
/usr/lib/yp/ypinit -m
```
* check if `central.inova.pt` is one the list
* Ctrl + D
```
systemctl restart nis
```
⚠️This might take some time
```
cd /var/yp
```
```
make
```
### Client Sales and Marketing
```
apt install -y nis
```
```
nano /etc/yp.conf
```
* add to the bottom `domain inova.pt server central.inova.pt`
```
nano /etc/nsswitch.conf
```
* line 7, add `nis` to the end
* line 8, add `nis` to the end
* line 9, add `nis` to the end
* line 12, add `nis` to the end
```
nano /etc/pam.d/common-session
```
* add to the bottom:
```
session optional pam_mkhomedir.so skel=/etc/skel umask=077
```
```
systemctl restart nis
```
