# Instalar Git

Git es el sistema de control de versiones más usado en el mundo. Permite trackear cambios en el código y colaborar con otros desarrolladores.

**Sitio oficial:** https://git-scm.com

## Linux

```bash
sudo apt update
sudo apt install -y git
git --version
```

## Mac

```bash
# Git viene preinstalado, pero se puede actualizar con Homebrew
brew install git
git --version
```

## Configuración inicial

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu-email@ejemplo.com"
git config --global init.defaultBranch main
# Recomendado si usás WSL para evitar issues de fin de línea
git config --global core.autocrlf input
```

> Para configurar SSH y autenticarte con GitHub, ver [install-ssh.md](install-ssh.md)

## Cheatsheet

```bash
git status              # Ver estado del repositorio
git add .               # Agregar todos los cambios
git commit -m "mensaje" # Crear commit
git push                # Subir cambios al remoto
git pull                # Traer cambios del remoto
git log --oneline       # Ver historial de commits
```