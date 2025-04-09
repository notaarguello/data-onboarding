# Instalar psql (cliente PostgreSQL)

psql es el cliente de línea de comandos oficial de PostgreSQL. Permite conectarse a bases de datos, ejecutar consultas SQL y administrar el servidor.

**Sitio oficial:** https://www.postgresql.org/docs/current/app-psql.html

## Linux

```bash
sudo apt update
sudo apt install -y postgresql-client
psql --version
```

## Mac

```bash
brew install libpq
brew link --force libpq
psql --version
```

## Conexión básica

```bash
# Conectar a base de datos local
psql -U usuario -d base_de_datos

# Conectar a servidor remoto
psql -h host -p 5432 -U usuario -d base_de_datos

# Usando connection string
psql "postgresql://usuario:password@host:5432/base_de_datos"
```

## Cheatsheet

```bash
psql -U user -d db          # Conectar a base de datos
\l                          # Listar bases de datos
\dt                         # Listar tablas
\d tabla                    # Describir estructura de tabla
\q                          # Salir de psql
\i archivo.sql              # Ejecutar script SQL
```
