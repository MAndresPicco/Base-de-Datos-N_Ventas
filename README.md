Base de Datos Ventas

USE master;
GO
DROP DATABASE IF EXISTS Ventas;
GO

-- CREACION DE LA BASE DE DATOS
CREATE DATABASE Ventas;
GO
USE Ventas;
GO

-- =====================================================================
-- TABLA: clientes
-- =====================================================================
CREATE TABLE clientes (

    -- INT: numero entero, ideal para identificadores numericos sin decimales.
    -- IDENTITY(1,1): autoincremento automatico en SQL Server (equivale a AUTO_INCREMENT en MySQL).
    -- PRIMARY KEY: garantiza unicidad y es la referencia principal de la tabla.
    id_cliente     INT           NOT NULL IDENTITY(1,1) PRIMARY KEY,

    -- VARCHAR(100): texto de longitud variable hasta 100 caracteres.
    -- Elegido sobre CHAR porque los nombres no tienen longitud fija,
    -- VARCHAR no desperdicia espacio.
    nombre         VARCHAR(100)  NOT NULL,

    -- VARCHAR(MAX): texto largo sin limite fijo.
    -- Reemplaza al tipo TEXT (obsoleto en SQL Server) y acepta NOT NULL.
    -- Ideal para biografias o notas extensas sin longitud predecible.
    perfil_bio     VARCHAR(MAX)  NOT NULL,

    -- DATE: almacena solo fecha (dia/mes/ano), sin hora.
    -- Elegido sobre DATETIME porque solo necesitamos el dia de registro.
    fecha_registro DATE          NOT NULL

);
GO

-- =====================================================================
-- TABLA: productos
-- =====================================================================
CREATE TABLE productos (

    -- INT con IDENTITY: clave primaria autoincremental del producto.
    id_producto    INT           NOT NULL IDENTITY(1,1) PRIMARY KEY,

    -- VARCHAR(255): descripcion corta del producto.
    -- 255 es un limite clasico y suficiente para nombres de productos.
    descripcion    VARCHAR(255)  NOT NULL,

    -- DECIMAL(10,2): precision exacta para valores monetarios.
    -- Se evita FLOAT porque representa numeros de forma aproximada
    -- en binario, lo que puede generar errores de redondeo en dinero.
    -- DECIMAL(10,2) permite hasta 10 digitos con 2 decimales exactos.
    precio         DECIMAL(10,2) NOT NULL,

    -- VARCHAR(10): almacena 'activo' o 'inactivo' como texto.
    -- Alternativa legible a usar 0/1, facilita la lectura de los datos.
    esta_activo    VARCHAR(10)   NOT NULL

);
GO

SELECT * FROM clientes;
SELECT * FROM productos;
