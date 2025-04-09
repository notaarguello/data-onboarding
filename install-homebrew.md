# Instalar Homebrew

Homebrew es el gestor de paquetes más popular para macOS. Permite instalar herramientas de línea de comandos y aplicaciones de forma sencilla.

**Sitio oficial:** https://brew.sh

## Mac

```bash
# 1. Instalar Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# 2. Agregar Homebrew al PATH (el instalador te indica el comando exacto)
# Para Apple Silicon (M1/M2/M3):
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"

# Para Intel:
echo 'eval "$(/usr/local/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/usr/local/bin/brew shellenv)"

# 3. Verificar instalación
brew --version
```

## Cheatsheet

```bash
brew install PAQUETE      # Instalar un paquete
brew uninstall PAQUETE    # Desinstalar un paquete
brew update               # Actualizar lista de paquetes
brew upgrade              # Actualizar paquetes instalados
brew list                 # Listar paquetes instalados
brew search TEXTO         # Buscar paquetes
```
