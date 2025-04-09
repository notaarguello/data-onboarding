# Instalar jq y yq

**jq** es un procesador de JSON en línea de comandos. Permite filtrar, transformar y extraer datos de archivos JSON.

**yq** es similar a jq pero para archivos YAML. Usa la misma sintaxis que jq.

**Sitio oficial jq:** https://jqlang.github.io/jq/
**Sitio oficial yq:** https://github.com/mikefarah/yq

## Linux

```bash
# Instalar jq
sudo apt-get update
sudo apt-get install -y jq

# Instalar yq
sudo wget -qO /usr/local/bin/yq "https://github.com/mikefarah/yq/releases/latest/download/yq_linux_amd64"
sudo chmod +x /usr/local/bin/yq

# Verificar
jq --version
yq --version
```

## Mac

```bash
brew install jq yq
jq --version
yq --version
```

## Cheatsheet jq

```bash
jq '.'  archivo.json            # Formatear JSON (pretty print)
jq '.clave' archivo.json        # Extraer valor de clave
jq '.items[]' archivo.json      # Iterar sobre array
jq '.items[] | .nombre' a.json  # Extraer campo de cada elemento
jq -r '.clave' archivo.json     # Output sin comillas (raw)
cat data.json | jq '.clave'     # Leer desde stdin
```

## Cheatsheet yq

```bash
yq '.' archivo.yaml             # Formatear YAML (pretty print)
yq '.clave' archivo.yaml        # Extraer valor de clave
yq '.items[]' archivo.yaml      # Iterar sobre array
yq -i '.clave = "valor"' a.yaml # Editar archivo in-place
yq -o=json archivo.yaml         # Convertir YAML a JSON
yq -P archivo.json              # Convertir JSON a YAML
```
