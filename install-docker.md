# Instalar Docker

Docker es una plataforma de contenedores que permite empaquetar aplicaciones con todas sus dependencias. Facilita el desarrollo, testing y despliegue de aplicaciones de forma consistente.

**Sitio oficial:** https://www.docker.com

## Linux (Ubuntu/Debian)

```bash
# 1. Instalar dependencias
sudo apt-get update
sudo apt-get install -y ca-certificates curl gnupg

# 2. Agregar clave GPG de Docker
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

# 3. Agregar repositorio
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# 4. Instalar Docker
sudo apt-get update
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# 5. Agregar usuario al grupo docker (para no usar sudo)
sudo usermod -aG docker $USER
newgrp docker

# 6. Verificar
docker --version
docker compose version
```

## Mac

```bash
# Instalar Docker Desktop (incluye Docker Engine y Docker Compose)
brew install --cask docker

# Abrir Docker Desktop desde Applications
# Verificar (después de abrir Docker Desktop)
docker --version
docker compose version
```

## WSL2 (Windows)

Para usar Docker en WSL2, instalar **Docker Desktop para Windows** y habilitar la integración con WSL2:

1. Descargar Docker Desktop desde https://www.docker.com/products/docker-desktop
2. En Settings → Resources → WSL Integration, habilitar tu distro de Ubuntu
3. Reiniciar la terminal de WSL

## Cheatsheet

```bash
docker ps                     # Listar contenedores activos
docker ps -a                  # Listar todos los contenedores
docker images                 # Listar imágenes
docker run -it ubuntu bash    # Ejecutar contenedor interactivo
docker stop CONTAINER         # Detener contenedor
docker compose up -d          # Levantar servicios en background
```
