<div>

<div align="center">
<img src="https://autoescuelacamponuevo.com/wp-content/uploads/2013/04/acceso-alumnos-camponuevo-750x375.jpg" width="600px"/>
</div>

Dadas las siguiente tabla :

alumno:
 - expediente: entero
 - nombre: texto
 - localidad: texto
 - fecha_nacimiento: texto
 - direccion: texto
 - curso: entero
 - nivel: texto
 - faltas: entero
 > clave expediente(entero)

Sentencia de inserción de sql:
```sql
insert into alumnos values(123456,'Juan Miguel Soler Bakero','S/C de Tenerife','1995/10/10','Gran Vía, 2, 4A',1,'ESO',15);
insert into alumnos values(654321,'Laura Gómez Fernández','Las Palmas de Gran Canaria','1994/10/05','Junterones, 10, 5B',2,'ESO',25);
insert into alumnos values(765432,'Beatriz Martínez Hernández','S/C de Tenerife','1993/05/05','Plaza Mayor, 6, 3B',3,'ESO',5);
insert into alumnos values(987654,'Diego Marín Llorente','Puerto de S/C de Tenerife','1990/03/06','Diego de la Cierva, 5, 7A',1,'BACHILLER',34);

insert into alumnos values(445544,'Juan Francisco Cano Riquelme','S/C de Tenerife','1992/01/07','Plaza de Belluga, 3, 4A',4,'ESO',13);
insert into alumnos values(223322,'Raquel Riquelme Rubio','Las Palmas de Gran Canaria','1990/23/11','San Juan, 14, 3B',1,'BACHILLER',7);

insert into alumnos values(9988877,'Cristina Sánchez Bermejo','S/C de Tenerife','95/03/19','Torre de Romo, 7',1,'ESO',1);
insert into alumnos values(334455,'Pedro Jesús Rodríguez Soler','Puerto de S/C de Tenerife','94/10/03','Camino de Badel, 4',2,'ESO',11);
insert into alumnos values(334400,'Javier Ramínez Rodríguez','S/C de Tenerife','93/05/27','Gran Vía, 4, 3A',3,'ESO',0);
insert into alumnos values(993322,'Gema Rubio Colero','Las Palmas de Gran Canaria','92/09/09','Plaza Fuensanta, 5, 7A',1,'BACHILLER',19);
insert into alumnos values(554411,'Joaquín Herníndez Gonzilez','Las Palmas de Gran Canaria','91/12/12','Junterones, 4, 5A',2,'BACHILLER',14);
```

Se pide realizar:

Realiza las siguientes consultas:
1. Muestra todos los datos de todos los alumnos.
2. Muestra el nombre y fecha de nacimiento de todos los alumnos, ordenando alfabéticamente la localidad.
3. Consulta los datos de los alumnos que son de Las Palmas de Gran Canaria. 
4. Obtén los nombres, fecha de nacimiento y curso de los alumnos que son de S/C de Tenerife o Puerto de S/C de Tenerife.
5. Repite la consulta anterior ordenando por curso de forma descendente.
6. Obtén el expediente y el nombre de los alumnos que son de S/C de Tenerife y están en el primer curso de E.S.O.
7. ¿ Hay algún alumno  que sea de Las Palmas de Gran Canaria, esté en segundo de bachillerato y tenga más de 10 faltas? Demuéstralo obteniendo su expediente, nombre y dirección.
8. Ordena de mayor a menor número de faltas, los alumnos de primero de la ESO de la región de S/C de Tenerife.
9. Muestra el nombre y las faltas de los alumnos dividiendo las faltas entre dos.
10. Obtén los datos de todos los alumnos ordenados por nivel, y dentro de cada nivel por curso.
11. Muestra el nombre y expediente de todos aquellos alumnos que tengan menos de 10 faltas en tercer o cuarto curso y además sean de S/C de Tenerife.
12. Muestra los datos de aquellos alumnos cuyo nombre empiece por la letra 'J' y ordénalos según su expediente de forma ascendente.
13.  Muestra los datos de  los alumnos que son de Las Palmas de Gran Canaria y cuyo nombre termina con una letra 'z'.
14. Muestra los datos de aquellos alumnos que tienen entre 10 y 20 faltas. Ordena el resultado por curso ascendente, nivel ascendente número de faltas en orden descendente.
15. Muestra los datos de los alumnos cuya fecha de nacimiento comprenda los años 1993 y 1994. Ordena el resultado por curso de forma descendente.
16. Obtén los datos de aquellos alumnos que sean de tercer o cuarto curso y sean de Las Palmas de Gran Canaria. Utiliza el operador IN.
17. Muestra los datos de los alumnos que no sean de BACHILLER, ordenados por nombre descendentemente. Utiliza el operador IN.
18. Obtén los datos de los alumnos cuyo nombre empiece por la letra 'J', que tengan más de 10 faltas y no sean de Bachiller. Ordena el resultado por curso, y dentro de cada curso, por nombre.
19. Muestra los datos de los alumnos que tienen entre 10 y 20 faltas, son de S/C de Tenerife y están matriculados en 1o de E.S.O.
20. Muestra los datos de los alumnos cuya fecha de nacimiento comprenda los años 1993 y 1994. Ordena el resultado por nombre.

- Realizar captura de pantalla de cada una de las salidas.
- Fichero .sql con las consultas

</div>