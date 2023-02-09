<div>

<div align="center">
<img src="https://culturacientifica.com/app/uploads/2016/03/Left-handed-facts-Einstein.jpg" width="600px"/>
</div>

Dadas las siguientes tablas :
cientifico:
  - id: texto
  - nombre: texto
  - apellido1: texto
  - apellido2: texto

cientifico_proyecto
  - ref_cientifico:  texto 
  - ref_proyecto:  texto

proyecto:
  - id: texto
  - nombre: texto
  - horas: entero

Se pide:

Crea la estrucuta de tablas en función de las propiedades y sus nombres para determinar las claves primarias, claves foraneas.

Realiza la insercición de almenos 10 científicos, 5 proyectos y la relación entre estos.

Realizar las siguientes consultas:
1. Sacar una relación completa de los científicos asignados a cada proyecto. Mostrar DNI, Nombre del científico, identificador del proyecto y nombre del proyecto.
2. Obtener el número de proyectos al que está asignado cada científico (mostrar el DNI y el nombre).
3. Obtener el numero de científicos asignados a cada proyecto (mostrar el identificador del proyecto y el nombre del proyecto).
4. Obtener el número de horas de dedicación de cada científico.
5. Obtener el DNI y nombre de los científicos que se dedican a más de un proyecto y cuya dedicación media a cada proyecto sea superior __a un número de horas superior a 10, por ejemplo 11 horas__.

Se debe de entregar un fichero _Nombre_Apellido1_Apellido2.sql_ con:
- Sentencias para la creación de la BBDD.
- Sentencias para la inserción de los elementos.
- Sentencias con cada una de las consultas solicitadas.

__Solución__:

1. Sacar una relación completa de los científicos asignados a cada proyecto. Mostrar
DNI, Nombre del científico, identificador del proyecto y nombre del proyecto.

```sql
/* sin JOIN */
SELECT id, nombre, apellido1, apellido2, id_proyecto, Nombre
FROM cientifico C, cientifico_proyecto A, proyecto P
WHERE C.id = A.Cientifico
AND A.ref_proyecto = P. id_proyecto
/* Con JOIN */
SELECT DNI, nombre, apellido1, apellido2, id_proyecto, nombre
FROM cientifico C INNER JOIN
(cientifico_proyecto A INNER JOIN proyecto P
ON A.ref_proyecto = P.id_proyecto)
ON C. id = A.ref_cientifico
```

2. Obtener el número de proyecto al que está asignado cada científico (mostrar el
DNI y el nombre).

```sql
SELECT id, nombre, apellido1, apellido2, COUNT(id_proyecto)
FROM cientifico LEFT JOIN cientifico_proyecto
ON cientifico.id = cientifico_proyecto.ref_cientifico
GROUP BY id, nombre, apellido1, apellido2
```

3. Obtener el numero de científicos asignados a cada proyecto (mostrar el identificador
del proyecto y el nombre del proyecto).

```sql
SELECT id_proyecto, nombre, COUNT(id_proyecto)
FROM proyecto LEFT JOIN cientifico_proyecto
ON proyecto.id_proyecto = cientifico_proyecto.ref_proyecto
GROUP BY id_proyecto, nombre
```

4. Obtener el número de horas de dedicación de cada cientifico.

```sql
SELECT id, nombre, apellido1, apellido2, SUM(horas)
FROM cientifico C LEFT JOIN
(cientifico_proyecto A INNER JOIN proyecto P
ON A.ref_proyecto = P. id_proyecto)
ON C.id = A.ref_cientifico
GROUP BY id, nombre, apellido1, apellido2
```

5. Obtener el DNI y nombre de los científicos que se dedican a más de un proyecto y
cuya dedicación media a cada proyecto sea superior a las 80 horas.

```sql
/* Con dos subconsultas */
SELECT id, nombre, apellido1, apellido2
FROM cientifico C
WHERE 1 <
(
SELECT COUNT(*) FROM cientifico_proyecto
WHERE CiênfiifiC0 = C.id
)
AND
11 <
(
SELECT AVG(horas)
FROM proyecto INNER JOIN cientifico_proyecto
ON proyecto.id_proyecto = cientifico_proyecto.ref_proyecto
WHERE ref_cientifico = C.id
)
/* Juntando tablas y con HAVING */
SELECT id, nombre, apellido1, apellido2
FROM cientifico C, cientifico_proyecto A, proyecto P
WHERE C.id = A.ref_cientifico
AND P.id_proyecto = A.ref_proyecto
GROUP BY id, nombre, apellido1, apellido2
HAVING COUNT(id_proyecto) > 1 AND AVG(horas) > 11
```