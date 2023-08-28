## Kernel src download
```
sudo apt-get source linux-source
sudo apt-cache search linux-source
sudo apt install <download-src-name>
or
git clone git://kernel.ubuntu.com/ubuntu/ubuntu-trusty.git
```
Downloaded kernel image will be located in "**/usr/src**"

## 
```
cp /boot/config-$(uname -r) .config
make oldconfig
```
