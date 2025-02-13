
# Installing the NVIDIA Container Toolkit
```warp-runnable-command
install nvidia-container-toolkit

```
## Configuration
```warp-runnable-command
sudo nvidia-ctk runtime configure --runtime=docker
sudo systemctl restart docker

# Rootless mode
nvidia-ctk runtime configure --runtime=docker --config=$HOME/.config/docker/daemon.json
systemctl --user restart docker
sudo nvidia-ctk config --set nvidia-container-cli.no-cgroups --in-place

# Configuring containerd (for Kubernetes)
sudo nvidia-ctk runtime configure --runtime=containerd
sudo systemctl restart containerd
```
# Install Open WebUI
```warp-runnable-command
docker run -d -p 3000:8080 --gpus all --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:cuda
```
