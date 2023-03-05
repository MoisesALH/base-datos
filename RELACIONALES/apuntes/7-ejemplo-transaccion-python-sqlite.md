# Ejemplo de transacciones en Python

<div align="justify">

Un ejemplo de transacción podría ser el siguiente:

```sql
BEGIN TRANSACTION;
CREATE TABLE test (i integer);
INSERT INTO "test" VALUES(99);
COMMIT;
```

Veamos como sería programando:

```python
import sqlite3

sql = sqlite3.connect("test.db")
with sql:
    c = sql.cursor()
    c.executescript("""
        update test set i = 1;
        fnord;
        update test set i = 0;
        """)
```        

Como podemos observar, la ejecución de este código puede producir un error, y no estaría controlado.

Veamos como mejorar el código:

```python
import sqlite3

sql = sqlite3.connect("test.db")
try:
    c = sql.cursor()
    c.executescript("""
        update test set i = 1;
        fnord;
        update test set i = 0;
    """)
    sql.commit()
except sql.Error:
    print("failed!")
    sql.rollback()
```

Ahora veamos como crear el código correctamente:

```python
import sqlite3

sql = sqlite3.connect("test.db")
try:
    c = sql.cursor()
    c.execute("begin")
    c.executescript("""
            update test set i = 1;
            fnord;
            update test set i = 0;
    """)
    c.execute("commit")
except sql.Error:
    print("failed!")
    c.execute("rollback")
```    

Un error producirá un error del tipo:

```python
sqlite3.OperationalError: cannot rollback - no transaction is active
```

La corrección del código es la sustitución de  c.__execute()__ por __c.executescript()__.

```python
import sqlite3

sql = sqlite3.connect("test.db")
try:
    c = sql.cursor()
    c.executescript("begin")
    c.executescript("""
            update test set i = 1;
            fnord;
            update test set i = 0;
    """)
    c.executescript("commit")
except sql.Error:
    print("failed!")
    c.executescript("rollback")
```    

</div>