### Source \: github\.com\/sickcodes\/Docker\-OSX
## Initial setup
```warp-runnable-command
install qemu libvirt dnsmasq virt-manager bridge-utils flex bison iptables-nft edk2-ovmf
```
Then\, enable libvirt and load the KVM kernel module\:
```warp-runnable-command
sudo systemctl enable --now libvirtd
sudo systemctl enable --now virtlogd

echo 1 | sudo tee /sys/module/kvm/parameters/ignore_msrs

sudo modprobe kvm
```
Fix Display Authorization
```warp-runnable-command
xhost +local:
export DISPLAY=:0
```
### Run Big Sur
```warp-runnable-command
docker run -it \
    --device /dev/kvm \
    -p 50922:10022 \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    -e "DISPLAY=${DISPLAY:-:0.0}" \
    sickcodes/docker-osx:big-sur

```
### Run Catalina
```warp-runnable-command
docker run -it \
    --device /dev/kvm \
    -p 50922:10022 \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    -e "DISPLAY=${DISPLAY:-:0.0}" \
    -e SHORTNAME=catalina \
    sickcodes/docker-osx:latest

# docker build -t docker-osx .
```
\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
Run 
```warp-runnable-command
xhost +local: \
export DISPLAY=:0 \
docker run -it \
    --device /dev/kvm \
    -p 50922:10022 \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    -e "DISPLAY=${DISPLAY:-:0.0}" \
    sickcodes/docker-osx:big-sur
```
