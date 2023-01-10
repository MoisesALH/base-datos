<div align="justify">

<div align="center">
<img src="https://luciamonterorodriguez.com/wp-content/uploads/2021/03/computer-1331579_640.png" width="200px"/>
</div>

> __Nota__. Seguiremos trabajando con la tabla __usuario__.

Una clave primaria es un campo (o varios) que identifica un solo registro (fila) en una tabla.
Para un valor del campo clave existe solamente un registro.

Veamos un ejemplo, si tenemos una tabla con datos de personas, el número de documento puede establecerse como clave primaria, es un valor que no se repite; puede haber personas con igual apellido y nombre, incluso el mismo domicilio (padre e hijo por ejemplo), pero su documento será siempre distinto.

Si tenemos la tabla "usuario", el nombre de cada usuario puede establecerse como clave primaria, es un valor que no se repite; puede haber usuarios con igual clave, pero su nombre de usuario será siempre diferente.

Podemos establecer que un campo sea clave primaria al momento de crear la tabla o luego que ha sido creada. Vamos a aprender a establecerla al crear la tabla. Hay 2 maneras de hacerlo, por ahora veremos la sintaxis más sencilla.

Tenemos nuestra tabla "usuario" definida con 2 campos ("nombre" y "clave").
La sintaxis básica y general es la siguiente:

`````
create table NOMBRETABLA(
  CAMPO TIPO not null,
  ...
  primary key (NOMBRECAMPO)
 );
 `````
El códido de definición de la tabla será el siguiente:
`````
create table usuario(
        nombre text not null,
        clave text,
        primary key(nombre)
);
`````

o que hacemos agregar luego de la definición de cada campo, "primary key" y entre paréntesis, el nombre del campo que será clave primaria.

Una tabla sólo puede tener una clave primaria. Cualquier campo (de cualquier tipo) puede ser clave primaria, debe cumplir como requisito, que sus valores no se repitan. Al definir un campo como clave primaria es importante en SQLite definirlo con "not null".

Luego de haber establecido un campo como clave primaria, al ingresar los registros, SQLite controla que los valores para el campo establecido como clave primaria no estén repetidos en la tabla; si estuviesen repetidos, muestra un mensaje y la inserción no se realiza. Es decir, si en nuestra tabla "usuario" ya existe un usuario con nombre "juanperez" e intentamos ingresar un nuevo usuario con nombre "juanperez", aparece un mensaje y la instrucción "insert" no se ejecuta.

Igualmente, si realizamos una actualización, SQLite controla que los valores para el campo establecido como clave primaria no estén repetidos en la tabla, si lo estuviese, aparece un mensaje indicando que se viola la clave primaria y la actualización no se realiza.


Vamos a realizar las siguientes acciones:

``````
drop table if exists usuario;
```````

Eliminando la tabla de la base de datos.

Creamos la tabla definiendo el campo "nombre" como clave primaria:

``````
create table usuario(
	nombre text not null,
	clave text,
        primary key(nombre)
);
``````
Al campo "nombre" lo definimos "not null" para no permitir ingresar dicho valor.

Ingresamos algunos registros:

``````
insert into usuarios (nombre, clave)
  values ('juanperez','Boca');
insert into usuarios (nombre, clave)
  values ('raulgarcia','River');
``````

> __Nota__. Recordemos que cuando un campo es clave primaria, sus valores no se repiten. Intentamos ingresar un valor de clave primaria existente:

``````
insert into usuarios (nombre, clave)
  values ('juanperez','payaso');
  ``````

> __Nota__. ¿Qué mensaje estas recibiendo?



</div>