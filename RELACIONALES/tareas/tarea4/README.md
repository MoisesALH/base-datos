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

</div>