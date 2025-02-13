### install Docker
```warp-runnable-command
install docker docker-compose
```
### Configure Docker to start on boot with systemD
```warp-runnable-command
sudo systemctl start docker.service
sudo systemctl start containerd.service
sudo systemctl enable docker.service
sudo systemctl enable containerd.service
```
### Create Docker group and add user to groub
```warp-runnable-command
sudo groupadd docker
sudo usermod -aG docker $USER
```
Log out and log back in so that your group membership is re\-evaluated
### Verify that you can run `docker` commands without `sudo`
```warp-runnable-command
docker run hello-world
```
### Install Podman
```warp-runnable-command
install podman podman-compose podman-desktop
```
