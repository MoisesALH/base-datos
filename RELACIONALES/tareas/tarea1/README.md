<div align="justify">

<div align="center">
<img src="https://luciamonterorodriguez.com/wp-content/uploads/2021/03/computer-1331579_640.png" width="200px"/>
</div>


tabla fabricante
  id_fab entero primary key,
  nombre texto,
  pais   texto;

tabla programa(
  codigo entero primary key,
  nombre texto,
  version texto);

tabla comercio(
  cif entero primary key,
  nombre texto,
  ciudad texto);

tabla cliente(
  dni entero primary key,
  nombre texto,
  edad entero);

tabla desarrolla(
  id_fab entero,
  codigo entero,
  primary key(id_fab,codigo);

tabla distribuye(
  cif entero,
  codigo entero,
  cantidad entero,
  primary key(cif,codigo);

tabla registra(
  cif entero,
  dni entero,
  codigo entero,
  medio texto,
  primary key(cif,dni);
  