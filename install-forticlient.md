# Conectar VPN FortiClient desde terminal

openfortivpn es un cliente VPN open source compatible con Fortinet. Permite conectarse a VPNs FortiGate desde la línea de comandos.

**Sitio oficial:** https://github.com/adrienverge/openfortivpn

## Linux

```bash
# Ubuntu/Debian
sudo apt update
sudo apt install -y openfortivpn

# Verificar
openfortivpn --version
```

## Mac

```bash
brew install openfortivpn
openfortivpn --version
```

## Conexión básica

```bash
# Conectar (pedirá password)
sudo openfortivpn vpn.empresa.com:443 -u tu-usuario

# Conectar con password en variable (no recomendado en scripts)
sudo openfortivpn vpn.empresa.com:443 -u tu-usuario -p tu-password
```

## Configuración con archivo

Crear archivo `/etc/openfortivpn/config` (o `~/.config/openfortivpn/config`):

```ini
host = vpn.empresa.com
port = 443
username = tu-usuario
# password = tu-password  # Opcional, pedirá si no está
trusted-cert = FINGERPRINT_DEL_CERTIFICADO
```

Para obtener el fingerprint del certificado:
```bash
sudo openfortivpn vpn.empresa.com:443 -u tu-usuario 2>&1 | grep "certificate"
```

Conectar usando el archivo:
```bash
sudo openfortivpn -c /etc/openfortivpn/config
```

## Cheatsheet

```bash
sudo openfortivpn HOST:PORT -u USER        # Conectar con usuario
sudo openfortivpn -c /etc/openfortivpn/config  # Usar archivo config
sudo pkill openfortivpn                    # Desconectar VPN
openfortivpn --version                     # Ver versión instalada
```
