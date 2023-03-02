# Transacciones


“__Las transacciones__ son __bloques o secuencias__ de trabajo lógicamente organizados que un DBMS puede ejecutar manual o mecánicamente. Cuando crea, cambia o elimina datos de la tabla, realiza transacciones en la tabla. El control de las transacciones es fundamental para mantener la integridad de los datos y tratar los problemas de la base de datos. En SQLite, una transacción es un grupo de comandos T-SQL ejecutados como un comando T-SQL único. Si se produce un error al ejecutar estos comandos de SQLite, la transacción se revertirá por completo. En general, SQLite está en modo de confirmación automática, lo que significa que cada comando crea automáticamente una transacción, la procesa y confirma los cambios en la base de datos. En este artículo, mostramos cómo se implementa la transacción SQLite para garantizar la integridad y confiabilidad de los datos”.

## Propiedades de la transacción SQLite

SQLite es una base de datos transaccional, lo que significa que todas las actualizaciones y búsquedas son atómicas, consistentes, aisladas y de larga duración (ACID). Las cuatro funciones estándar enumeradas a continuación, comúnmente abreviadas como ACID, están presentes en las transacciones.
- __Atomicidad__: Un solo paso del proceso debe ser completado por una transacción atómica. Significa que un mod no se puede dividir en componentes más pequeños. Cuando una transacción está en modo COMPROMISO, se confirma la transacción completa o no.
- __Consistencia__: Las transacciones deben garantizar que la base de datos cambie de un estado legítimo al siguiente. La base de datos se vuelve inconsistente cuando una transacción inicia y ejecuta un comando para actualizar los datos. Sin embargo, la base de datos debe permanecer consistente cuando las transacciones se confirman y revierten.
- __Aislamiento__: La transacción pendiente de la sesión debe estar separada de otras sesiones. Cuando una sesión inicia una transacción y usa el comando _INSERTAR o ACTUALIZAR_ para cambiar datos, los cambios son accesibles solo para la operación actual y no para otros. Por otro lado, los cambios realizados por otros usuarios después de iniciada la transacción nunca deberían ser visibles para el usuario actual.
- __Durabilidad__: Si una transacción se confirma correctamente, los cambios en la base de datos deben ser persistentes en caso de un corte de energía o un bloqueo del programa. La actualización no debería persistir si el programa sale primero antes de que se confirme la transacción.

## ¿Cómo realizo transacciones en SQLite?

Supongamos que queremos regular dichas transacciones para mantener la consistencia de los datos y manejar los errores de la base de datos. Podemos detener el modo de confirmación automática e iniciar explícitamente las transacciones según nuestras necesidades utilizando las siguientes declaraciones.

- __EMPEZAR__: Este es el punto donde se inicia la transacción.
- __COMPROMETERSE__: Usando esta terminología en SQLite, confirmaremos la transacción, lo que significa que todos los cambios se guardarán en la base de datos.
- __REINICIAR__: La transacción en su totalidad será cancelada.
Tenga en cuenta que solo las operaciones __DML INSERTAR, ACTUALIZAR y ELIMINAR__ utilizan sentencias de control de transacciones. No se pueden usar para extraer tablas porque la base de datos confirma inmediatamente estas operaciones.

## Creación de tablas SQLite para ejecutar transacciones

Para realizar transacciones, primero debemos crear una tabla. En la imagen, puede ver que creamos una tabla llamada person_accounts. La tabla se especifica con las cuatro columnas person_id, person_name, account_number y account_balance con sus tipos de datos.

```sql
CREATE TABLE person_accounts(
     person_id INT PRIMARY KEY ,
       person_name CHAR(10) ,
       account_number INT , 
       account_balance FLOAT );
```

Aquí hemos insertado un registro usando el comando de inserción de SQLite.

```sql

 INSERT VALUE IN person_accounts (1, ‘Ayat’, 171636460, 5000);
 INSERT VALUE IN person_accounts (2, ‘Muneeb’, 673201984, 8000);  INSERT VALUE IN person_accounts (4, ‘Maya’, 501738449, 7500);
 ```

 La tabla se puede ver en formato de tabla de la siguiente manera:

 ```sql
 select * from person_accounts;
 ```

 ## Realizar una transacción con el comando BEGIN en SQLite

 ___BEGIN TRANSACTION___ o el comando _BEGIN_ se pueden utilizar para iniciar transacciones. Sin embargo, si la base de datos finaliza o se produce un error, la transacción será _ROLLBACK_. 

 <div align="center">
<img src="https://territoriomovil.net/wp-content/uploads/2022/06/sqlite-transactions-04.jpg" width="500px"/>
</div>

La traducción se realiza correctamente para la tabla person_accounts y el campo account_balance se actualiza para el person_id proporcionado.

 <div align="center">
<img src="https://territoriomovil.net/wp-content/uploads/2022/06/sqlite-transactions-05.jpg" width="500px"/>
</div>

## Ejecutar transacción en el comando COMMIT en SQLite

El comando __COMMIT__ es un comando transaccional que guarda los cambios activados por transacciones en la base de datos. El comando __COMMIT__ conserva todas las transacciones de la base de datos desde la instrucción anterior __COMMIT o ROLLBACK__. En el siguiente ejemplo, tenemos el primer inicio de la transacción con el término __BEGIN TRANSACTION__. Después de eso, tenemos el comando de inserción, que inserta un nuevo registro en la tabla person_accounts. Dimos un comando __COMMIT__ al final que finaliza la transacción aquí y guarda el cambio en la tabla dada. 

 <div align="center">
<img src="https://territoriomovil.net/wp-content/uploads/2022/06/sqlite-transactions-06.jpg" width="500px"/>
</div>

La vista de tabla muestra el nuevo registro en la siguiente tabla.

<div align="center">
<img src="https://territoriomovil.net/wp-content/uploads/2022/06/sqlite-transactions-07.jpg" width="500px"/>
</div>

## Ejecutar transacción en el comando ROLLBACK en SQLite

__ROLLBACK__ es un comando transaccional que se utiliza para deshacer transacciones que aún no se han escrito en la base de datos. Aquí realizamos la operación __DELETE__ en la tabla de cuentas_personas donde coincidió con la condición en el campo número_cuenta especificado. Después de eso, dimos declaraciones __ROLLBACK__ que también finalizan la transacción aquí pero no guardan los cambios que hicimos en la tabla.

<div align="center">
<img src="https://territoriomovil.net/wp-content/uploads/2022/06/sqlite-transactions-08.jpg" width="500px"/>
</div>

Después de realizar la operación ROLLBACK, la tabla tendrá los mismos valores y campos que antes existían en la tabla.

<div align="center">
<img src="https://territoriomovil.net/wp-content/uploads/2022/06/sqlite-transactions-09.jpg" width="500px"/>
</div>