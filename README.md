# Manual del workshop 
```
docker run -d -p 80:80 docker/getting-started
```
# Install Docker in AWS Ami Linux 2023
```
sudo dnf install git -y
sudo dnf install docker -y
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker $USER
newgrp docker
```
```
sudo curl -s https://api.github.com/repos/docker/compose/releases/latest | grep browser_download_url | grep docker-compose-linux-x86_64 | cut -d '"' -f 4 | wget -qi -
sudo chmod +x docker-compose-linux-x86_64
sudo mv docker-compose-linux-x86_64 /usr/local/bin/docker-compose
docker-compose --version
```
```
mkdir -p ~/.docker/cli-plugins
curl -L https://github.com/docker/buildx/releases/download/v0.17.0/buildx-v0.17.0.linux-amd64 \
  -o ~/.docker/cli-plugins/docker-buildx
chmod +x ~/.docker/cli-plugins/docker-buildx
docker buildx version
```
# Install Docker AWS Ubuntu 
```
sudo apt update && sudo apt upgrade -y

sudo apt install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: https://download.docker.com/linux/ubuntu
Suites: $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}")
Components: stable
Architectures: $(dpkg --print-architecture)
Signed-By: /etc/apt/keyrings/docker.asc
EOF

sudo apt update

sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
sudo usermod -aG docker $USER
newgrp docker
```
# Docker scout
```
# 1. Crea la ruta donde Docker busca complementos de usuario
mkdir -p ~/.docker/cli-plugins

# 2. Descarga e instala el binario directamente en esa ruta
curl -sSfL https://raw.githubusercontent.com/docker/scout-cli/main/install.sh | sh -s -- -b ~/.docker/cli-plugins
```

```
docker scout version
docker login
docker scout quickview <tu_imagen>:<tag>
docker scout cves <tu_imagen>:<tag>
docker scout recommendations <tu_imagen>:<tag>
```
# Cloudbeaver
```
docker run --network getting-started-app_default --name cloudbeaver --rm -ti -d -p 8080:8978 -v /opt/cloudbeaver/workspace dbeaver/cloudbeaver:latest
```

# Getting started

This repository is a sample application for users following the getting started guide at https://docs.docker.com/get-started/.

The application is based on the application from the getting started tutorial at https://github.com/docker/getting-started

