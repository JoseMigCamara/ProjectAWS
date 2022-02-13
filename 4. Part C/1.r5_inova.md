## RAID5 - LVM - LUKS
## RAID5
```
apt install raidutils
```
```
lsblk
```
* Replace the "X" with the correspondent letter of the disk
```
gdisk /dev/xvdX
```
* `o` and then `Y`
* `n` and `ENTER`,`ENTER`,`ENTER`,`fd00`
* `w` and then `Y`
```
mkdir /mnt/raid5_homes /mnt/raid5_info
```
```
mdadm --create /dev/md0 --level 5 --raid-devices 3 /dev/xvdf1 /dev/xvdg1 /dev/xvdh1
```
```
mdadm --detail /dev/md0
```
* Wait until appears :`State : clean`
```
pvcreate /dev/md0
```
```
vgcreate vg0 /dev/md0 
```
```
lvcreate -n lv0 -l 80%FREE vg0
```
```
lvcreate -n lv1 -l 100%FREE vg0
```
```
cryptsetup luksFormat --hash=sha512 --key-size=512 --cipher=aes-xts-plain64 --verify-passphrase /dev/vg0/lv0
```
* Password: `Passw0rd1`
```
cryptsetup luksFormat --hash=sha512 --key-size=512 --cipher=aes-xts-plain64 --verify-passphrase /dev/vg0/lv1
```
* Password: `Passw0rd2`
```
cryptsetup luksOpen /dev/vg0/lv0 lv0_crypt
```
* Password: `Passw0rd1`
```
cryptsetup luksOpen /dev/vg0/lv1 lv1_crypt
```
* Password: `Passw0rd2`
```
mkfs.xfs /dev/mapper/lv0_crypt
```
```
mkfs.xfs /dev/mapper/lv1_crypt
```
```
mount /dev/mapper/lv0_crypt /mnt/raid5_homes/
```
```
mount /dev/mapper/lv1_crypt /mnt/raid5_info/
```
```
cat /etc/mtab
```
```
nano /etc/fstab
```
```
df -hT
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

