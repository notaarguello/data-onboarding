# Instalar Google Cloud CLI (gcloud)

Google Cloud CLI es la herramienta de línea de comandos para interactuar con Google Cloud Platform. Permite gestionar recursos, desplegar aplicaciones y administrar proyectos.

**Sitio oficial:** https://cloud.google.com/sdk

## Linux

```bash
# 1. Descargar e instalar
curl -O https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-cli-linux-x86_64.tar.gz
tar -xf google-cloud-cli-linux-x86_64.tar.gz
./google-cloud-sdk/install.sh

# 2. Reiniciar la terminal o ejecutar:
source ~/.bashrc

# 3. Inicializar gcloud
gcloud init
```

## Mac

```bash
# Opción 1: Con Homebrew
brew install --cask google-cloud-sdk

# Opción 2: Manual
curl -O https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-cli-darwin-arm.tar.gz
tar -xf google-cloud-cli-darwin-arm.tar.gz
./google-cloud-sdk/install.sh

# Inicializar gcloud
gcloud init
```

## Trabajar con múltiples cuentas/proyectos

gcloud usa "configuraciones" para manejar múltiples cuentas. Cada configuración guarda cuenta, proyecto y región.

```bash
# Crear configuración para cuenta personal
gcloud config configurations create personal
gcloud auth login
gcloud config set project mi-proyecto-personal

# Crear configuración para trabajo
gcloud config configurations create trabajo
gcloud auth login
gcloud config set project proyecto-empresa

# Ver configuraciones disponibles
gcloud config configurations list

# Cambiar entre configuraciones
gcloud config configurations activate personal
gcloud config configurations activate trabajo
```

## Cheatsheet

```bash
gcloud auth login                         # Autenticarse con cuenta Google
gcloud config set project PROJECT_ID      # Cambiar proyecto activo
gcloud config configurations list         # Ver todas las configuraciones
gcloud config configurations activate NAME # Cambiar entre cuentas
gcloud projects list                      # Listar proyectos disponibles
gcloud auth list                          # Ver cuentas autenticadas
```
