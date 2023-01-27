<div>

<div align="center">
<img src="https://aluma3.com/wp-content/uploads/2021/08/Almacenes-Madrid-Paris.jpeg" width="600px"/>
</div>

Dadas las siguientes tablas:
- __caja__:
  - id: entero
  - contenido: texto
  - valor: entero
  > clave primaria(id)
  > clave foranea(id_almacen)
- __almacen__:
  - id: entero
  - lugar: texto
  - capacidad: entero
  > clave primaria(id)  

Se pide realizar:
- La creación de la BBDD_ALMACENES.
- Inserción de Al menos 20 registros en cada una de las tablas, teniendo en cuenta que:
	- Ingresar valores de cajas superior e inferior a __150__.
- Crear cada una de las sentencias sql para las consultas especificadas, siguiendo el siguiente patrón y almacenar en un _fichero de extensión_ ___.sql___ (Ej: _tarea_5_Nombre_Apellido1_Apellido.sql_).

```sql
-- sentencia sql de creación de la/s tabla/s de la bbdd


-- sentencia sql para la inserción de datos

-- Sentencia sql para cada una de las consultas especificadas.

--- 1. xxxxx

```

Consultas a realizar:
1. Obtener todos los almacenes
2. Obtener todas las cajas cuyo contenido tenga un valor superior a 150 €.
3. Obtener los tipos de contenidos de las cajas.
4. Obtener el valor medio de todas las cajas.
5. Obtener el valor medio de las cajas de cada almacén.
6. Obtener los códigos de los almacenes en los cuales el valor medio de las cajas sea superior a 150 €.
7. Obtener el numero de referencia de cada caja junto con el nombre de la ciudad en la que se encuentra.
8. Obtener el número de cajas que hay en cada almacén.
9. Obtener los códigos de los almacenes que están saturados (los almacenes donde el número de cajas es superior a la capacidad).
10. Obtener los números de referencia de las cajas que están en Bilbao.
11. Insertar un nuevo almacén en Madrid con capacidad para 3 cajas.
12. Insertar una nueva caja, con número de referencia __PH5__, con contenido __Papel__, valor
100, y situada en el almacén 2.
13. Rebajar el valor de todas las cajas un __15%__, dado que estamos en rebajas.
14. Rebajar un __20%__ el valor de todas las cajas cuyo valor sea superior al valor medio de todas las cajas.
15. Eliminar todas las cajas cuyo valor sea inferior a __100__.
16. Vaciar el contenido de los almacenes que están saturados.

</div>