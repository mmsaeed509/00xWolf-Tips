To install the CUDA Toolkit on Arch Linux\, follow these steps\:
***
### 1\. **Update Your System**
```warp-runnable-command
sudo pacman -Syu
```
***
### 2\. **Check Your GPU**
Ensure your NVIDIA GPU is supported by the current CUDA version\:
```warp-runnable-command
nvidia-smi
```
If `nvidia-smi` isn\'t available\, install the `nvidia-utils` package\:
```warp-runnable-command
sudo pacman -S nvidia-utils
```
***
### 3\. **Install CUDA Toolkit**
CUDA is available in the official Arch Linux repositories\:
```warp-runnable-command
sudo pacman -S cuda
```
***
### 4\. **Set Up Environment Variables**
Add the CUDA path to your shell configuration file \(e\.g\.\, `~/.bashrc`\, `~/.zshrc`\)\:
```warp-runnable-command
echo 'export PATH=/opt/cuda/bin:$PATH' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH=/opt/cuda/lib64:$LD_LIBRARY_PATH' >> ~/.bashrc
source ~/.bashrc
```
***
### 5\. **Verify CUDA Installation**
Check the installed CUDA version\:
```warp-runnable-command
nvcc --version
```
***
### 6\. **Compile and Test**
Use the CUDA samples to verify everything works\:
```warp-runnable-command
cp -r /opt/cuda/samples ~/
cd ~/samples/1_Utilities/deviceQuery
make
./deviceQuery
```
If the output shows your GPU and its capabilities\, the installation is successful\.
***
### Notes
* Ensure your NVIDIA driver is up\-to\-date\. You can install it with\:
```warp-runnable-command
sudo pacman -S nvidia
```
* If using DKMS\, install `nvidia-dkms` instead\:
```warp-runnable-command
sudo pacman -S nvidia-dkms
```
* Reboot after installation for changes to take effect\:
```warp-runnable-command
sudo reboot
```
Let me know if you encounter any issues\!