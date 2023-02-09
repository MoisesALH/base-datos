<div>

# Tienda Informática

<div align="center">
<img src="https://ultimainformatica.com/img/cms/TIENDAS/NIVARIA/CC%20NIVARIA_%208FEB_18_WEB.jpg" width="600px"/>
</div>

Siguiento con la tarea anterior, recordando que las tablas tenían la estructura siguiente:

producto:
  - codigo: entero
  - nombre: texto
  - precio: real
  - codigo_fabricante: entero

fabricante
  - codigo: entero 
  - nombre: texto


Almacena el contenido en un fichero y realiza la inserción a través de la sentencia de __sqlite__ que consideres adecuada.
>Nota: Se debe de leer el fichero, utiliza el comando __.help__ para conocer el comando adecuado.

Realiza las siguientes consultas, indicando, la consulta y la salida que has obtenido.

## Consultas Multitabla:

### Consultas con multitabla con clausula where:

- Devuelve una lista con el nombre del producto, precio y nombre de fabricante de todos los productos de la base de datos.
- Devuelve una lista con el nombre del producto, precio y nombre de fabricante de todos los productos de la base de datos. Ordene el resultado por el nombre del fabricante, por orden alfabético.
- Devuelve una lista con el identificador del producto, nombre del producto, identificador del fabricante y nombre del fabricante, de todos los productos de la base de datos.
- Devuelve el nombre del producto, su precio y el nombre de su fabricante, del producto más barato.
- Devuelve el nombre del producto, su precio y el nombre de su fabricante, del producto más caro.
- Devuelve una lista de todos los productos del fabricante Lenovo.
- Devuelve una lista de todos los productos del fabricante Crucial que tengan un precio mayor que 200€.
- Devuelve un listado con todos los productos de los fabricantes Asus, Hewlett-Packardy Seagate. Sin utilizar el operador IN.
- Devuelve un listado con todos los productos de los fabricantes Asus, Hewlett-Packardy Seagate. Utilizando el operador IN.
- Devuelve un listado con el nombre y el precio de todos los productos de los fabricantes cuyo nombre termine por la vocal e.
- Devuelve un listado con el nombre y el precio de todos los productos cuyo nombre de fabricante contenga el carácter w en su nombre.
- Devuelve un listado con el nombre de producto, precio y nombre de fabricante, de todos los productos que tengan un precio mayor o igual a 180€. Ordene el resultado en primer lugar por el precio (en orden descendente) y en segundo lugar por el nombre (en orden ascendente)
- Devuelve un listado con el identificador y el nombre de fabricante, solamente de aquellos fabricantes que tienen productos asociados en la base de datos.

### Consultas con multitabla con LEFT JOIN y RIGHT JOIN
- Devuelve un listado de todos los fabricantes que existen en la base de datos, junto con los productos que tiene cada uno de ellos. El listado deberá mostrar también aquellos fabricantes que no tienen productos asociados.
- Devuelve un listado donde sólo aparezcan aquellos fabricantes que no tienen ningún producto asociado.
>__Nota:__¿Pueden existir productos que no estén relacionados con un fabricante? Justifique su respuesta.

### Consultas realizando calculos

- Calcula el número total de productos que hay en la tabla productos.
- Calcula el número total de fabricantes que hay en la tabla fabricante.
- Calcula el número de valores distintos de identificador de fabricante aparecen en la tabla productos.
- Calcula la media del precio de todos los productos.
- Calcula el precio más barato de todos los productos.
- Calcula el precio más caro de todos los productos.
- Lista el nombre y el precio del producto más barato.
- Lista el nombre y el precio del producto más caro.
- Calcula la suma de los precios de todos los productos.
- Calcula el número de productos que tiene el fabricante Asus.
- Calcula la media del precio de todos los productos del fabricante Asus.
- Calcula el precio más barato de todos los productos del fabricante Asus.
- Calcula el precio más caro de todos los productos del fabricante Asus.
- Calcula la suma de todos los productos del fabricante Asus.
- Muestra el precio máximo, precio mínimo, precio medio y el número total de productos que tiene el fabricante Crucial.
- Muestra el número total de productos que tiene cada uno de los fabricantes. El listado también debe incluir los fabricantes que no tienen ningún producto. El resultado mostrará dos columnas, una con el nombre del fabricante y otra con el número de productos que tiene. Ordene el resultado descendentemente por el número de productos.
- Muestra el precio máximo, precio mínimo y precio medio de los productos de cada uno de los fabricantes. El resultado mostrará el nombre del fabricante junto con los datos que se solicitan.
- Muestra el precio máximo, precio mínimo, precio medio y el número total de productos de los fabricantes que tienen un precio medio superior a 200€. No es necesario mostrar el nombre del fabricante, con el identificador del fabricante es suficiente.
- Muestra el nombre de cada fabricante, junto con el precio máximo, precio mínimo, precio medio y el número total de productos de los fabricantes que tienen un precio medio superior a 200€. Es necesario mostrar el nombre del fabricante.
- Calcula el número de productos que tienen un precio mayor o igual a 180€.
- Calcula el número de productos que tiene cada fabricante con un precio mayor o igual a 180€.
- Lista el precio medio los productos de cada fabricante, mostrando solamente el identificador del fabricante.
- Lista el precio medio los productos de cada fabricante, mostrando solamente el nombre del fabricante.
- Lista los nombres de los fabricantes cuyos productos tienen un precio medio mayor o igual a 150€.
- Devuelve un listado con los nombres de los fabricantes que tienen 2 o más productos.
- Devuelve un listado con los nombres de los fabricantes y el número de productos que tiene cada uno con un precio superior o igual a 220 €. No es necesario mostrar el nombre de los fabricantes que no tienen productos que cumplan la condición.

> Ejemplo del resultado esperado:

| nombre	| total |
| ----- |  ----- |
| Lenovo | 2 |
| .... | .. |

- Devuelve un listado con los nombres de los fabricantes y el número de productos que tiene cada uno con un precio superior o igual a 220 €. El listado debe mostrar el nombre de todos los fabricantes, es decir, si hay algún fabricante que no tiene productos con un precio superior o igual a 220€ deberá aparecer en el listado con un valor igual a 0 en el número de productos.

Ejemplo del resultado esperado:

| nombre	| total |
| ----- |  ----- |
| Lenovo | 2 |
| .... | .. |

- Devuelve un listado con los nombres de los fabricantes donde la suma del precio de todos sus productos es superior a 1000 €.
- Devuelve un listado con el nombre del producto más caro que tiene cada fabricante. El resultado debe tener tres columnas: nombre del producto, precio y nombre del fabricante. El resultado tiene que estar ordenado alfabéticamente de menor a mayor por el nombre del fabricante.

### Subconsultas (En la cláusula WHERE)(Sin utilizar INNER JOIN)

- Devuelve todos los productos del fabricante Lenovo. (Sin utilizar INNER JOIN).
- Devuelve todos los datos de los productos que tienen el mismo precio que el producto más caro del fabricante Lenovo. (Sin utilizar INNER JOIN).
- Lista el nombre del producto más caro del fabricante Lenovo.
- Lista el nombre del producto más barato del fabricante Hewlett-Packard.
- Devuelve todos los productos de la base de datos que tienen un precio mayor o igual al producto más caro del fabricante Lenovo.
- Lista todos los productos del fabricante Asus que tienen un precio superior al precio medio de todos sus productos.

### Subconsultas con ALL y ANY

- Devuelve el producto más caro que existe en la tabla producto sin hacer uso de MAX, ORDER BY ni LIMIT.
- Devuelve el producto más barato que existe en la tabla producto sin hacer uso de MIN, ORDER BY ni LIMIT.
- Devuelve los nombres de los fabricantes que tienen productos asociados. (Utilizando ALL o ANY).
- Devuelve los nombres de los fabricantes que no tienen productos asociados. (Utilizando ALL o ANY).

### Subconsultas con IN y NOT IN

- Devuelve los nombres de los fabricantes que tienen productos asociados. (Utilizando IN o NOT IN).
- Devuelve los nombres de los fabricantes que no tienen productos asociados. (Utilizando IN o NOT IN).

###  Subconsultas con EXISTS y NOT EXISTS

- Devuelve los nombres de los fabricantes que tienen productos asociados. (Utilizando EXISTS o NOT EXISTS).
- Devuelve los nombres de los fabricantes que no tienen productos asociados. (Utilizando EXISTS o NOT EXISTS).

###  Subconsultas correlacionadas

- Lista el nombre de cada fabricante con el nombre y el precio de su producto más caro.
- Devuelve un listado de todos los productos que tienen un precio mayor o igual a la media de todos los productos de su mismo fabricante.
- Lista el nombre del producto más caro del fabricante Lenovo.

###  Subconsultas (En la cláusula HAVING)

- Devuelve un listado con todos los nombres de los fabricantes que tienen el mismo número de productos que el fabricante Lenovo.

## Entrega

Se debe de entregar:
 - Un fichero __Nombre_Apellido1_Apellido2.sql__ con:
   - Sentencias para la creación de la BBDD.
   - Sentencias para la inserción de los elementos.
   - Sentencias con cada una de las consultas solicitadas.
 - Salida de datos en cada una de las consultas.
 - Fichero __tienda.db__.