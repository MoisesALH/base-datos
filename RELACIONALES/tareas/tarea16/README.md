<div align="justify">

# Gestión Ventas

<div align="center">
<img src="https://blog.homedepot.com.mx/wp-content/uploads/2019/10/Portada_Principiantes_01.jpg" width="600px"/>
</div>

Dada la base de datos para la gestion de una empresa de jardinería, que se encuentra en el fichero __file/jardineria.sql__, se pide:
  > __Nota__: En primer lugar, _verifica que el fichero es correcto_ y carga para la generación de la __BBDD__. Utiliza la sentencia _.read_ para la carga del fichero.

- Realiza la carga de datos a través del fichero ___file/insert_jardineria.sql__.
- Realiza la verificación que todas las tablas contienen datos a través de las funciones, _.schema_ y un __select * from nombre_tabla__.

___Apollate en las funciones del lenguaje sql y sqlite__:
- [Funciones de core](https://www.sqlite.org/lang_corefunc.html). 
- [Funciones de fechas](https://www.sqlite.org/lang_datefunc.html).

Realiza cada una de las siguientes consultas:

## Consultas sobre una tabla
1. Devuelve un listado con el código de oficina y la ciudad donde hay oficinas.
2. Devuelve un listado con la ciudad y el teléfono de las oficinas de España.
3. Devuelve un listado con el nombre, apellidos y email de los empleados cuyo jefe tiene un código de jefe igual a 7.
4. Devuelve el nombre del puesto, nombre, apellidos y email del jefe de la empresa.
5. Devuelve un listado con el nombre, apellidos y puesto de aquellos empleados que no sean representantes de ventas.
6. Devuelve un listado con el nombre de los todos los clientes españoles.
7. Devuelve un listado con los distintos estados por los que puede pasar un pedido.
8. Devuelve un listado con el código de cliente de aquellos clientes que realizaron algún pago en 2008. Tenga en cuenta que deberá eliminar aquellos códigos de cliente que aparezcan repetidos. 
9. Devuelve un listado con el código de pedido, código de cliente, fecha esperada y fecha de entrega de los pedidos que no han sido entregados a tiempo.
10. Devuelve un listado con el código de pedido, código de cliente, fecha esperada y fecha de entrega de los pedidos cuya fecha de entrega ha sido al menos dos días antes de la fecha esperada.
>__Nota__: Argumenta el camino para la solución.
11. Devuelve un listado de todos los pedidos que fueron rechazados en 2009.
12. Devuelve un listado de todos los pedidos que han sido entregados en el mes de enero de cualquier año.
13. Devuelve un listado con todos los pagos que se realizaron en el año 2008 mediante Paypal. Ordene el resultado de mayor a menor.
14. Devuelve un listado con todas las formas de pago que aparecen en la tabla pago. Tenga en cuenta que no deben aparecer formas de pago repetidas.
15. Devuelve un listado con todos los productos que pertenecen a la gama Ornamentales y que tienen más de 100 unidades en stock. El listado deberá estar ordenado por su precio de venta, mostrando en primer lugar los de mayor precio.
16. Devuelve un listado con todos los clientes que sean de la ciudad de Madrid y cuyo representante de ventas tenga el código de empleado 11 o 30.

## Consultas multitabla (JOIN´s).

17. Obtén un listado con el nombre de cada cliente y el nombre y apellido de su representante de ventas.
18. Muestra el nombre de los clientes que hayan realizado pagos junto con el nombre de sus representantes de ventas.
19. Muestra el nombre de los clientes que no hayan realizado pagos junto con el nombre de sus representantes de ventas.
20. Devuelve el nombre de los clientes que han hecho pagos y el nombre de sus representantes junto con la ciudad de la oficina a la que pertenece el representante.
21. Devuelve el nombre de los clientes que no hayan hecho pagos y el nombre de sus representantes junto con la ciudad de la oficina a la que pertenece el representante.
22. Lista la dirección de las oficinas que tengan clientes en Fuenlabrada.
23. Devuelve el nombre de los clientes y el nombre de sus representantes junto con la ciudad de la oficina a la que pertenece el representante.
24. Devuelve un listado con el nombre de los empleados junto con el nombre de sus jefes.
25. Devuelve un listado que muestre el nombre de cada empleados, el nombre de su jefe y el nombre del jefe de sus jefe.
26. Devuelve el nombre de los clientes a los que no se les ha entregado a tiempo un pedido.
27. Devuelve un listado de las diferentes gamas de producto que ha comprado cada cliente.

## Consultas multitabla (LEFT JOIN, RIGHT JOIN)

28. Devuelve un listado que muestre solamente los clientes que no han realizado ningún pago.
29. Devuelve un listado que muestre solamente los clientes que no han realizado ningún pedido.
30. Devuelve un listado que muestre los clientes que no han realizado ningún pago y los que no han realizado ningún pedido.
31. Devuelve un listado que muestre solamente los empleados que no tienen una oficina asociada.
32. Devuelve un listado que muestre solamente los empleados que no tienen un cliente asociado.
33. Devuelve un listado que muestre solamente los empleados que no tienen un cliente asociado junto con los datos de la oficina donde trabajan.
34. Devuelve un listado que muestre los empleados que no tienen una oficina asociada y los que no tienen un cliente asociado.
35. Devuelve un listado de los productos que nunca han aparecido en un pedido.
36. Devuelve un listado de los productos que nunca han aparecido en un pedido. El resultado debe mostrar el nombre, la descripción y la imagen del producto.
37. Devuelve las oficinas donde no trabajan ninguno de los empleados que hayan sido los representantes de ventas de algún cliente que haya realizado la compra de algún producto de la gama Frutales.
38. Devuelve un listado con los clientes que han realizado algún pedido pero no han realizado ningún pago.
39. Devuelve un listado con los datos de los empleados que no tienen clientes asociados y el nombre de su jefe asociado.

## Consultas resumen
40. ¿Cuántos empleados hay en la compañía?
41. ¿Cuántos clientes tiene cada país?
42. ¿Cuál fue el pago medio en 2009?
43. ¿Cuántos pedidos hay en cada estado? Ordena el resultado de forma descendente por el número de pedidos.
44. Calcula el precio de venta del producto más caro y más barato en una misma consulta.
45. Calcula el número de clientes que tiene la empresa.
46. ¿Cuántos clientes existen con domicilio en la ciudad de Madrid?
47. ¿Calcula cuántos clientes tiene cada una de las ciudades que empiezan por M?
48. Devuelve el nombre de los representantes de ventas y el número de clientes al que atiende cada uno.
49. Calcula el número de clientes que no tiene asignado representante de ventas.
50. Calcula la fecha del primer y último pago realizado por cada uno de los clientes. El listado deberá mostrar el nombre y los apellidos de cada cliente.
51. Calcula el número de productos diferentes que hay en cada uno de los pedidos.
52. Calcula la suma de la cantidad total de todos los productos que aparecen en cada uno de los pedidos.
53. Devuelve un listado de los 20 productos más vendidos y el número total de unidades que se han vendido de cada uno. El listado deberá estar ordenado por el número total de unidades vendidas.
54. La facturación que ha tenido la empresa en toda la historia, indicando la base imponible, el IVA y el total facturado. La base imponible se calcula sumando el coste del producto por el número de unidades vendidas de la tabla detalle_pedido. El IVA es el 21 % de la base imponible, y el total la suma de los dos campos anteriores.
55. La misma información que en la pregunta anterior, pero agrupada por código de producto.
56. La misma información que en la pregunta anterior, pero agrupada por código de producto filtrada por los códigos que empiecen por OR.
57. Lista las ventas totales de los productos que hayan facturado más de 3000 euros. Se mostrará el nombre, unidades vendidas, total facturado y total facturado con impuestos (21% IVA).
58. Muestre la suma total de todos los pagos que se realizaron para cada uno de los años que aparecen en la tabla pagos.

## Subconsultas
### Con operadores básicos de comparación
59. Devuelve el nombre del cliente con mayor límite de crédito.
60. Devuelve el nombre del producto que tenga el precio de venta más caro.
61. Devuelve el nombre del producto del que se han vendido más unidades. (Tenga en cuenta que tendrá que calcular cuál es el número total de unidades que se han vendido de cada producto a partir de los datos de la tabla detalle_pedido)
62. Los clientes cuyo límite de crédito sea mayor que los pagos que haya realizado. (Sin utilizar INNER JOIN).
63. Devuelve el producto que más unidades tiene en stock.
64. Devuelve el producto que menos unidades tiene en stock.
65. Devuelve el nombre, los apellidos y el email de los empleados que están a cargo de Alberto Soria.

### Subconsultas con IN y NOT IN
66. Devuelve el nombre, apellido1 y cargo de los empleados que no representen a ningún cliente.
67. Devuelve un listado que muestre solamente los clientes que no han realizado ningún pago.
68. Devuelve un listado que muestre solamente los clientes que sí han realizado algún pago.
69. Devuelve un listado de los productos que nunca han aparecido en un pedido.
70. Devuelve el nombre, apellidos, puesto y teléfono de la oficina de aquellos empleados que no sean representante de ventas de ningún cliente.
71. Devuelve las oficinas donde no trabajan ninguno de los empleados que hayan sido los representantes de ventas de algún cliente que haya realizado la compra de algún producto de la gama Frutales.
72. Devuelve un listado con los clientes que han realizado algún pedido pero no han realizado ningún pago.

## Subconsultas con EXISTS y NOT EXISTS
73. Devuelve un listado que muestre solamente los clientes que no han realizado ningún pago.
74. Devuelve un listado que muestre solamente los clientes que sí han realizado algún pago.
75. Devuelve un listado de los productos que nunca han aparecido en un pedido.
76. Devuelve un listado de los productos que han aparecido en un pedido alguna vez.

## Subconsultas correlacionadas

77. Devuelve el listado de clientes indicando el nombre del cliente y cuántos pedidos ha realizado. Tenga en cuenta que pueden existir clientes que no han realizado ningún pedido.
78. Devuelve un listado con los nombres de los clientes y el total pagado por cada uno de ellos. Tenga en cuenta que pueden existir clientes que no han realizado ningún pago.
79. Devuelve el nombre de los clientes que hayan hecho pedidos en 2008 ordenados alfabéticamente de menor a mayor.
80. Devuelve el nombre del cliente, el nombre y primer apellido de su representante de ventas y el número de teléfono de la oficina del representante de ventas, de aquellos clientes que no hayan realizado ningún pago.
81. Devuelve el listado de clientes donde aparezca el nombre del cliente, el nombre y primer apellido de su representante de ventas y la ciudad donde está su oficina.
82. Devuelve el nombre, apellidos, puesto y teléfono de la oficina de aquellos empleados que no sean representante de ventas de ningún cliente.
83. Devuelve un listado indicando todas las ciudades donde hay oficinas y el número de empleados que tiene.


</div>