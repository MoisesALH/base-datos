<div>

<div align="center">
<img src="https://ultimainformatica.com/img/cms/TIENDAS/NIVARIA/CC%20NIVARIA_%208FEB_18_WEB.jpg" width="600px"/>
</div>

Dadas las siguientes tablas :

Fabricante:
 - clave: texto
 - nombre: texto
 > clave primaria(dni)

Articulo:
 - clave entero
 - nombre: texto
 - precio: entero
 > clave primaria(clave)
 > claver foranea(clave_fabricante)

Se pide realizar:
1. Realiza la inserción:

```sql
INSERT INTO fabricante VALUES (1 ,
`Kingston`);
INSERT INTO fabricant VALUES (2 ,
`Adata`);
INSERT INTO fabricante VALUES (3 ,
`Logitech`);
INSERT INTO fabricante VALUES (4 ,
`Lexar`);
INSERT INTO fabricante VALUES (5 ,
`Seagate`);
```

### Articulo
| clave | nombre | precio | clave_fabricante |
| -----| -----| -----| -----|
| 1 | Teclado | 100 | 3 | 
| 2 | Disco duro 300 Gb | 500 | 5| 
| 3 | Mouse | 80 | 3 | 
| 4 | Memoria USB | 140 | 4 | 
| 5 | Memoria RAM 290 | 1 | 
| 6 | Disco duro extraíble 250 Gb|   650 | 5 | 
| 7 | Memoria USB | 279 | 1 | 
| 8 | DVD Rom | 450 | 2 | 
| 9 | CD Rom | 200 | 2 | 
| 10 | Tarjeta de red | 180 | 3 | 

Realizar las siguientes consultas:

1. Obtener todos los datos de los productos de la tienda.
2. Obtener los nombres de los productos de la tienda.
3. Obtener los nombres y precio de los productos de la tienda.
Obtener los nombres de los artículos sin repeticiones.
4. Obtener todos los datos del artículo cuya clave de producto es __5__.
5. Obtener todos los datos del artículo cuyo nombre del producto es __Teclado__.
6. Obtener todos los datos de la Memoria RAM y memorias USB.
7. Obtener todos los datos de los artículos que empiezan con __M__.
8. Obtener el nombre de los productos donde el precio sea __100__.
9. Obtener el nombre de los productos donde el precio sea mayor a __200__.
10. Obtener todos los datos de los artículos cuyo precio este entre __100 y 350__.
11. Obtener el precio medio de todos los productos.
12. Obtener el precio medio de los artículos cuyo código de fabricante sea __2__.
13. Obtener el nombre y precio de los artículos ordenados por __Nombre__.
14. Obtener todos los datos de los productos ordenados descendentemente por __Precio__.
15. Obtener el nombre y precio de los artículos cuyo precio sea mayor a __250__ y __ordenarlos descendentemente por precio__ y luego __ascendentemente por nombre__.
16. Obtener un listado completo de los productos, incluyendo por cada articulo los __datos del articulo y del fabricante__.
17. Obtener la clave de producto, __nombre del producto y nombre del fabricante__ de todos los productos en venta.
18. Obtener el nombre y precio de los artículos donde el fabricante sea Logitech ordenarlos __alfabéticamente por
nombre del producto__.
19. Obtener el nombre, precio y nombre de fabricante de los productos que son marca Lexar o __Kingston__ ordenados descendentemente por precio.
20. Añade un nuevo producto: Clave del producto __11__, __Altavoces de 120__ del fabricante __2__.
21. Cambia el nombre del producto __6__ a __Impresora Laser__.
22. Aplicar un descuento del __10%__ a todos los productos.
23. Aplicar un descuento de __10__ a todos los productos cuyo precio sea mayor o igual a __300__.
24. Borra el producto número __6__.

__Se pide__:crear cada una de las sentencias sql solicitadas (creación de tablas, inserción de datos, y consultas solicitas) siguiendo el siguiente patrón y almacenar en un _fichero de extensión_ ___.sql___ (Ej: _tarea_6_Nombre_Apellido1_Apellido.sql_).

```sql
-- sentencia sql de creación de la/s tabla/s de la bbdd


-- sentencia sql para la inserción de datos

-- Sentencia sql para cada una de las consultas especificadas.

--- 1. xxxxx



--- 22. xxxxx

```

</div>