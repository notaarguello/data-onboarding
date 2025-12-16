# Instalar Python con uv

 uv es un gestor de entornos muy rápido (escrito en Rust) que permite descargar versiones de Python, crear entornos virtuales y gestionar dependencias.

**Sitio oficial Python:** https://www.python.org
**Sitio oficial uv:** https://github.com/astral-sh/uv

## Linux

```bash
# 1. Instalar dependencias mínimas
sudo apt update
sudo apt install -y ca-certificates curl tar xz-utils

# 2. Instalar uv
curl -LsSf https://astral.sh/uv/install.sh | sh

# 3. Agregar al PATH
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc

# 4. Verificar
uv --version
```

## Mac

```bash
# 1. Instalar uv con Homebrew
brew install uv

# O con el script oficial:
curl -LsSf https://astral.sh/uv/install.sh | sh

# 2. Verificar
uv --version
```

## Instalar Python con uv

```bash
# Instalar Python 3.13
uv python install 3.13

# Ver versiones instaladas
uv python list

# Instalar múltiples versiones
uv python install 3.11 3.12 3.13
```

## Configurar proyecto

```bash
cd ~/code/tu-proyecto

# Crear entorno virtual con versión específica
uv venv --python 3.13 .venv

# Activar entorno (opcional, uv run no lo necesita)
source .venv/bin/activate

# Ejecutar sin activar
uv run python script.py
```

## Cheatsheet

```bash
uv python install 3.13        # Instalar versión de Python
uv venv .venv                 # Crear entorno virtual
uv pip install -r requirements.txt  # Instalar dependencias
uv run python script.py       # Ejecutar sin activar entorno
uvx ruff check .              # Ejecutar herramienta sin instalar
uv python list                # Ver versiones instaladas
```
