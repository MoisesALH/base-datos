<div>

# Tienda Informática

<div align="center">
<img src="https://ultimainformatica.com/img/cms/TIENDAS/NIVARIA/CC%20NIVARIA_%208FEB_18_WEB.jpg" width="600px"/>
</div>

Dadas las siguientes tablas :
producto:
  - codigo: entero
  - nombre: texto
  - precio: real
  - codigo_fabricante: entero

fabricante
  - codigo: entero 
  - nombre: texto

Se pide:

Crea la estrucuta de tablas en función de las propiedades y sus nombres para determinar las claves primarias, claves foraneas. El fichero de la __BBDD__ debe de llamarse __tienda.db__.

Realiza la insercición de los datos siguientes:

```sql
INSERT INTO fabricante VALUES(1, 'Asus');
INSERT INTO fabricante VALUES(2, 'Lenovo');
INSERT INTO fabricante VALUES(3, 'Hewlett-Packard');
INSERT INTO fabricante VALUES(4, 'Samsung');
INSERT INTO fabricante VALUES(5, 'Seagate');
INSERT INTO fabricante VALUES(6, 'Crucial');
INSERT INTO fabricante VALUES(7, 'Gigabyte');
INSERT INTO fabricante VALUES(8, 'Huawei');
INSERT INTO fabricante VALUES(9, 'Xiaomi');
INSERT INTO producto VALUES(1, 'Disco duro SATA3 1TB', 86.99, 5);
INSERT INTO producto VALUES(2, 'Memoria RAM DDR4 8GB', 120, 6);
INSERT INTO producto VALUES(3, 'Disco SSD 1 TB', 150.99, 4);
INSERT INTO producto VALUES(4, 'GeForce GTX 1050Ti', 185, 7);
INSERT INTO producto VALUES(5, 'GeForce GTX 1080 Xtreme', 755, 6);
INSERT INTO producto VALUES(6, 'Monitor 24 LED Full HD', 202, 1);
INSERT INTO producto VALUES(7, 'Monitor 27 LED Full HD', 245.99, 1);
INSERT INTO producto VALUES(8, 'Portátil Yoga 520', 559, 2);
INSERT INTO producto VALUES(9, 'Portátil Ideapd 320', 444, 2);
INSERT INTO producto VALUES(10, 'Impresora HP Deskjet 3720', 59.99, 3);
INSERT INTO producto VALUES(11, 'Impresora HP Laserjet Pro M26nw', 180, 3);
```

Almacena el contenido en un fichero y realiza la inserción a través de la sentencia de __sqlite__ que consideres adecuada.
>Nota: Se debe de leer el fichero, utiliza el comando __.help__ para conocer el comando adecuado.

Realiza las siguientes consultas, indicando, la consulta y la salida que has obtenido.

## Consultas de repaso:
 - Lista el nombre de todos los productos que hay en la tabla producto.
 - Lista los nombres y los precios de todos los productos de la tabla producto.
 - Lista todas las columnas de la tabla producto.
 - Lista el nombre de los productos, el precio en euros y el precio en dólares estadounidenses (USD).
 - Lista el nombre de los productos, el precio en euros y el precio en dólares estadounidenses (USD). Utiliza los siguientes alias para las columnas: nombre de producto, euros, dólares.
 - Lista los nombres y los precios de todos los productos de la tabla producto, convirtiendo los nombres a mayúscula.
 - Lista los nombres y los precios de todos los productos de la tabla producto, convirtiendo los nombres a minúscula.
 - Lista el nombre de todos los fabricantes en una columna, y en otra columna obtenga en mayúsculas los dos primeros caracteres del nombre del fabricante.
 - Lista los nombres y los precios de todos los productos de la tabla producto, redondeando el valor del precio.
 - Lista los nombres y los precios de todos los productos de la tabla producto, truncando el valor del precio para mostrarlo sin ninguna cifra decimal.
 - Lista el identificador de los fabricantes que tienen productos en la tabla producto.
 - Lista el identificador de los fabricantes que tienen productos en la tabla producto, eliminando los identificadores que aparecen repetidos.
 - Lista los nombres de los fabricantes ordenados de forma ascendente.
 - Lista los nombres de los fabricantes ordenados de forma descendente.
 - Lista los nombres de los productos ordenados en primer lugar por el nombre de forma ascendente y en segundo lugar por el precio de forma descendente.
 - Devuelve una lista con las 5 primeras filas de la tabla fabricante.
 - Devuelve una lista con 2 filas a partir de la cuarta fila de la tabla fabricante. La cuarta fila también se debe incluir en la respuesta.
 - Lista el nombre y el precio del producto más barato. (Utilice solamente las cláusulas ORDER BY y LIMIT)
 - Lista el nombre y el precio del producto más caro. (Utilice solamente las cláusulas ORDER BY y LIMIT)
 - Lista el nombre de todos los productos del fabricante cuyo identificador de fabricante es igual a 2.
 - Lista el nombre de los productos que tienen un precio menor o igual a 120€.
 - Lista el nombre de los productos que tienen un precio mayor o igual a 400€.
 - Lista todos los productos que tengan un precio entre 80€ y 300€. Sin utilizar el operador BETWEEN.
 - Lista todos los productos que tengan un precio entre 60€ y 200€. Utilizando el operador BETWEEN.
 - Lista todos los productos que tengan un precio mayor que 200€ y que el identificador de fabricante sea igual a 6.
 - Lista todos los productos donde el identificador de fabricante sea 1, 3 o 5. Sin utilizar el operador IN.
 - Lista todos los productos donde el identificador de fabricante sea 1, 3 o 5. Utilizando el operador IN.
 - Lista el nombre y el precio de los productos en céntimos (Habrá que multiplicar por 100 el valor del precio). Cree un alias para la columna que contiene el precio que se llame céntimos.
 - Lista los nombres de los fabricantes cuyo nombre empiece por la letra S.
 - Lista los nombres de los fabricantes cuyo nombre termine por la vocal e.
 - Lista los nombres de los fabricantes cuyo nombre contenga el carácter w.
 - Lista los nombres de los fabricantes cuyo nombre sea de 4 caracteres.
 - Devuelve una lista con el nombre de todos los productos que contienen la cadena Portátil en el nombre.
 - Devuelve una lista con el nombre de todos los productos que contienen la cadena Monitor en el nombre y tienen un precio inferior a 215 €.
 - Lista el nombre y el precio de todos los productos que tengan un precio mayor o igual a 180€. Ordene el resultado en primer lugar por el precio (en orden descendente) y en segundo lugar por el nombre (en orden ascendente).

## Entrega

Se debe de entregar:
 - Un fichero __Nombre_Apellido1_Apellido2.sql__ con:
   - Sentencias para la creación de la BBDD.
   - Sentencias para la inserción de los elementos.
   - Sentencias con cada una de las consultas solicitadas.
 - Salida de datos en cada una de las consultas.
 - Fichero __tienda.db__.