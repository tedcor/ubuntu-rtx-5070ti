# UBUNTU RTX 5070ti GPU Driver Install

The instructions below will install the GPU drivers for Nvidia RTX 55** graphic cards from a fresh install of Ubuntu 24.04.

# Adding graphics repository and installing driver

sudo add-apt-repository ppa:graphics-drivers/ppa

sudo apt update 

sudo apt install nvidia-driver-560

reboot

# Installing Cuda 12.8

Link to official Nvidia CUDA 12.8 install page

https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=24.04&target_type=deb_network

Enter the commands below into your terminal

wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2404/x86_64/cuda-keyring_1.1-1_all.deb

sudo dpkg -i cuda-keyring_1.1-1_all.deb

sudo apt update

sudo apt-get -y install cuda-toolkit-12-8
