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

# install required apt packages
```
sudo apt install vim git meld terminator build-essential tree htop net-tools
```

# My aliases
```
vi ~/.bashrc
```
```
# My aliases
alias ..='cd ..'
alias ...='cd ../..'
alias ....='cd ../../..'
alias ....='cd ../../../..'
alias .....='cd ../../../../..'
alias ......='cd ../../../../../..'
alias .......='cd ../../../../../../..'
alias ........='cd ../../../../../../../..'
```

# Grub
/etc/default/grub
```
GRUB_DEFAULT=saved
GRUB_SAVEDEFAULT="true"
GRUB_TIMEOUT=3
#GRUB_TIMEOUT_STYLE=hidden
```
sudo update-grub


# Chrome
```
sudo apt install curl
curl https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
sudo sh -c 'echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list'
sudo apt-get update
sudo apt-get --no-install-recommends install -y google-chrome-stable
```
* Trouble shooting when chrome does not work on WSL
```
export LIBGL_ALWAYS_INDIRECT=1
export DISPLAY=:0
```

# OTX
```
sudo apt-get install python3-dev
sudo apt install libgl1-mesa-glx

pip install -U pip
pip install wheel
pip install datumaro[default]
pip install torch==1.13.1 torchvision==0.14.1 --extra-index-url https://download.pytorch.org/whl/cu117
pip uninstall mmcv-full
pip install mmcv-full -f https://download.openmmlab.com/mmcv/dist/cu117/torch1.13.0/index.html
pip install otx[full]

pip uninstall mmcv
pip install mmcv-full
# For CPU only
pip install mmcv-full -f https://download.openmmlab.com/mmcv/dist/cpu/torch2.0.0/index.html
or
sudo apt install gcc-10 g++-10
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-10 10
sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-10 10
```


# Python VENV
```
python3 -m venv venv
source venv/bin/activate
python -m pip install --upgrade pip
```

# NVIDIA GPU installation on Ubuntu
Disable Nouveau: The open-source Nouveau driver for NVIDIA GPUs should be disabled before installing the proprietary NVIDIA driver. Create a file at /etc/modprobe.d/blacklist-nouveau.conf with the following content:
```
blacklist nouveau
options nouveau modeset=0
```
Update the kernel initramfs:
```
sudo update-initramfs -u
```
Reboot your system to apply these changes.

```
sudo apt remove --purge nvidia-*
sudo apt remove --purge cuda-*
sudo apt autoremove nvidia* --purge
sudo rm -rf /usr/local/cuda*
sudo /usr/bin/nvidia-uninstall

sudo apt install pkg-config libglvnd-dev build-essencial

sudo apt update
apt-cache search 'nvidia-driver-' | grep '^nvidia-driver-[[:digit:]]*'
sudo apt install nvidia-driver-515-open

```

```
sudo apt remove --purge nvidia-*
sudo apt remove --purge cuda-*
rm -rf /usr/local/cuda*
/usr/bin/nvidia-uninstall
sudo /usr/bin/nvidia-uninstall
   
sudo ubuntu-drivers devices
sudo apt install nvidia-driver-530-open
sudo apt install nvidia-cuda-toolkit

https://docs.nvidia.com/deeplearning/cudnn/install-guide/index.html
```
```
sudo apt install pkg-config libglvnd-dev build-essencial

https://developer.nvidia.com/cuda-11-8-0-download-archive
https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html#pre-installation-actions
https://docs.nvidia.com/cuda/archive/11.8.0/cuda-installation-guide-linux/index.html

sudo apt autoremove nvidia* --purge
sudo /usr/bin/nvidia-uninstall
sudo /usr/local/cuda-X.Y/bin/cuda-uninstall
sudo apt install dirmngr ca-certificates software-properties-common apt-transport-https dkms curl -y
curl -fSsL https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/3bf863cc.pub | sudo gpg --dearmor | sudo tee /usr/share/keyrings/nvidia-drivers.gpg > /dev/null 2>&1
echo 'deb [signed-by=/usr/share/keyrings/nvidia-drivers.gpg] https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/ /' | sudo tee /etc/apt/sources.list.d/nvidia-drivers.list
sudo apt update
apt search nvidia-driver-*
sudo apt install nvidia-driver-xxx
https://developer.nvidia.com/cuda-11-7-1-download-archive?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=22.04&target_type=deb_local
https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=22.04&target_type=deb_local
```

Verify NVIDIA version
```
cat /proc/driver/nvidia/version
```
