# swap file **creation**
* create a swap file with 16G
```warp-runnable-command
sudo mkswap -U clear --size 16G --file /swapfile
```
* Activate the swap file
```warp-runnable-command
sudo swapon /swapfile
```
* Finally\, edit the fstab configuration to add an entry for the swap file
```warp-runnable-command
sudo nvim /etc/fstab
```
* and add this line 
```warp-runnable-command
/swapfile none swap defaults 0 0

```
# **Swap file removal**
```warp-runnable-command
sudo swapoff /swapfile
sudo rm -f /swapfile
```
and remove this line from `/etc/fstab`
```warp-runnable-command
/swapfile none swap defaults 0 0
```
