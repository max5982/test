# test
Just for my practice

# Init Ubuntu
``` bash
sudo vi /etc/sudoers
```
``` shell
#includedir /etc/sudoers.d
max     ALL=(ALL) NOPASSWD: ALL
```

# Grub
/etc/default/grub
```
GRUB_DEFAULT=saved
GRUB_SAVEDEFAULT="true"
```
sudo update-grub
