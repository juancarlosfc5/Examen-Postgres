## Arquitectura Hexagonal

Antes de iniciar el programa verifique los datos de conexion a Postgres en el archivo Program.cs verificando la siguiente linea y ajustando la contraseña

string connStr = "Host=localhost;database=introcsharp;Port=5432;Username=postgres;Password=123456;Pooling=true;";

Posteriormente cree la base de datos de Postgres ejecutando el siguiente codigo DML

-- Eliminar base de datos si ya existe
DROP DATABASE IF EXISTS introcsharp;

-- Crear base de datos
CREATE DATABASE introcsharp;

-- Conectarse a la base de datos
\c introcsharp;

-- Eliminar tablas si ya existen
DROP TABLE IF EXISTS productos;
DROP TABLE IF EXISTS clientes;

-- Crear tabla clientes
CREATE TABLE clientes (
    id SERIAL PRIMARY KEY,
    nombre VARCHAR(100),
    direccion VARCHAR(100)
);

-- Crear tabla productos
CREATE TABLE productos (
    id SERIAL PRIMARY KEY,
    nombre VARCHAR(100),
    stock INTEGER
);