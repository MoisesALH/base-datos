Para la realizacoón del ejercicio debemos de crear la siguiente tabla:

- Usuario: 
    - id número,
    - login texto;
    - nombre texto;
    - sexo texto;
    - nivel numero,
    - email texto;
    - telefono texto;
    - marca texto;
    - compañia texto;
    - saldo número,
    - activo booleano
    > clave primaria(id)


> _Nota_. Para resolver un boolean en sqlite mira la documentación siguiente: https://www.sqlite.org/datatype3.html


```sql

INSERT INTO Usuario VALUES ('1','BRE2271','BRENDA','M','2','brenda@live.com','655-330-5736','KINKI','IUSACELL','100','1');
INSERT INTO Usuario  VALUES ('2','OSC4677','OSCAR','H','3','oscar@gmail.com','655-143-4181','LG4','TELCEL','0','1');
INSERT INTO Usuario  VALUES ('3','JOS7086','JOSE','H','3','francisco@gmail.com','655-143-3922','TOMTON','MOVISTAR','150','1')
INSERT INTO Usuario  VALUES ('4','LUI6115','LUIS','H','0','enrique@outlook.com','655-137-1279','KINKI','TELCEL','50','1');
INSERT INTO Usuario  VALUES ('5','LUI7072','LUIS','H','1','luis@hotmail.com','655-100-8260','TOMTON','IUSACELL','50','0');
INSERT INTO Usuario  VALUES ('6','DAN2832','DANIEL','H','0','daniel@outlook.com','655-145-2586','DREAMS','UNEFON','100','1'),
INSERT INTO Usuario  VALUES ('7','JAQ5351','JAQUELINE','M','0','jaqueline@outlook.com','655-330-5514','BLACK','AXEL','0','1');
INSERT INTO Usuario  VALUES ('8','ROM6520','ROMAN','H','2','roman@gmail.com','655-330-3263','LG4','IUSACELL','50','1');
INSERT INTO Usuario  VALUES ('9','BLA9739','BLAS','H','0','blas@hotmail.com','655-330-3871','LG4','UNEFON','100','1');
INSERT INTO Usuario  VALUES ('10','JES4752','JESSICA','M','1','jessica@hotmail.com','655-143-6861','KINKI','TELCEL','500','1');
INSERT INTO Usuario  VALUES ('11','DIA6570','DIANA','M','1','diana@live.com','655-143-3952','DREAMS','UNEFON','100','0');
INSERT INTO Usuario  VALUES ('12','RIC8283','RICARDO','H','2','ricardo@hotmail.com','655-145-6049','MOT','IUSACELL','150','1');
INSERT INTO Usuario  VALUES ('13','VAL6882','VALENTINA','M','0','valentina@live.com','655-137-4253','BLACK','AT&T','50','0');
INSERT INTO Usuario  VALUES ('14','BRE8106','BRENDA','M','3','brenda2@gmail.com','655-100-1351','MOT','NEXTEL','150','1');
INSERT INTO Usuario  VALUES ('15','LUC4982','LUCIA','M','3','lucia@gmail.com','655-145-4992','BLACK','IUSACELL','0','1');
INSERT INTO Usuario  VALUES ('16','JUA2337','JUAN','H','0','juan@outlook.com','655-100-6517','KINKI','AXEL','0','0');
INSERT INTO Usuario  VALUES ('17','ELP2984','ELPIDIO','H','1','elpidio@outlook.com','655-145-9938','MOT','MOVISTAR','500','1');
INSERT INTO Usuario  VALUES ('18','JES9640','JESSICA','M','3','jessica2@live.com','655-330-5143','DREAMS','IUSACELL','200','1');
INSERT INTO Usuario  VALUES ('19','LET4015','LETICIA','M','2','leticia@yahoo.com','655-143-4019','BLACK','UNEFON','100','1');
INSERT INTO Usuario  VALUES ('20','LUI1076','LUIS','H','3','luis2@live.com','655-100-5085','DREAMS','UNEFON','150','1');
INSERT INTO Usuario  VALUES ('21','HUG5441','HUGO','H','2','hugo@live.com','655-137-3935','MOT','AT&T','500','1');
```

> __Nota__. Si __existe alguna errata__ en los __insert__, se debe de solventar.

Consultas a realizar:

1. Listar los nombres de los usuarios
2. Calcular el saldo máximo de los usuarios de sexo “Mujer”
3. Listar nombre y teléfono de los usuarios con teléfono TOMTON, BLACK o DREAMS
4. Contar los usuarios sin saldo o inactivos
5. Listar el login de los usuarios con nivel 1, 2 o 3
6. Listar los números de teléfono con saldo menor o igual a 300
7. Calcular la suma de los saldos de los usuarios de la compañia telefónica NEXTEL
8. Contar el número de usuarios por compañía telefónica
9. Contar el número de usuarios por nivel
10. Listar el login de los usuarios con nivel 2
11. Mostrar el email de los usuarios que usan gmail
12. Listar nombre y teléfono de los usuarios con teléfono LG4, KINKI o MOT
13. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca LG4 o KINKI
14. Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL
15. Listar el login y teléfono de los usuarios con compañia telefónica que no sea TELCEL
16. Calcular el saldo promedio de los usuarios que tienen teléfono marca TOMTON
17. Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL o AXEL
18. Mostrar el email de los usuarios que no usan yahoo
19. Listar el login y teléfono de los usuarios con compañia telefónica que no sea TELCEL o IUSACELL
20. Listar el login y teléfono de los usuarios con compañia telefónica UNEFON
21. Listar las diferentes marcas de celular en orden alfabético descendentemente
22. Listar las diferentes compañias en orden alfabético aleatorio
23. Listar el login de los usuarios con nivel 0 o 2
24. Calcular el saldo promedio de los usuarios que tienen teléfono marca LG4
25. Listar el login de los usuarios con nivel 1 o 3
26. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca BLACK
27. Listar el login de los usuarios con nivel 3
28. Listar el login de los usuarios con nivel 0
29. Listar el login de los usuarios con nivel 1
31. Contar el número de usuarios por sexo
32. Listar el login y teléfono de los usuarios con compañia telefónica AT&T
33. Listar las diferentes compañias en orden alfabético descendentemente
34. Listar el logn de los usuarios inactivos
35. Listar los números de teléfono sin saldo
36. Calcular el saldo mínimo de los usuarios de sexo “Hombre”
37. Listar los números de teléfono con saldo mayor a 300.

Realizara:
Un fichero .sql que contenga:
 - La __creación de la tabla de BBDD__.
 - Los __insert en dicha tabla__.
 - Cada una de __las consultas__.


<details>
          <summary>SOLUCIÓN</summary>
        </br>

- Creación de la tabla:
	- Usuario: 
	    - id número,
	    - login texto;
	    - nombre texto;
	    - sexo texto;
	    - nivel numero,
	    - email texto;
	    - telefono texto;
	    - marca texto;
	    - compañia texto;
	    - saldo número,
	    - activo booleano
	    > clave primaria(id)

		```sql
			
		drop table if EXISTS usuario;
		create table usuario (
				id integer,
				login text,
				nombre text,
				sexo text,
				nivel integer,
				email text,
				telefono text,
				marca text,
				compañia text,
				saldo integer,
				activo integer,
				primary key(id)
			);
		```
- Corrección de las sentencias sql:
> Existen __insert__ que carecen del __;__, o tienen una __,__ en lugar __;__. Las líneas que presentan problemas son las siguientes:
```sql
INSERT INTO Usuario  VALUES ('3','JOS7086','JOSE','H','3','francisco@gmail.com','655-143-3922','TOMTON','MOVISTAR','150','1')
INSERT INTO Usuario  VALUES ('6','DAN2832','DANIEL','H','0','daniel@outlook.com','655-145-2586','DREAMS','UNEFON','100','1'),
```

Esto producirá que cuando __se corrija__ y se realice nuevamente el insert, se debe realizar inicialmente la siguiente sentencia:

```sql
	delete from usuario;
``` 

que realizará la __eliminación de los registros insertados previamente__, de la tabla __usuario__ de base de datos.


```sql
	

INSERT INTO Usuario VALUES ('1','BRE2271','BRENDA','M','2','brenda@live.com','655-330-5736','KINKI','IUSACELL','100','1');
INSERT INTO Usuario  VALUES ('2','OSC4677','OSCAR','H','3','oscar@gmail.com','655-143-4181','LG4','TELCEL','0','1');
INSERT INTO Usuario  VALUES ('3','JOS7086','JOSE','H','3','francisco@gmail.com','655-143-3922','TOMTON','MOVISTAR','150','1');
INSERT INTO Usuario  VALUES ('4','LUI6115','LUIS','H','0','enrique@outlook.com','655-137-1279','KINKI','TELCEL','50','1');
INSERT INTO Usuario  VALUES ('5','LUI7072','LUIS','H','1','luis@hotmail.com','655-100-8260','TOMTON','IUSACELL','50','0');
INSERT INTO Usuario  VALUES ('6','DAN2832','DANIEL','H','0','daniel@outlook.com','655-145-2586','DREAMS','UNEFON','100','1');
INSERT INTO Usuario  VALUES ('7','JAQ5351','JAQUELINE','M','0','jaqueline@outlook.com','655-330-5514','BLACK','AXEL','0','1');
INSERT INTO Usuario  VALUES ('8','ROM6520','ROMAN','H','2','roman@gmail.com','655-330-3263','LG4','IUSACELL','50','1');
INSERT INTO Usuario  VALUES ('9','BLA9739','BLAS','H','0','blas@hotmail.com','655-330-3871','LG4','UNEFON','100','1');
INSERT INTO Usuario  VALUES ('10','JES4752','JESSICA','M','1','jessica@hotmail.com','655-143-6861','KINKI','TELCEL','500','1');
INSERT INTO Usuario  VALUES ('11','DIA6570','DIANA','M','1','diana@live.com','655-143-3952','DREAMS','UNEFON','100','0');
INSERT INTO Usuario  VALUES ('12','RIC8283','RICARDO','H','2','ricardo@hotmail.com','655-145-6049','MOT','IUSACELL','150','1');
INSERT INTO Usuario  VALUES ('13','VAL6882','VALENTINA','M','0','valentina@live.com','655-137-4253','BLACK','AT&T','50','0');
INSERT INTO Usuario  VALUES ('14','BRE8106','BRENDA','M','3','brenda2@gmail.com','655-100-1351','MOT','NEXTEL','150','1');
INSERT INTO Usuario  VALUES ('15','LUC4982','LUCIA','M','3','lucia@gmail.com','655-145-4992','BLACK','IUSACELL','0','1');
INSERT INTO Usuario  VALUES ('16','JUA2337','JUAN','H','0','juan@outlook.com','655-100-6517','KINKI','AXEL','0','0');
INSERT INTO Usuario  VALUES ('17','ELP2984','ELPIDIO','H','1','elpidio@outlook.com','655-145-9938','MOT','MOVISTAR','500','1');
INSERT INTO Usuario  VALUES ('18','JES9640','JESSICA','M','3','jessica2@live.com','655-330-5143','DREAMS','IUSACELL','200','1');
INSERT INTO Usuario  VALUES ('19','LET4015','LETICIA','M','2','leticia@yahoo.com','655-143-4019','BLACK','UNEFON','100','1');
INSERT INTO Usuario  VALUES ('20','LUI1076','LUIS','H','3','luis2@live.com','655-100-5085','DREAMS','UNEFON','150','1');
INSERT INTO Usuario  VALUES ('21','HUG5441','HUGO','H','2','hugo@live.com','655-137-3935','MOT','AT&T','500','1');
``` 


1. Listar los nombres de los usuarios

```sql
SELECT nombre FROM Usuario;
```

2. Calcular el saldo máximo de los usuarios de sexo "Mujer"

```sql
SELECT MAX(saldo) FROM Usuario WHERE sexo = 'M';
```

3. Listar nombre y teléfono de los usuarios con teléfono TOMTON, BLACK o DREAMS

```sql
SELECT nombre, telefono FROM Usuario WHERE marca IN('TOMTON', 'BLACK', 'DREAMS');
```

4. Contar los usuarios sin saldo o inactivos

```sql
SELECT COUNT(*) FROM Usuario WHERE NOT activo OR saldo <= 0;
```

5. Listar el login de los usuarios con nivel 1, 2 o 3

```sql
SELECT usuario FROM Usuario WHERE nivel IN(1, 2, 3);
```

6. Listar los números de teléfono con saldo menor o igual a 300

```sql
SELECT telefono FROM Usuario WHERE saldo <= 300;
```

7. Calcular la suma de los saldos de los usuarios de la compañia telefónica NEXTEL

```sql
SELECT SUM(saldo) FROM Usuario WHERE compañia = 'NEXTEL';
```

8. Contar el número de usuarios por compañía telefónica

```sql
SELECT compañia, COUNT(*) FROM Usuario GROUP BY compañia;
```
9. Contar el número de usuarios por nivel

```sql
SELECT nivel, COUNT(*) FROM Usuario GROUP BY nivel;
```

10. Listar el login de los usuarios con nivel 2

```sql
SELECT usuario FROM Usuario WHERE nivel = 2;
```

11. Mostrar el email de los usuarios que usan gmail

```sql
SELECT email FROM Usuario WHERE email LIKE '%gmail.com';
```
12. Listar nombre y teléfono de los usuarios con teléfono LG4, KINKI o MOT

```sql
SELECT nombre, telefono FROM Usuario WHERE marca IN('LG4', 'KINKI', 'MOT');
```

13. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca LG4 o KINKI

```sql
SELECT nombre, telefono FROM Usuario WHERE marca NOT IN('LG4', 'KINKI');
```
14. Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL

```sql
SELECT usuario, telefono FROM Usuario WHERE compañia = 'IUSACELL';
```

15. Listar el login y teléfono de los usuarios con compañia telefónica que no sea TELCEL

```sql
SELECT usuario, telefono FROM Usuario WHERE compañia <> "TELCEL";
```

16. Calcular el saldo promedio de los usuarios que tienen teléfono marca TOMTON

```sql
SELECT AVG(saldo) FROM Usuario WHERE marca = 'TOMTON';
```

17. Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL o AXEL

```sql
SELECT usuario, telefono FROM Usuario WHERE compañia IN('IUSACELL', 'AXEL');
```

18. Mostrar el email de los usuarios que no usan yahoo

```sql
SELECT email FROM Usuario WHERE email NOT LIKE '%yahoo.com';
```

20. Listar el login y teléfono de los usuarios con compañia telefónica que no sea TELCEL o IUSACELL

```sql
SELECT usuario, telefono FROM Usuario WHERE compañia NOT IN('TELCEL', 'IUSACELL');
```
21. Listar el login y teléfono de los usuarios con compañia telefónica UNEFON

```sql
SELECT usuario, telefono FROM Usuario WHERE compañia = 'UNEFON';
```

22. Listar las diferentes marcas de celular en orden alfabético descendentemente

```sql
SELECT DISTINCT marca FROM Usuario ORDER BY marca DESC;
```

23. Listar las diferentes compañias en orden alfabético aleatorio

```sql
SELECT DISTINCT compañia FROM Usuario ORDER BY RAND();
```
24. Listar el login de los usuarios con nivel 0 o 2

```sql
SELECT usuario FROM Usuario WHERE nivel IN(0, 2);
```
25. Calcular el saldo promedio de los usuarios que tienen teléfono marca LG4

```sql
SELECT AVG(saldo) FROM Usuario WHERE marca = 'LG4';
```

26. Listar el login de los usuarios con nivel 1 o 3

```sql
SELECT usuario FROM Usuario WHERE nivel IN(1, 3);
```

27. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca BLACK 

```sql
SELECT nombre, telefono FROM Usuario WHERE marca <> "BLACK";
```

28. Listar el login de los usuarios con nivel 3

```sql
SELECT usuario FROM Usuario WHERE nivel = 3;
```

29. Listar el login de los usuarios con nivel 0

```sql
SELECT usuario FROM Usuario WHERE nivel = 0;
```

30. Listar el login de los usuarios con nivel 1

```sql
SELECT usuario FROM Usuario WHERE nivel = 1;
```

31. Contar el número de usuarios por sexo

```sql
SELECT sexo, COUNT(*) FROM Usuario GROUP BY sexo;
```
32. Listar el login y teléfono de los usuarios con compañia telefónica AT&T

```sql
SELECT usuario, telefono FROM Usuario WHERE compañia = "AT&T";
```

33. Listar las diferentes compañias en orden alfabético descendentemente

```sql
SELECT DISTINCT compañia FROM Usuario ORDER BY compañia DESC;
```
34. Listar el login de los usuarios inactivos

```sql
SELECT usuario FROM Usuario WHERE NOT activo;
```

35. Listar los números de teléfono sin saldo

```sql
SELECT telefono FROM Usuario WHERE saldo <= 0;
```
36. Calcular el saldo mínimo de los usuarios de sexo "Hombre"

```sql
SELECT MIN(saldo) FROM Usuario WHERE sexo = 'H';
```
37. Listar los números de teléfono con saldo mayor a 300

```sql
SELECT telefono FROM Usuario WHERE saldo > 300;
```

</details>