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

Solución:



1. Obtener todos los almacenes

```sql
	SELECT * FROM almacen;
```

2. Obtener todas las cajas cuyo contenido tenga un valor superior a 150 €,

```sql
	SELECT * FROM caja WHERE valor > 150;
```

3. Obtener los tipos de contenidos de las cajas.

```sql
	SELECT DISTINCT contenido FROM caja;
```
4. Obtener el valor medio de todas las cajas.

```sql
	SELECT AVG (valor) FROM caja;
```

5. Obtener el valor medio de las cajas de cada almacén.

```sql
	SELECT id_almacen, AVG(valor)
	FROM caja
	GROUP BY id_almacen
```

6. Obtener los códigos de los almacenes en los cuales el valor medio de las cajas sea superior a 150 €.

```sql
	SELECT id_almacen, AVG(valor)
	FROM caja
	GROUP BY id_almacen
	HAVING AVG(valor) > 150
```	

7. Obtener el numero de referencia de cada caja junto con el nombre de la
ciudad en la que se encuentra.

```sql
	SELECT id_caja, lugar
	FROM almacen INNER JOIN caja
	ON almacen.id_almacen = caja.ref_almacen
```

8. Obtener el número de cajas que hay en cada almacén.

```sql
	/* Esta consulta no tiene en cuenta los almacenes vacíos */
	SELECT id_almacen, COUNT(*)
	FROM caja
	GROUP BY id_almacen
	/* Esta consulta tiene en cuenta los almacenes vacíos */
	SELECT id_almacen, COUNT(id_caja)
	FROM almacen LEFT JOIN cajas
	ON almacen.id_almacen = caja.ref_almacen
	GROUP BY id_almacen
```	
9. Obtener los códigos de los almacenes que están saturados (los
almacenes donde el número de cajas es superior a la capacidad).

```sql
	SELECT id_almacen
	FROM almacen
	WHERE capacidad <
	(
	SELECT COUNT(*)
	FROM caja
	WHERE ref_almacen = id_almacen
	)
```

10. Obtener los números de referencia de las cajas que están en Bilbao.

```sql
	/* Sin subconsultas */
	SELECT id_caja
	FROM almacen LEFT JOIN CAJAS
	UN almacen.id_almacen = caja.ref_almacen
	WHERE Lugar = 'Bilbao'
	/* Con subconsultas */
	SELECT id_caja
	FROM caja
	WHERE ref_almacen IN
	(
	SELECT id_almacen
	FROM almacen
	WHERE Lugar = 'Bilbao'
	)
```

11. Insertar un nuevo almacén en Barcelona con capacidad para 3 cajas.

```sql
	INSERT INTO almacen (lugar,capacidad) VALUES('Barcelona',3);
```

12. Insertar una nueva caja, con número de referencia ”H5RT”, con contenido “Papel”, valor 200, y situada en el almacén 2.

```sql
	INSERT INTO caja
	VALUES('H5RT','Papel',200,2)
```

13. Rebajar el valor de todas las cajas un 15 %,

```sql
	UPDATE caja SET valor = valor * 0.85;
```

14. Rebajar un 20 % el valor de todas las cajas cuyo valor sea superior al valor medio de todas las cajas.

```sql
	UPDATE caja SET valor = valor * 0.80
	WHERE valor > (SELECT AVG(valor) FROM caja);
```

15. Eliminar todas las cajas cuyo valor sea inferior a 100

```sql
	DELETE FROM caja WHERE valor < 100;
```

16. Vaciar el contenido de los almacenes que están saturados.

```sql
	DELETE FROM caja WHERE ref_almacen IN
	(
	SELECT id_almacen
	FROM almacen
	WHERE capacidad <
	(SELECT COUNT(*)
	FROM caja WHERE ref_almacen = id_almacen)
	)
```

</div>