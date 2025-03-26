# UBUNTU RTX 5070ti GPU Driver Install

The instructions below will install the GPU drivers for Nvidia RTX 55** graphic cards from a fresh install of Ubuntu 24.04.

### Adding graphics repository and installing driver
### I chose the 570-open driver as it seems to work better than the 570.
```
sudo add-apt-repository ppa:graphics-drivers/ppa

sudo apt update 

sudo apt install nvidia-driver-570-open

reboot
```
### Installing Cuda 12.8

Link to official Nvidia CUDA 12.8 install page

https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=24.04&target_type=deb_network

Enter the commands below into your terminal
```
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2404/x86_64/cuda-keyring_1.1-1_all.deb

sudo dpkg -i cuda-keyring_1.1-1_all.deb

sudo apt update

sudo apt-get -y install cuda-toolkit-12-8
```
### How to check if the drivers and CUDA installed correctly

open your terminal and enter the folling command:
```
nvidia-smi
```
If all went well you should see the status of your GPU and processes in the terminal.

### Installing Torch for use with 50** Blackwell GPU

Install pipx
```
sudo apt install pipx

pip install --pre torch torchvision torchaudio --index-url https://download.pytorch.org/whl/nightly/cu128

```
### issues with running comfyui

uninstall pytorch
```
pip uninstall torch torchvision torchaudio -y
```

https://www.reddit.com/r/StableDiffusion/comments/1j3ix0m/runtimeerror_cuda_error_no_kernel_image_is/

https://download.pytorch.org/whl/nightly/cu128/torch/

download this:
```
torch-2.7.0.dev20250304+cu128-cp313-cp313-win_amd64.whl
```

https://www.reddit.com/r/StableDiffusion/comments/1j3ix0m/runtimeerror_cuda_error_no_kernel_image_is/
