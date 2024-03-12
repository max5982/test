## Kernel src download
```
sudo add-apt-repository ppa:canonical-kernel-team/proposed -y
sudo apt update
sudo apt-get source linux-source
sudo apt-cache search linux-source
sudo apt install <download-src-name>
or
apt-get source linux-image-unsigned-$(uname -r)
or
git clone git://kernel.ubuntu.com/ubuntu/ubuntu-trusty.git
```
Downloaded kernel image will be located in "**/usr/src**"

## 
```
cp /boot/config-$(uname -r) .config
make oldconfig
```

```
sudo apt-get install libncurses-dev gawk flex bison openssl libssl-dev dkms libelf-dev libudev-dev libpci-dev libiberty-dev autoconf llvm
```
