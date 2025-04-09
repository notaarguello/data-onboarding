# Onboarding WSL + Ubuntu (Windows)

Este instructivo guía para habilitar WSL e instalar Ubuntu (distro/versión de linux).

* **WSL2** permite correr **Linux real** dentro de Windows, con buen rendimiento.
* Tenés tu **home de Linux** (`/home/tuusuario`) y acceso a discos de Windows en `/mnt/c`, `/mnt/d`, etc.
* Ideal para desarrollo con toolchains Linux (Python, Node, Docker, etc.).

## 1) Habilitar WSL desde PowerShell (Admin)

1. **Buscar y ejecutar *PowerShell* como Administrador**
2. Correr:

   ```powershell
   dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
   dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
   ```
3. **Reiniciar**

## 2) Instalar Ubuntu

1. **Buscar y abrir *WSL*** en el menú de Windows (o abrir PowerShell como Admin)
2. Correr:

   ```powershell
   wsl --install -d Ubuntu
   ```
3. Una vez terminado, podés abrir la terminal de Ubuntu desde el menú de Windows (o escribiendo `wsl` en PowerShell)

## 3) Actualizaciones básicas (dentro de Ubuntu)

```bash
sudo apt update && sudo apt upgrade -y
```

## 4) Configurar VS Code (trabajar *dentro* de WSL)

* Instalar **Visual Studio Code** en Windows.
* Instalar la extensión **Remote – WSL** (Microsoft).
* En la terminal de Ubuntu, posicionate en tu carpeta de trabajo y ejecutá:

  ```bash
  code .
  ```

  Esto abre VS Code conectado a WSL. Las extensiones (Python, Docker, etc.) se instalan del lado Linux automáticamente cuando hace falta.
* Opcional: dejar bash (WSL) como terminal por defecto en VS Code:

  * Settings → “Default Profile” → **Ubuntu (WSL)**.


## 5) Cómo compartir archivos entre Windows y Ubuntu

* Desde Ubuntu, tus discos de Windows están montados en `/mnt`:

  * Ejemplo: `cd /mnt/c/Users/TU-USUARIO/Downloads`
* Para **abrir el Explorador** desde la carpeta actual de Ubuntu:

  ```bash
  explorer.exe .
  ```