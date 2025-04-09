# Instalar GitHub CLI (gh)

GitHub CLI es la herramienta oficial de línea de comandos de GitHub. Permite crear PRs, revisar código, gestionar issues y más, directamente desde la terminal.

**Sitio oficial:** https://cli.github.com

## Linux

```bash
# Ubuntu/Debian
(type -p wget >/dev/null || (sudo apt update && sudo apt-get install wget -y)) \
  && sudo mkdir -p -m 755 /etc/apt/keyrings \
  && out=$(mktemp) && wget -nv -O$out https://cli.github.com/packages/githubcli-archive-keyring.gpg \
  && cat $out | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
  && sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
  && echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
  && sudo apt update \
  && sudo apt install gh -y

# Verificar
gh --version
```

## Mac

```bash
brew install gh
gh --version
```

## Autenticación

```bash
# Autenticarse (abre el navegador)
gh auth login

# Verificar estado
gh auth status
```

## Cheatsheet

```bash
gh auth login           # Autenticarse con GitHub
gh repo clone REPO      # Clonar repositorio
gh pr create            # Crear pull request
gh pr list              # Listar PRs del repo
gh issue list           # Listar issues
gh pr checkout NUMBER   # Checkout de un PR
```
