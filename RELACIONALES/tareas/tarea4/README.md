<div>

<div align="center">
<img src="https://tuportaldelempleado.es/wp-content/uploads/empleados-logistica-1240x800.jpg" width="600px"/>
</div>

Dadas las siguientes tablas:

Empleado:
 - dni: texto
 - nombre: texto
 - apellido: texto
 > clave primaria(dni)
 > clave foranea(id)
 - ref_departamento: id_departamento

Departamento:
 - id entero
 - nombre: texto
 - presupuesto: entero
 > clave primaria(id)

Se pide realizar:
1. Crear la base de datos: BD_EMPLEADO.
2. Realiza la inserción de, al menos, 10 empleados.
3. Obtener los apellidos de los empleados.
4. Obtener los apellidos de los empleados sin repeticiones.
5. Obtener todos los datos de los empleados que se apellidan __López__.
6. Obtener todos los datos de los empleados que se apellidan __López__ y los que se apellidan __Pérez__.
7. Obtener todos los datos de los empleados que trabajan para el departamento __10__.
8. Obtener todos los datos de los empleados que trabajan para el departamento __8__ y para el departamento 5.
9. Obtener todos los datos de los empleados cuyo apellido comience por __P__.
10. Obtener el presupuesto total de todos los departamentos.
11. Obtener el número de empleados en cada departamento.
12. Obtener un listado completo de empleados, incluyendo por cada empleado los datos del empleado y de su departamento.
13. Obtener un listado completo de empleados, incluyendo el nombre y apellido del empleado junto al nombre y presupuesto de su departamento.
14. Obtener los nombres y apellido de los empleados que trabajen en departamentos cuyo presupuesto sea mayor de 60.000 €.
15. Obtener los datos de los departamentos cuyo presupuesto es superior al presupuesto medio de todos los departamentos.
16. Obtener los nombres (únicamente los nombres) de los departamentos que tiene más de dos empleados.
18. Añadir un nuevo departamento: “Calidad”, con presupuesto de 40.000 € y código 11.
19. Añadir un empleado vinculado al departamento recién creado: Esther Vázquez, DNI:00000000.
20. Calcular un recorte presupuestario del 10 % a todos los departamentos.
21. Despedir a todos los empleados que trabajan para el departamento de informática (código 2).
22. Despedir a todos los empleados que trabajen para departamentos cuyo presupuesto sea superior a los 60.000 €.
23. Despedir a todos los empleados.

Realiza:
- La creación de la BBDD_EMPLEADO, tal y como se indica en el punto 1.
- Inserción de Al menos 10 registros en cada una de las tablas, teniendo en cuenta que:
	- Deben de existir empleados que se apellidan __López__.
	- Debe existir al menos 10 departamentos.
	- Empleados cuyo apellido comience por __P__.
	- Presupuestos de al menos __60.000€__.
	- Insertar al empleado __Esther Vázquez, DNI:00000000__ relacionado con el departamento __11__.
	- El departamente _número 2_ debe de ser el de informática.

- Crear cada una de las sentencias sql para las consultas especificadas, siguiendo el siguiente patrón y almacenar en un _fichero de extensión_ ___.sql___ (Ej: _tarea_4_Nombre_Apellido1_Apellido.sql_).

```sql
-- sentencia sql de creación de la/s tabla/s de la bbdd


-- sentencia sql para la inserción de datos

-- Sentencia sql para cada una de las consultas especificadas.

--- 1. xxxxx



--- 22. xxxxx

```


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