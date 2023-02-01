<div>

<div align="center">
<img src="https://www.captio.net/hs-fs/hubfs/director-comercial.jpg?width=1460&name=director-comercial.jpg" width="600px"/>
</div>

Dadas las siguientes tablas :

Director:
 - dni: texto
 - nombre:texto
 - apellido: texto
  
  > clave foranera director_jefe -> dni texto
  clave foranera id_despacho: int
  clave primaria (dni)

Despacho:
 - id: intero
 - capacidad: intero
  
  > clave primaria (id)

Se pide:

Realizar las siguientes consultas:

1. Mostrar el DNI, nombre y apellidos de todos los directores.
2. Mostrar los datos de los directores que no tienen jefes,
3. Mostrar el nombre y apellidos de cada director, junto con la capacidad del despacho en el
que se encuentra.
4. Mostrar el número de directores que hay en cada despacho.
5. Mostrar los datos de los directores cuyos jefes no tienen jefes.
6. Mostrar los nombres y apellidos de los directores junto con los de su jefe.
7. Mostrar el número de despachos que están sobreutilizados.
8. Añadir un nuevo director llamado Paco Pérez, DNI 11111111T, sin jefe, y situado en el despacho 3,
9. Asignar a todos los empleados apellidados Pérez un nuevo jefe con DNI 00000000H.
10. Despedir a todos los directores, excepto a los que no tienen jefe.

> Requerimientos:
 - Inserta al menos 5 departamentos.
 - Inserta al menos 5 directores con jefe.
 - Inserta al menos 5 directores sin jefe.
 - Insertar valores teniendo en cuenta los datos que se solicitan en las consultas.

__Se pide__:crear cada una de las sentencias sql solicitadas (creación de tablas, inserción de datos, y consultas solicitas) siguiendo el siguiente patrón y almacenar en un _fichero de extensión_ ___.sql___ (Ej: _tarea_7_Nombre_Apellido1_Apellido.sql_).

```sql
-- sentencia sql de creación de la/s tabla/s de la bbdd


-- sentencia sql para la inserción de datos

-- Sentencia sql para cada una de las consultas especificadas.

--- 1. xxxxx

```

</div>