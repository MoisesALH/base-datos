<div align="justify">

<div align="center">
<img src="https://statics.forbesargentina.com/2022/09/crop/63233a72b7071__822x460.webp" width="500px"/>
</div>


Se plantea la creación de una BBDD para una empresa de tecnología. Las necesidades se describen en la siguiente guía de tablas de la BBDD.

- tabla fabricante:
  - id_fab:entero;
  - nombre:texto;
  - pais:texto;
  > clave primaria(id_fab);
- tabla programa:
  - codigo:entero,
  - nombre:texto;
  - version:texto;
  > clave primaria(codigo);
- tabla comercio:
  - cif:entero,
  - nombre:texto,
  - ciudad:texto);
  > clave primaria(cif);
- tabla cliente:
  - dni:entero,
  - nombre:texto,
  - edad:entero;
  > clave primaria(dni);
- tabla desarrolla:
  - id_fab entero:
  - codigo entero:
  > clave primaria(id_fab,codigo);
- tabla distribuye:
  - cif entero:
  - codigo entero:
  - cantidad entero,
  > clave primaria(cif,codigo);
- tabla registra:
  - cif entero:
  - dni entero:
  - codigo entero:
  - medio texto:
  > clave primaria(cif,dni);

- Realiza la creación de la BBDD, creando las sentencias __sql__ necesarias.  
- Realiza la inserción de los siguientes valores:

  ```  
  insert into fabricante values(1,'Oracle','Estados Unidos');
  insert into fabricante values(2,'Microsoft','Estados Unidos');
  insert into fabricante values(3,'IBM','Estados Unidos');
  insert into fabricante values(4,'Dinamic','España');
  insert into fabricante values(5,'Borland','Estados Unidos');
  insert into fabricante values(6,'Symantec','Estados Unidos');

  insert into programa values(1,'Application Server','9i');
  insert into programa values(2,'Database','8i');
  insert into programa values(3,'Database','9i');
  insert into programa values(4,'Database','10g');
  insert into programa values(5,'Developer','6i');
  insert into programa values(6,'Access','97');
  insert into programa values(7,'Access','2000');
  insert into programa values(8,'Access','XP');
  insert into programa values(9,'Windows','98');
  insert into programa values(10,'Windows','XP Professional');
  insert into programa values(11,'Windows','XP Home Edition');
  insert into programa values(12,'Windows','2003 Server');
  insert into programa values(13,'Norton Internet Security','2004');
  insert into programa values(14,'Freddy Hardest',NULL);
  insert into programa values(15,'Paradox','2');
  insert into programa values(16,'C++ Builder','5.5');
  insert into programa values(17,'DB/2','2.0');
  insert into programa values(18,'OS/2','1.0');
  insert into programa values(19,'JBuilder','X');
  insert into programa values(20,'La prisión','1.0');

  insert into comercio values(1,'El Corte Inglés','Sevilla');
  insert into comercio values(2,'El Corte Inglés','Madrid');
  insert into comercio values(3,'Jump','Valencia');
  insert into comercio values(4,'Centro Mail','Sevilla');
  insert into comercio values(5,'FNAC','Barcelona');

  insert into cliente values(1,'Pepe Pérez',45);
  insert into cliente values(2,'Juan González',45);
  insert into cliente values(3,'María Gómez',33);
  insert into cliente values(4,'Javier Casado',18);
  insert into cliente values(5,'Nuria Sánchez',29);
  insert into cliente values(6,'Antonio Navarro',58);

  insert into desarrolla values(1,1);
  insert into desarrolla values(1,2);
  insert into desarrolla values(1,3);
  insert into desarrolla values(1,4);
  insert into desarrolla values(1,5);
  insert into desarrolla values(2,6);
  insert into desarrolla values(2,7);
  insert into desarrolla values(2,8);
  insert into desarrolla values(2,9);
  insert into desarrolla values(2,10);
  insert into desarrolla values(2,11);
  insert into desarrolla values(2,12);
  insert into desarrolla values(6,13);
  insert into desarrolla values(4,14);
  insert into desarrolla values(5,15);
  insert into desarrolla values(5,16);
  insert into desarrolla values(3,17);
  insert into desarrolla values(3,18);
  insert into desarrolla values(5,19);
  insert into desarrolla values(4,20);

  insert into distribuye values(1,1,10);
  insert into distribuye values(1,2,11);
  insert into distribuye values(1,6,5);
  insert into distribuye values(1,7,3);
  insert into distribuye values(1,10,5);
  insert into distribuye values(1,13,7);
  insert into distribuye values(2,1,6);
  insert into distribuye values(2,2,6);
  insert into distribuye values(2,6,4);
  insert into distribuye values(2,7,7);
  insert into distribuye values(3,10,8);
  insert into distribuye values(3,13,5);
  insert into distribuye values(4,14,3);
  insert into distribuye values(4,20,6);
  insert into distribuye values(5,15,8);
  insert into distribuye values(5,16,2);
  insert into distribuye values(5,17,3);
  insert into distribuye values(5,19,6);
  insert into distribuye values(5,8,8);

  insert into registra values(1,1,1,'Internet');
  insert into registra values(1,3,4,'Tarjeta postal');
  insert into registra values(4,2,10,'Teléfono');
  insert into registra values(4,1,10,'Tarjeta postal');
  insert into registra values(5,2,12,'Internet');
  insert into registra values(2,4,15,'Internet');
  ```

___Apollate en las funciones del lenguaje sql y sqlite__:
- [Funciones de core](https://www.sqlite.org/lang_corefunc.html). 
- [Funciones de fechas](https://www.sqlite.org/lang_datefunc.html).

- Realiza las siguientes consultas:
  
  1. Averigua el DNI de todos los clientes. 
  2. Consulta todos los datos de todos los programas. 
  3. Obtén un listado con los nombres de todos los programas.
  4. Genera una lista con todos los comercios. 
  5. Genera una lista de las ciudades con establecimientos donde se venden programas, sin que aparezcan valores duplicados (utiliza DISTINCT). 
  6. Obtén una lista con los nombres de programas, sin que aparezcan valores duplicados (utiliza DISTINCT). 
  7. Obtén el DNI más 4 de todos los clientes.
  8. Haz un listado con los códigos de los programas multiplicados por 7.
  9. ¿Cuáles son los programas cuyo código es inferior o igual a 10?     
  10. ¿Cuál es el programa cuyo código es 11?
  11. ¿Qué fabricantes son de Estados Unidos?
  12. ¿Cuáles son los fabricantes no españoles? Utilizar el operador IN.      
  13. Obtén un listado con los códigos de las distintas versiones de Windows.       
  14. ¿En qué ciudades comercializa programas El Corte Inglés?
  15. ¿Qué otros comercios hay, además de El Corte Inglés? Utilizar el operador IN.
  16. Genera una lista con los códigos de las distintas versiones de Windows y Access. Utilizar el operador IN.
  17. Obtén un listado que incluya los nombres de los clientes de edades comprendidas entre 10 y 25 y de los mayores de 50 años. Da una solución con BETWEEN y otra sin BETWEEN.
  18. Saca un listado con los comercios de Sevilla y Madrid. No se admiten valores duplicados.
  19. ¿Qué clientes terminan su nombre en la letra “o”?
  20. ¿Qué clientes terminan su nombre en la letra “o” y, además, son mayores de 30 años?
  21. Obtén un listado en el que aparezcan los programas cuya versión finalice por una letra i, o cuyo nombre comience por una A o por una W.
  22. Obtén un listado en el que aparezcan los programas cuya versión finalice por una letra i, o cuyo nombre comience por una A y termine por una S.
  23. Obtén un listado en el que aparezcan los programas cuya versión finalice por una letra i, y cuyo nombre no comience por una A.
  24. Obtén una lista de empresas por orden alfabético ascendente.
  25. Genera un listado de empresas por orden alfabético descendente.
  26. Obtén un listado de programas por orden de versión.
  27. Genera un listado de los programas que desarrolla Oracle.
  28. ¿Qué comercios distribuyen Windows?
  29. Genera un listado de los programas y cantidades que se han distribuido a El Corte Inglés de Madrid.
  30. ¿Qué fabricante ha desarrollado Freddy Hardest?
  31. Selecciona el nombre de los programas que se registran por Internet.
  32. ¿Qué medios ha utilizado para registrarse Pepe Pérez?
  33. ¿Qué usuarios han optado por Internet como medio de registro?
  34. ¿Qué programas han recibido registros por tarjeta postal?
  35. ¿En qué localidades se han vendido productos que se han registrado por Internet?
  36. Obtén un listado de los nombres de las personas que se han registrado por Internet, junto al nombre de los programas para los que ha efectuado el registro.
  37. Genera un listado en el que aparezca cada cliente junto al programa que ha registrado, el medio con el que lo ha hecho y el comercio en el que lo ha adquirido.
  38. Genera un listado con las ciudades en las que se pueden obtener los productos de Oracle.
  39. Obtén el nombre de los usuarios que han registrado Access XP.
  40. Nombre de aquellos fabricantes cuyo país es el mismo que ʻOracleʼ. (Subconsulta).
  41. Nombre de aquellos clientes que tienen la misma edad que Pepe Pérez. (Subconsulta).
  42. Genera un listado con los comercios que tienen su sede en la misma ciudad que tiene el comercio ʻFNACʼ. (Subconsulta).
  43. Nombre de aquellos clientes que han registrado un producto de la misma forma que el cliente ʻPepe Pérezʼ. (Subconsulta).
  44. Obtener el número de programas que hay en la tabla programas. 46 Calcula el número de clientes cuya edad es mayor de 40 años.
  45. Calcula el número de productos que ha vendido el establecimiento cuyo CIF es 1.
  46. Calcula la media de programas que se venden cuyo código es 7.
  47. Calcula la mínima cantidad de programas de código 7 que se ha vendido.
  48. Calcula la máxima cantidad de programas de código 7 que se ha vendido.
  49. ¿En cuántos establecimientos se vende el programa cuyo código es 7?
  50. Calcular el número de registros que se han realizado por Internet.
  51. Obtener el número total de programas que se han vendido en ʻSevillaʼ.
  52. Calcular el número total de programas que han desarrollado los fabricantes cuyo país es ʻEstados Unidosʼ.
  53. Visualiza el nombre de todos los clientes en mayúscula. En el resultado de la consulta debe aparecer también la longitud de la cadena nombre.
  54. Con una consulta concatena los campos nombre y versión de la tabla PROGRAMA.   
       
__Se debe de realizar:__
 - La __creación de cada una de las tablas__ e indicar la __sentencia sql__ utilizada, además de la salida obtenida.
    - tabla fabricante:
      - id_fab:entero;
      - nombre:texto;
      - pais:texto;
      > clave primaria(id_fab);  
        <details>
          <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        create table fabricante(
            id_fab integer not null,
            nombre text,
            pais text,
            primary key(id_fab)
        );
        ```
      </details>
    - tabla programa:
      - codigo:entero,
      - nombre:texto;
      - version:texto;
      > clave primaria(codigo);

        <details>
          <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        create table programa(
            codigo integer,
            nombre text,
            version text,
            primary key(codigo)
        );
        ```
      </details>

    - tabla comercio:
      - cif:entero,
      - nombre:texto,
      - ciudad:texto);
      > clave primaria(cif);
        <details>
          <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        create table comercio(
            cif integer,
            nombre text,
            ciudad text,
            primary key(cif)
        );
        ```
      </details>
    - tabla cliente:
      - dni:entero,
      - nombre:texto,
      - edad:entero;
      > clave primaria(dni);

        <details>
          <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        create table cliente(
            dni integer,
            nombre text,
            edad integer,
            primary key(dni)
        );
        ```
      </details>

    - tabla desarrolla:
      - id_fab entero:
      - codigo entero:
      > clave primaria(id_fab,codigo);

        <details>
          <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        create table desarrolla(
            id_fab integer,
            codigo integer,
            primary key(id_fab,codigo)
        );
        ```
      </details>

    - tabla distribuye:
      - cif entero:
      - codigo entero:
      - cantidad entero,
      > clave primaria(cif,codigo);

        <details>
          <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        create table distribuye(
            cif integer,
            codigo integer,
            cantidad integer,
            primary key(cif,codigo)
        );
        ```
      </details>

    - tabla registra:
      - cif entero:
      - dni entero:
      - codigo entero:
      - medio texto:
      > clave primaria(cif,dni);

        <details>
          <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        create table registra(
            cif integer,
            dni integer,
            codigo integer,
            cantidad integer,
            primary key(cif,dni)
        );
        ```
      </details>

- Realizar la __inserción de los datos__.
  	<details>
      <summary>SOLUCIÓN</summary>
	  </br>
	  
    ```sql
        insert into fabricante values(1,'Oracle','Estados Unidos');
        insert into fabricante values(2,'Microsoft','Estados Unidos');
        insert into fabricante values(3,'IBM','Estados Unidos');
        insert into fabricante values(4,'Dinamic','España');
        insert into fabricante values(5,'Borland','Estados Unidos');
        insert into fabricante values(6,'Symantec','Estados Unidos');

        insert into programa values(1,'Application Server','9i');
        insert into programa values(2,'Database','8i');
        insert into programa values(3,'Database','9i');
        insert into programa values(4,'Database','10g');
        insert into programa values(5,'Developer','6i');
        insert into programa values(6,'Access','97');
        insert into programa values(7,'Access','2000');
        insert into programa values(8,'Access','XP');
        insert into programa values(9,'Windows','98');
        insert into programa values(10,'Windows','XP Professional');
        insert into programa values(11,'Windows','XP Home Edition');
        insert into programa values(12,'Windows','2003 Server');
        insert into programa values(13,'Norton Internet Security','2004');
        insert into programa values(14,'Freddy Hardest',NULL);
        insert into programa values(15,'Paradox','2');
        insert into programa values(16,'C++ Builder','5.5');
        insert into programa values(17,'DB/2','2.0');
        insert into programa values(18,'OS/2','1.0');
        insert into programa values(19,'JBuilder','X');
        insert into programa values(20,'La prisión','1.0');

        insert into comercio values(1,'El Corte Inglés','Sevilla');
        insert into comercio values(2,'El Corte Inglés','Madrid');
        insert into comercio values(3,'Jump','Valencia');
        insert into comercio values(4,'Centro Mail','Sevilla');
        insert into comercio values(5,'FNAC','Barcelona');

        insert into cliente values(1,'Pepe Pérez',45);
        insert into cliente values(2,'Juan González',45);
        insert into cliente values(3,'María Gómez',33);
        insert into cliente values(4,'Javier Casado',18);
        insert into cliente values(5,'Nuria Sánchez',29);
        insert into cliente values(6,'Antonio Navarro',58);

        insert into desarrolla values(1,1);
        insert into desarrolla values(1,2);
        insert into desarrolla values(1,3);
        insert into desarrolla values(1,4);
        insert into desarrolla values(1,5);
        insert into desarrolla values(2,6);
        insert into desarrolla values(2,7);
        insert into desarrolla values(2,8);
        insert into desarrolla values(2,9);
        insert into desarrolla values(2,10);
        insert into desarrolla values(2,11);
        insert into desarrolla values(2,12);
        insert into desarrolla values(6,13);
        insert into desarrolla values(4,14);
        insert into desarrolla values(5,15);
        insert into desarrolla values(5,16);
        insert into desarrolla values(3,17);
        insert into desarrolla values(3,18);
        insert into desarrolla values(5,19);
        insert into desarrolla values(4,20);

        insert into distribuye values(1,1,10);
        insert into distribuye values(1,2,11);
        insert into distribuye values(1,6,5);
        insert into distribuye values(1,7,3);
        insert into distribuye values(1,10,5);
        insert into distribuye values(1,13,7);
        insert into distribuye values(2,1,6);
        insert into distribuye values(2,2,6);
        insert into distribuye values(2,6,4);
        insert into distribuye values(2,7,7);
        insert into distribuye values(3,10,8);
        insert into distribuye values(3,13,5);
        insert into distribuye values(4,14,3);
        insert into distribuye values(4,20,6);
        insert into distribuye values(5,15,8);
        insert into distribuye values(5,16,2);
        insert into distribuye values(5,17,3);
        insert into distribuye values(5,19,6);
        insert into distribuye values(5,8,8);

        insert into registra values(1,1,1,'Internet');
        insert into registra values(1,3,4,'Tarjeta postal');
        insert into registra values(4,2,10,'Teléfono');
        insert into registra values(4,1,10,'Tarjeta postal');
        insert into registra values(5,2,12,'Internet');
        insert into registra values(2,4,15,'Internet');
	  ```
	</details>

- Realizar cada una de las consultas propuestas, indicando la __sentencia sql__, y la __salida obtenida__.  
  1. Averigua el DNI de todos los clientes.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select dni from cliente; 
        ```

      </details> 
  2. Consulta todos los datos de todos los programas. 
        <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select * from programa;
        ```

      </details>
  3. Obtén un listado con los nombres de todos los programas.
        <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select nombre from programa;
        ```

      </details>
  4. Genera una lista con todos los comercios.
        <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select nombre from comercio;
        ```

      </details> 
  5. Genera una lista de las ciudades con establecimientos donde se venden programas, sin que aparezcan valores duplicados (utiliza DISTINCT). 
        <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select DISTINCT ciudad from comercio;
        ```

      </details>
  6. Obtén una lista con los nombres de programas, sin que aparezcan valores duplicados (utiliza DISTINCT).
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select DISTINCT nombre from programa;
        ```

      </details> 
  7. Obtén el DNI más 4 de todos los clientes.
        <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select dni+4 from cliente;
        ```

      </details> 
  8. Haz un listado con los códigos de los programas multiplicados por 7.
          <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select codigo*7 from programa;
        ```
      
      </details>
  9. ¿Cuáles son los programas cuyo código es inferior o igual a 10? 
        <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select codigo from programa WHERE codigo  <= 10;
        ```

      </details>
  10. ¿Cuál es el programa cuyo código es 11?
        <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select * from programa WHERE codigo  = 11;
        ```

      </details>
  11. ¿Qué fabricantes son de Estados Unidos?
        <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select * from fabricante where pais ='Estados Unidos';
        ```

      </details> 
  12. ¿Cuáles son los fabricantes no españoles? Utilizar el operador IN.
        <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select * from fabricante where pais not in ('España');
        ```

      </details> 
  13. Obtén un listado con los códigos de las distintas versiones de Windows.
        <details>
            <summary>SOLUCIÓN</summary>
            </br>
            
            ```sql
            select * from programa where nombre='Windows';
            ```

      </details> 
  14. ¿En qué ciudades comercializa programas El Corte Inglés?
        <details>
        <summary>SOLUCIÓN</summary>
        </br>
          
          ```sql
          SELECT * from comercio where nombre ='El Corte Inglés';
          ```

      </details> 
  15. ¿Qué otros comercios hay, además de El Corte Inglés? Utilizar el operador IN.
        <details>
          <summary>SOLUCIÓN</summary>
          </br>
          
          ```sql
          SELECT * from comercio where nombre not in ('El Corte Inglés');
          ```

        </details> 
         
  16. Genera una lista con los códigos de las distintas versiones de Windows y Access. Utilizar el operador IN.
        <details>
          <summary>SOLUCIÓN</summary>
          </br>
          
          ```sql
          select DISTINCT codigo FROM programa where nombre in ('Windows', 'Access');
          ```

        </details>  

  17. Obtén un listado que incluya los nombres de los clientes de edades comprendidas entre 10 y 25 y de los mayores de 50 años. Da una solución con BETWEEN y otra sin BETWEEN.
        <details>
          <summary>SOLUCIÓN</summary>
          </br>
        
          ```sql
          select nombre from cliente where ((edad >10 and edad<=25) or edad >= 50)

          select nombre from cliente where  ( (edad BETWEEN 10 and 25) or edad >= 50);
          ```

        </details> 

  18. Saca un listado con los comercios de Sevilla y Madrid. No se admiten valores duplicados.
        <details>
          <summary>SOLUCIÓN</summary>
          </br>
          
          ```sql
          select DISTINCT nombre from comercio where ciudad in ('Sevilla', 'Madrid');
          ```

        </details> 
  19. ¿Qué clientes terminan su nombre en la letra “o”?
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select nombre from cliente where nombre like '%o %'
        ```
      
      </details> 
  20. ¿Qué clientes terminan su nombre en la letra “o” y, además, son mayores de 30 años?
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select nombre from cliente where nombre like '%o %' and edad >=30;
        ```

      </details> 
  21. Obtén un listado en el que aparezcan los programas cuya versión finalice por una letra i, o cuyo nombre comience por una A o por una W.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select nombre,version from programa where version REGEXP 'i$' or nombre REGEXP '^A|^W';

        //version like
        select nombre,version from programa where version like '%i' or nombre like 'A%' or nombre like 'W%';
        ```

      </details> 
  22. Obtén un listado en el que aparezcan los programas cuya versión finalice por una letra i, o cuyo nombre comience por una A y termine por una S.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select nombre,version from programa where version REGEXP 'i$' or nombre REGEXP '^A.*S$';
        ```

      </details> 
  23. Obtén un listado en el que aparezcan los programas cuya versión finalice por una letra i, y cuyo nombre no comience por una A.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
         select nombre,version from programa where version REGEXP 'i$' and nombre not REGEXP '^A';
        ```

      </details> 
  24. Obtén una lista de empresas por orden alfabético ascendente.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select nombre from comercio order by nombre asc;
        ```

      </details> 
  25. Genera un listado de empresas por orden alfabético descendente.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select nombre from comercio order by nombre desc;
        ```

      </details> 
  26. Obtén un listado de programas por orden de versión.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select nombre from programa order by version asc;
        ```

      </details> 
  27. Genera un listado de los programas que desarrolla Oracle.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT programa.* FROM fabricante, desarrolla, programa
        WHERE fabricante.id_fab=desarrolla.id_fab AND desarrolla.codigo=programa.codigo AND fabricante.nombre='Oracle';
        ```

      </details> 
  28. ¿Qué comercios distribuyen Windows?
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT comercio.nombre FROM comercio, distribuye, programa WHERE comercio.cif = distribuye.cif AND distribuye.codigo = programa.codigo AND programa.nombre = "Windows" ;
        ```

      </details> 
  29. Genera un listado de los programas y cantidades que se han distribuido a El Corte Inglés de Madrid.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT programa.nombre,distribuye.cantidad FROM comercio, distribuye, programa WHERE comercio.cif = distribuye.cif AND distribuye.codigo = programa.codigo AND comercio.nombre='El Corte Inglés' ;
        ```

      </details> 
  30. ¿Qué fabricante ha desarrollado Freddy Hardest?
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT fabricante.nombre FROM fabricante,desarrolla,programa WHERE fabricante.id_fab = desarrolla.id_fab AND desarrolla.codigo = programa.codigo AND programa.nombre='Freddy Hardest';
        ```

      </details>  
  31. Selecciona el nombre de los programas que se registran por Internet.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT DISTINCT programa.nombre FROM programa, registra WHERE programa.codigo = registra.codigo AND medio = 'Internet' ;
        ```

      </details> 
  32. ¿Qué medios ha utilizado para registrarse Pepe Pérez?
      <details>
        <summary>SOLUCIÓN</summary>
        </br>

        ```sql
        SELECT medio FROM registra, cliente WHERE registra.dni = cliente.dni AND nombre = 'Pepe Pérez';
        ```

      </details>  
  33. ¿Qué usuarios han optado por Internet como medio de registro?
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT cliente.nombre FROM cliente, registra WHERE cliente.dni = registra.dni AND medio = 'Internet';
        ```

      </details> 
  34. ¿Qué programas han recibido registros por tarjeta postal?
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT programa.nombre FROM programa, registra WHERE programa.codigo = registra.codigo AND medio = 'tarjeta postal' ;
        ```

      </details> 
  35. ¿En qué localidades se han vendido productos que se han registrado por Internet?
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT comercio.ciudad FROM comercio, distribuye, programa, registra WHERE comercio.cif = distribuye.cif AND distribuye.codigo = programa.codigo AND programa.codigo =registra.codigo AND registra.medio = 'Internet' ;
        ```

      </details> 
  36. Obtén un listado de los nombres de las personas que se han registrado por Internet, junto al nombre de los programas para los que ha efectuado el registro.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT cliente.nombre, programa.nombre FROM cliente, registra, programa WHERE cliente.dni = registra.dni AND registra.codigo = programa.codigo AND registra.medio = 'Internet'  ;
        ```

      </details> 
  37. Genera un listado en el que aparezca cada cliente junto al programa que ha registrado, el medio con el que lo ha hecho y el comercio en el que lo ha adquirido.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT cliente.nombre, programa.nombre, programa.version, registra.medio, comercio.nombre, comercio.ciudad FROM cliente, registra, programa, distribuye, comercio WHERE cliente.dni = registra.dni AND registra.codigo = programa.codigo AND programa.codigo = distribuye.codigo AND distribuye.cif = comercio.cif ;
        ```

      </details> 
  38. Genera un listado con las ciudades en las que se pueden obtener los productos de Oracle.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT DISTINCT comercio.ciudad FROM comercio, distribuye, programa, desarrolla, fabricante WHERE comercio.cif=distribuye.cif AND distribuye.codigo = programa.codigo AND programa.codigo = desarrolla.codigo AND desarrolla.id_fab = fabricante.id_fab AND fabricante.nombre = 'Oracle';
        ```

      </details> 
  39. Obtén el nombre de los usuarios que han registrado Access XP.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT cliente.nombre FROM cliente, registra, programa WHERE cliente.dni = registra.dni AND registra.codigo = programa.codigo AND programa.nombre = 'Access' AND programa.version like  'XP%';
        ```

      </details> 
  40. Nombre de aquellos fabricantes cuyo país es el mismo que ʻOracleʼ. (Subconsulta).
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT nombre FROM fabricante WHERE pais = (SELECT pais FROM fabricante WHERE nombre = 'Oracle') ;
        ```

      </details>  
  41. Nombre de aquellos clientes que tienen la misma edad que Pepe Pérez. (Subconsulta).
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT nombre FROM cliente WHERE edad = (SELECT edad FROM cliente WHERE nombre = 'Pepe Pérez') ;
        ```

      </details> 
  42. Genera un listado con los comercios que tienen su sede en la misma ciudad que tiene el comercio ʻFNACʼ. (Subconsulta).
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        ```

      </details>  
  43. Nombre de aquellos clientes que han registrado un producto de la misma forma que el cliente ʻPepe Pérezʼ. (Subconsulta).
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
          ```sql
          SELECT DISTINCT cliente.nombre FROM cliente, registra WHERE cliente.dni = registra.dni AND medio IN (SELECT DISTINCT medio FROM cliente, registra WHERE cliente.dni = registra.dni AND cliente.nombre = 'Pepe Pérez' ) ;
          ```
      </details> 
  44. Obtener el número de programas que hay en la tabla programas.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select COUNT(codigo) FROM programa ;
        ```

      </details>
  45. Calcula el número de clientes cuya edad es mayor de 40 años.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT COUNT(dni) FROM cliente WHERE edad > 40 ;
        ```

      </details> 
  46. Calcula el número de productos que ha vendido el establecimiento cuyo CIF es 1.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT SUM(cantidad) FROM distribuye WHERE cif = 1;
        ```

      </details>  
  47. Calcula la media de programas que se venden cuyo código es 7.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select avg(cantidad) from distribuye as d,programa as p where  d.codigo = p.codigo and p.codigo = 7 ;
        ```

      </details>   
  48. Calcula la mínima cantidad de programas de código 7 que se ha vendido.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT MIN(cantidad) FROM distribuye,programa
        WHERE distribuye.codigo = programa.codigo
        AND programa.codigo = 7 ;
        ```

      </details> 
  49. Calcula la máxima cantidad de programas de código 7 que se ha vendido.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select max(cantidad) from distribuye as d,programa as p
        where d.codigo = p.codigo
        and p.codigo = 7 ;
        ```

      </details> 
  50. ¿En cuántos establecimientos se vende el programa cuyo código es 7?
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        select count (c.cif) from  comercio as c,distribuye as d
        where d.cif = c.cif
        and d.codigo = 7 ;
        ```

      </details> 
  51. Calcular el número de registros que se han realizado por Internet.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT COUNT(dni) FROM registra 
        WHERE medio="INTERNET" ;
        ```

      </details>  
  52. Obtener el número total de programas que se han vendido en ʻSevillaʼ.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT SUM(distribuye.cantidad) FROM comercio,distribuye
        WHERE comercio.cif=distribuye.cif
        AND comercio.ciudad="SEVILLA" ;
        ```

      </details> 
  53. Calcular el número total de programas que han desarrollado los fabricantes cuyo país es ʻEstados Unidosʼ.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT COUNT(programa.codigo) FROM fabricante, desarrolla, programa
        WHERE fabricante.id_fab=desarrolla.id_fab
        AND desarrolla.codigo=programa.codigo
        AND fabricante.pais="Estados Unidos" ;
        ```

      </details> 
  54. Visualiza el nombre de todos los clientes en mayúscula. En el resultado de la consulta debe aparecer también la longitud de la cadena nombre.
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT UPPER(nombre), LENGTH(nombre) FROM cliente ;
        ```

      </details>  
  55. Con una consulta concatena los campos nombre y versión de la tabla PROGRAMA.   
      <details>
        <summary>SOLUCIÓN</summary>
        </br>
        
        ```sql
        SELECT  nombre || version FROM programa ;
        ```

      </details> 