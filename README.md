# Base-de-Datos-N_Ventas
Ejercicio 1 Módulo 3
--CREACION BASE DE DATOS
CREATE DATABASE Ventas;

--CREACION TABLA CLIENTES
CREATE TABLE clientes (
id_cliente int NOT NULL IDENTITY (1,1) PRIMARY KEY,
nombre_cliente varchar(100) NOT NULL,
perfil_bio text NOT NULL,
fecha_regustro date NOT NULL,
); 

SELECT *FROM clientes

--CREACIÓN TABLA PRODUCTOS
CREATE TABLE productos (
id_producto int NOT NULL IDENTITY (1,1) PRIMARY KEY,
descripcion varchar(255) NOT NULL,
precio decimal (10,2) NOT NULL,
esta_activo varchar (10) NOT NULL,
);


SELECT *FROM productos
