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
5. Obtener el DNI y nombre de los científicos que se dedican a más de un proyecto y cuya dedicación media a cada proyecto sea superior __ a un número de horas superior a 10, por ejemplo 11 horas__.

Se debe de entregar un fichero _Nombre_Apellido1_Apellido2.sql_ con:
- Sentencias para la creación de la BBDD.
- Sentencias para la inserción de los elementos.
- Sentencias con cada una de las consultas solicitadas.