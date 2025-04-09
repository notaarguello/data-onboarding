# Instalar DuckDB

DuckDB es una base de datos analítica embebida, similar a SQLite pero optimizada para consultas OLAP. Puede leer CSV, Parquet, JSON y otros formatos directamente sin importarlos.

**Sitio oficial:** https://duckdb.org

## Linux

```bash
# Descargar el binario
wget https://github.com/duckdb/duckdb/releases/latest/download/duckdb_cli-linux-amd64.zip
unzip duckdb_cli-linux-amd64.zip
sudo mv duckdb /usr/local/bin/

# Verificar
duckdb --version
```

## Mac

```bash
brew install duckdb
duckdb --version
```

## Uso básico

```bash
# Abrir shell interactivo
duckdb

# Abrir/crear base de datos persistente
duckdb mi_base.db

# Consultar archivo CSV directamente
duckdb -c "SELECT * FROM 'datos.csv' LIMIT 10"

# Consultar archivo Parquet
duckdb -c "SELECT * FROM 'datos.parquet' WHERE columna > 100"
```

## Cheatsheet

```bash
duckdb                        # Abrir shell interactivo
duckdb archivo.db             # Abrir/crear base de datos
.tables                       # Listar tablas (dentro del shell)
.read archivo.sql             # Ejecutar script SQL
SELECT * FROM 'data.csv';     # Consultar CSV directamente
COPY tabla TO 'out.parquet';  # Exportar a Parquet
```
