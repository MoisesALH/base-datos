<div>

# Gestión Empleados

<div align="center">
<img src="https://cdn.bizneo.com/blog/wp-content/uploads/2019/10/como-motivar-a-los-empleados.jpg" width="600px"/>
</div>

Dadas las siguientes tablas :
empleado:
  - codigo: entero
  - nif: texto
  - nombre: texto
  - apelllido1: texto
  - apelllido2: texto
  - codigo_departamento: entero

departamento
  - codigo: entero 
  - nombre: texto
  - presupuesto: real

Se pide:

Crea la estrucuta de tablas en función de las propiedades y sus nombres para determinar las claves primarias, claves foraneas. El fichero de la __BBDD__ debe de llamarse __empleados.db__.

Realiza la insercición de los datos siguientes:

```sql
INSERT INTO departamento VALUES(1, 'Desarrollo', 120000, 6000);
INSERT INTO departamento VALUES(2, 'Sistemas', 150000, 21000);
INSERT INTO departamento VALUES(3, 'Recursos Humanos', 280000, 25000);
INSERT INTO departamento VALUES(4, 'Contabilidad', 110000, 3000);
INSERT INTO departamento VALUES(5, 'I+D', 375000, 380000);
INSERT INTO departamento VALUES(6, 'Proyectos', 0, 0);
INSERT INTO departamento VALUES(7, 'Publicidad', 0, 1000);
INSERT INTO empleado VALUES(1, '32481596F', 'Aarón', 'Rivero', 'Gómez', 1);
INSERT INTO empleado VALUES(2, 'Y5575632D', 'Adela', 'Salas', 'Díaz', 2);
INSERT INTO empleado VALUES(3, 'R6970642B', 'Adolfo', 'Rubio', 'Flores', 3);
INSERT INTO empleado VALUES(4, '77705545E', 'Adrián', 'Suárez', NULL, 4);
INSERT INTO empleado VALUES(5, '17087203C', 'Marcos', 'Loyola', 'Méndez', 5);
INSERT INTO empleado VALUES(6, '38382980M', 'María', 'Santana', 'Moreno', 1);
INSERT INTO empleado VALUES(7, '80576669X', 'Pilar', 'Ruiz', NULL, 2);
INSERT INTO empleado VALUES(8, '71651431Z', 'Pepe', 'Ruiz', 'Santana', 3);
INSERT INTO empleado VALUES(9, '56399183D', 'Juan', 'Gómez', 'López', 2);
INSERT INTO empleado VALUES(10, '46384486H', 'Diego','Flores', 'Salas', 5);
INSERT INTO empleado VALUES(11, '67389283A', 'Marta','Herrera', 'Gil', 1);
INSERT INTO empleado VALUES(12, '41234836R', 'Irene','Salas', 'Flores', NULL);
INSERT INTO empleado VALUES(13, '82635162B', 'Juan Antonio','Sáez', 'Guerrero',
NULL);
```

Almacena el contenido en un fichero y realiza la inserción a través de la sentencia de __sqlite__ que consideres adecuada.
>Nota: Se debe de leer el fichero, utiliza el comando __.help__ para conocer el comando adecuado.

Realiza las siguientes consultas, indicando, la consulta y la salida que has obtenido.

## Consultas sobre una tabla

1. Lista el primer apellido de todos los empleados.
2. Lista el primer apellido de los empleados eliminando los apellidos que estén repetidos.
3. Lista todas las columnas de la tabla empleado.
4. Lista el nombre y los apellidos de todos los empleados.
5. Lista el identificador de los departamentos de los empleados que aparecen en la tabla empleado.
6. Lista el identificador de los departamentos de los empleados que aparecen en la tabla empleado, eliminando los identificadores que aparecen repetidos.
7. Lista el nombre y apellidos de los empleados en una única columna.
8. Lista el nombre y apellidos de los empleados en una única columna, convirtiendo todos los caracteres en
mayúscula.
9. Lista el nombre y apellidos de los empleados en una única columna, convirtiendo todos los caracteres en
minúscula.
10. Lista el identificador de los empleados junto al nif, pero el nif deberá aparecer en dos columnas, una
mostrará únicamente los dígitos del nif y la otra la letra.
11. Lista el nombre de cada departamento y el valor del presupuesto actual del que dispone. Para calcular
este dato tendrá que restar al valor del presupuesto inicial (columna presupuesto) los gastos que se
han generado (columna gastos). Tenga en cuenta que en algunos casos pueden existir valores negativos.
Utilice un alias apropiado para la nueva columna columna que está calculando.
12. Lista el nombre de los departamentos y el valor del presupuesto actual ordenado de forma ascendente.
13. Lista el nombre de todos los departamentos ordenados de forma ascendente.
14. Lista el nombre de todos los departamentos ordenados de forma desscendente.
15. Lista los apellidos y el nombre de todos los empleados, ordenados de forma alfabética tendiendo en
cuenta en primer lugar sus apellidos y luego su nombre.
16. Devuelve una lista con el nombre y el presupuesto, de los 3 departamentos que tienen mayor presupuesto.
17. Devuelve una lista con el nombre y el presupuesto, de los 3 departamentos que tienen menor presupuesto.
18. Devuelve una lista con el nombre y el gasto, de los 2 departamentos que tienen mayor gasto.
19. Devuelve una lista con el nombre y el gasto, de los 2 departamentos que tienen menor gasto.
20. Devuelve una lista con 5 filas a partir de la tercera fila de la tabla empleado. La tercera fila se debe incluir
en la respuesta. La respuesta debe incluir todas las columnas de la tabla empleado.
21. Devuelve una lista con el nombre de los departamentos y el presupuesto, de aquellos que tienen un presupuesto mayor o igual a 150000 euros.
22. Devuelve una lista con el nombre de los departamentos y el gasto, de aquellos que tienen menos de 5000
euros de gastos.
23. Devuelve una lista con el nombre de los departamentos y el presupesto, de aquellos que tienen un presupuesto entre 100000 y 200000 euros. Sin utilizar el operador BETWEEN.
24. Devuelve una lista con el nombre de los departamentos que no tienen un presupuesto entre 100000 y
200000 euros. Sin utilizar el operador BETWEEN.
25. Devuelve una lista con el nombre de los departamentos que tienen un presupuesto entre 100000 y 200000
euros. Utilizando el operador BETWEEN.
26. Devuelve una lista con el nombre de los departamentos que no tienen un presupuesto entre 100000 y
200000 euros. Utilizando el operador BETWEEN.
27. Devuelve una lista con el nombre de los departamentos, gastos y presupuesto, de quellos departamentos
donde los gastos sean mayores que el presupuesto del que disponen.
28. Devuelve una lista con el nombre de los departamentos, gastos y presupuesto, de aquellos departamentos donde los gastos sean menores que el presupuesto del que disponen.
29. Devuelve una lista con el nombre de los departamentos, gastos y presupuesto, de aquellos departamentos donde los gastos sean iguales al presupuesto del que disponen.
30. Lista todos los datos de los empleados cuyo segundo apellido sea NULL.
31. Lista todos los datos de los empleados cuyo segundo apellido no sea NULL.
32. Lista todos los datos de los empleados cuyo segundo apellido sea López.
33. Lista todos los datos de los empleados cuyo segundo apellido sea Díaz o Moreno. Sin utilizar el operador
IN.
34. Lista todos los datos de los empleados cuyo segundo apellido sea Díaz o Moreno. Utilizando el operador
IN.
35. Lista los nombres, apellidos y nif de los empleados que trabajan en el departamento 3.
36. Lista los nombres, apellidos y nif de los empleados que trabajan en los departamentos 2, 4 o 5.

## Consultas multitabla (Composición interna)

1. Devuelve un listado con los empleados y los datos de los departamentos donde trabaja cada uno.
2. Devuelve un listado con los empleados y los datos de los departamentos donde trabaja cada uno. Ordena
el resultado, en primer lugar por el nombre del departamento (en orden alfabético) y en segundo lugar
por los apellidos y el nombre de los empleados.
3. Devuelve un listado con el identificador y el nombre del departamento, solamente de aquellos departamentos que tienen empleados.
4. Devuelve un listado con el identificador, el nombre del departamento y el valor del presupuesto actual
del que dispone, solamente de aquellos departamentos que tienen empleados. El valor del presupuesto
actual lo puede calcular restando al valor del presupuesto inicial (columna presupuesto) el valor de los
gastos que ha generado (columna gastos).
5. Devuelve el nombre del departamento donde trabaja el empleado que tiene el nif 38382980M.
6. Devuelve el nombre del departamento donde trabaja el empleado Pepe Ruiz Santana.
7. Devuelve un listado con los datos de los empleados que trabajan en el departamento de I+D. Ordena el
resultado alfabéticamente.
8. Devuelve un listado con los datos de los empleados que trabajan en el departamento de Sistemas,
Contabilidad o I+D. Ordena el resultado alfabéticamente.
9. Devuelve una lista con el nombre de los empleados que tienen los departamentos que no tienen un presupuesto entre 100000 y 200000 euros.
10. Devuelve un listado con el nombre de los departamentos donde existe algún empleado cuyo segundo
apellido sea NULL. Tenga en cuenta que no debe mostrar nombres de departamentos que estén repetidos.
1.2.5 Consultas multitabla (Composición externa)
Resuelva todas las consultas utilizando las cláusulas LEFT JOIN y RIGHT JOIN.
1. Devuelve un listado con todos los empleados junto con los datos de los departamentos donde trabajan.
Este listado también debe incluir los empleados que no tienen ningún departamento asociado.
2. Devuelve un listado donde sólo aparezcan aquellos empleados que no tienen ningún departamento asociado.
3. Devuelve un listado donde sólo aparezcan aquellos departamentos que no tienen ningún empleado asociado.
4. Devuelve un listado con todos los empleados junto con los datos de los departamentos donde trabajan.
El listado debe incluir los empleados que no tienen ningún departamento asociado y los departamentos
que no tienen ningún empleado asociado. Ordene el listado alfabéticamente por el nombre del departamento.
5. Devuelve un listado con los empleados que no tienen ningún departamento asociado y los departamentos que no tienen ningún empleado asociado. Ordene el listado alfabéticamente por el nombre del departamento.
1.2.6 Consultas resumen
1. Calcula la suma del presupuesto de todos los departamentos.
2. Calcula la media del presupuesto de todos los departamentos.
3. Calcula el valor mínimo del presupuesto de todos los departamentos.
4. Calcula el nombre del departamento y el presupuesto que tiene asignado, del departamento con menor
presupuesto.
5. Calcula el valor máximo del presupuesto de todos los departamentos.
6. Calcula el nombre del departamento y el presupuesto que tiene asignado, del departamento con mayor
presupuesto.
7. Calcula el número total de empleados que hay en la tabla empleado.
8. Calcula el número de empleados que no tienen NULL en su segundo apellido.
9. Calcula el número de empleados que hay en cada departamento. Tienes que devolver dos columnas, una
con el nombre del departamento y otra con el número de empleados que tiene asignados.
10. Calcula el nombre de los departamentos que tienen más de 2 empleados. El resultado debe tener dos
columnas, una con el nombre del departamento y otra con el número de empleados que tiene asignados.
11. Calcula el número de empleados que trabajan en cada uno de los departamentos. El resultado de esta
consulta también tiene que incluir aquellos departamentos que no tienen ningún empleado asociado.
12. Calcula el número de empleados que trabajan en cada unos de los departamentos que tienen un presupuesto mayor a 200000 euros.

## Subconsultas

### Con operadores básicos de comparación

1. Devuelve un listado con todos los empleados que tiene el departamento de Sistemas. (Sin utilizar INNER
JOIN).
2. Devuelve el nombre del departamento con mayor presupuesto y la cantidad que tiene asignada.
3. Devuelve el nombre del departamento con menor presupuesto y la cantidad que tiene asignada.

### Subconsultas con IN y NOT IN

4. Devuelve los nombres de los departamentos que tienen empleados asociados. (Utilizando IN o NOT IN).
5. Devuelve los nombres de los departamentos que no tienen empleados asociados. (Utilizando IN o NOT
IN).

### Subconsultas con EXISTS y NOT EXISTS

10. Devuelve los nombres de los departamentos que tienen empleados asociados. (Utilizando EXISTS o NOT
EXISTS).
11. Devuelve los nombres de los departamentos que tienen empleados asociados. (Utilizando EXISTS o NOT
EXISTS).
</div>