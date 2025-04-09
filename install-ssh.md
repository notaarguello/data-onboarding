# Configurar SSH

SSH (Secure Shell) es el protocolo estándar para conexiones seguras a servidores remotos y para autenticarse con servicios como GitHub mediante claves públicas/privadas.

**Documentación:** https://www.openssh.com/manual.html

## Linux

```bash
# 1. Generar clave SSH (usar tu email)
ssh-keygen -t ed25519 -C "tu-email@ejemplo.com"

# 2. Iniciar el agente SSH
eval "$(ssh-agent -s)"

# 3. Agregar la clave al agente
ssh-add ~/.ssh/id_ed25519

# 4. Ver la clave pública (copiar para GitHub, GitLab, etc.)
cat ~/.ssh/id_ed25519.pub
```

## Mac

```bash
# 1. Generar clave SSH (usar tu email)
ssh-keygen -t ed25519 -C "tu-email@ejemplo.com"

# 2. Iniciar el agente SSH
eval "$(ssh-agent -s)"

# 3. Agregar la clave al agente (con Keychain)
ssh-add --apple-use-keychain ~/.ssh/id_ed25519

# 4. Ver la clave pública (copiar para GitHub, GitLab, etc.)
cat ~/.ssh/id_ed25519.pub
```

## Configurar múltiples claves SSH

Si tenés múltiples cuentas (ej: GitHub personal y trabajo), creá un archivo `~/.ssh/config`:

```bash
# Cuenta personal de GitHub
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_personal
    AddKeysToAgent yes

# Cuenta de trabajo de GitHub
Host github-trabajo
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_trabajo
    AddKeysToAgent yes

# Servidor de producción
Host prod
    HostName 192.168.1.100
    User deploy
    IdentityFile ~/.ssh/id_ed25519_prod
```

Para clonar con la cuenta de trabajo:
```bash
git clone git@github-trabajo:empresa/repo.git
```

## Cheatsheet

```bash
ssh-keygen -t ed25519 -C "email"  # Generar nueva clave
ssh-add ~/.ssh/id_ed25519         # Agregar clave al agente
ssh user@host                     # Conectar a servidor
ssh -i ~/.ssh/otra_clave host     # Usar clave específica
cat ~/.ssh/id_ed25519.pub         # Ver clave pública
ssh -T git@github.com             # Probar conexión a GitHub
```
