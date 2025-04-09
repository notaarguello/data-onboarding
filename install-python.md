# 1. Instalar uv
```bash
# 1. Instala dependencias mínimas para TLS y descompresión
sudo apt update
sudo apt install -y ca-certificates curl tar xz-utils

# 2. Instala uv en ~/.local/bin (sin sudo)
curl -LsSf https://astral.sh/uv/install.sh | sh

# 3. Asegurá el PATH (si hace falta)
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc

uv --version
```

# 2. Instalar python 3.13 con uv

```bash
uv python install 3.13
uv python list
```

# 3. Configurar proyecto para usar 3.13

```bash
cd ~/code/tu-proyecto
uv venv --python 3.13 .venv
# No hace falta "activar": podés ejecutar con uv
uv run python -V          # usa .venv/ con 3.13
```

## 7 ¿Qué es *uv*? (muy breve)

* **uv** es un gestor de entornos **muy rápido** para **Python**: descarga runtimes, crea entornos virtuales y gestiona dependencias.
* Comandos útiles:

  ```bash
  # crear entorno aislado y activarlo
  uv venv .venv
  source .venv/bin/activate

  # instalar dependencias en ese entorno
  uv pip install -r requirements.txt

  # ejecutar sin activar el entorno
  uv run python script.py

  # ejecutar herramientas sin instalarlas globalmente
  uvx ruff --version
  uvx pytest -q
```