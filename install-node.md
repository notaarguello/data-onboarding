# Instalar Node.js con fnm

Node.js es un entorno de ejecución de JavaScript del lado del servidor. fnm (Fast Node Manager) es un gestor de versiones rápido escrito en Rust que permite instalar y cambiar entre múltiples versiones de Node.

**Sitio oficial Node:** https://nodejs.org
**Sitio oficial fnm:** https://github.com/Schniz/fnm

## Linux

```bash
# 1. Instalar fnm
curl -fsSL https://fnm.vercel.app/install | bash

# 2. Agregar al shell (el script lo hace automáticamente, pero verificar)
# Para bash:
echo 'eval "$(fnm env --use-on-cd --shell bash)"' >> ~/.bashrc
source ~/.bashrc

# Para zsh:
echo 'eval "$(fnm env --use-on-cd --shell zsh)"' >> ~/.zshrc
source ~/.zshrc

# 3. Instalar Node.js
fnm install 20
fnm use 20

# 4. Verificar
node -v
npm -v
```

## Mac

```bash
# 1. Instalar fnm con Homebrew
brew install fnm

# 2. Agregar al shell
# Para zsh (default en Mac):
echo 'eval "$(fnm env --use-on-cd --shell zsh)"' >> ~/.zshrc
source ~/.zshrc

# 3. Instalar Node.js
fnm install 20
fnm use 20

# 4. Verificar
node -v
npm -v
```

## Gestión de versiones

```bash
# Instalar versión específica
fnm install 18
fnm install 20
fnm install 22

# Cambiar versión
fnm use 18
fnm use 20

# Establecer versión por defecto
fnm default 20

# Ver versiones instaladas
fnm list

# Usar versión del archivo .node-version o .nvmrc automáticamente
# (ya configurado con --use-on-cd)
```

## Cheatsheet

```bash
fnm install 20        # Instalar Node 20
fnm use 20            # Usar Node 20
fnm list              # Listar versiones instaladas
fnm default 20        # Establecer versión por defecto
node -v               # Verificar versión activa
npm -v                # Verificar versión de npm
```
