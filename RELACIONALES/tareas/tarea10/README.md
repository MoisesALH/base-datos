<div>

<div align="center">
<img src="https://www.autopista.es/uploads/s1/10/49/54/48/encuentra-millones-de-pieza-de-recambio-para-tu-coche-garantizadas-en-internet-de-esta-forma-foto-istock.jpeg" width="600px"/>
</div>

Dadas las siguientes tablas :

pieza:
 - id: entero
 - nombre: texto

suministrador:
 - ref_pieza_codigo: entero
 - ref_proveedor: texto
 -  precio: enterio

proveedor:
 - id: texto
 - nombre: texto

Se pide:

Crea la estrucuta de tablas en función de las propiedades y sus nombres para determinar las claves primarias, claves foraneas.

Realiza la inserción de datos teniendo en cuenta los siguientes datos:
- Debe existir piezas suministradas por un proveedor con códgo __HAL__.
- Existira el suministrador _SkeHington Supplies_ (con código __TNBC__).
- Existira el suministrador _Susan Calvin Corp_  (con código __RBT__).
- La empresa con código __RBT__ debe suministrar las piezas con código 4.
- Se debe de crear al menos 10 piezas y 5 proveedores, asi como la relación entre ellos.

Realizar las siguientes consultas:
1. Obtener los nombres de todas las piezas.
2. Obtener todos los datos de todos los proveedores.
3. Obtener el precio medio al que se nos suministran las piezas.
4. Obtener los nombres de los proveedores que suministran la pieza 1.
5. Obtener los nombres de las piezas suministradas por el proveedor cuyo código es
__HAL__.
6. Obtener los nombres de los proveedores que suministran las piezas más caras,
indicando el nombre de la pieza y el precio al que la suministran.
7. Hacer constar en la base de datos que la empresa _SkeHington Supplies_ (codigo
__TNBC__) va a empezar a suministrarnos los elementos piezas con _código 1_ a 10 € cada tuerca.
8. Aumentar los precios en una unidad.
9. Hacer constar en la base de datos que la empresa _Susan Calvin Corp._(__RBT__) no
va a suministrarnos ninguna pieza (aunque la empresa en si va a seguir constando en nuestra base de datos).
10. Hacer constar en la base de datos que la empresa _Susan Calvin Corp._ (RBT) ya
no va a suministrarnos clavos (código 4).

Se debe de entregar un fichero _Nombre_Apellido1_Apellido2.sql_ con:
- Sentencias para la creación de la BBDD.
- Sentencias para la inserción de los elementos.
- Sentencias con cada una de las consultas solicitadas.
