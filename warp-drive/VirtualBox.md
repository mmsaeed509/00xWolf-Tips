### install VBox
```warp-runnable-command
install virtualbox virtualbox-ext-oracle virtualbox-ext-vnc virtualbox-guest-iso virtualbox-guest-utils virtualbox-host-dkms virtualbox-sdk
```
### Kernel driver not installed 
```warp-runnable-command
sudo vboxreload
```
### can\'t enumerate USB devices
```warp-runnable-command
sudo usermod -aG vboxusers o0xwolf

```
