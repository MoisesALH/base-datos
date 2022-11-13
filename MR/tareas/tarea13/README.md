<div align="justify">

# Educando

<div align="center">
<img src="img/educando.png" width="400px"/>
</div>

En la Empresa __Educando S.A.__ se lleva control de sus Bienes y Servicios. El interés primario es poder hacer que los Bienes se manejen de forma rápida y con el menor grado de error. Para esto quien maneja la sección de "Bienes y Suministros" plantea las siguientes condiciones del negocio para la construcción de una base de datos:
- La Sección está dividida en tres (3) áreas: COMPRAS, ALMACEN, INVENTARIO.
- El área de Compras funciona de la siguiente forma:
  - Recibe las solicitudes de compras de las diferentes áreas de la empresa.
  - Cada solicitud tiene un responsable.
  - Cada solicitud es autorizada por el jefe del área y posteriormente por el Director Financiero.
  - Quien realiza una solicitud puede ser responsable de uno o varios centros de costos, con la salvedad de que él como empleado solo está adscrito a uno.
  - De la solicitud se debe diligenciar la siguiente información: Número de la solicitud (consecutivo), Fecha, Responsable (nombre y cédula), Centro de Costos, Rubro presupuestal del cual se descargará la compra. En cada solicitud se pueden discriminar uno o muchos ítems con la siguiente información: ítem, nombre del bien, cantidad solicitada, unidad de medida del bien, valor unitario y valor total. Cada solicitud debe ser totalizada.
  - Cada bien es identificado por un código universal que es único y es de carácter devolutivo (suministro) o un bien inmueble.
  - Una vez diligenciada la solicitud es remitida al área de compras para realizar su correspondiente cotización.
  - Las cotizaciones son realizadas con uno o varios proveedores de los bienes solicitados.
  - Una vez la cotización definitiva está lista, se crea una orden contractual que maneja la siguiente información: Número de la orden contractual, nit y nombre del proveedor al cual se le va a realizar la compra, fecha de la orden, monto total de la orden, fecha de entrega. Cada orden puede tener asociado uno o varios ítems de la solicitud o solicitudes que van a ser despachadas. Cada ítem tiene la siguiente información:
    - nombre del bien
    - cantidad solicitada
    - cantidad despachada
    - unidad de medida del bien
    - valor unitario
    - valor total.

  - La orden de compra es aprobada por el Director Financiero para que sea enviada al proveedor elegido.

- El área de Almacén funciona de la siguiente forma:
  - Su función principal es recepcionar los bienes que llegan de los proveedores y distribuirlos a las correspondientes áreas que realizaron las solicitudes de compras.
  - Cuando llega un proveedor mercancía, este hace una entrega física de los bienes, los cuales son comparados con la factura que este entrega y con la orden de compra correspondiente. Si esta acción es correcta se registra una entrada de almacén por cada factura relacionada, con la siguiente información: Número de Entrada, Fecha, Número de factura, Proveedor, Total Bienes, Valor Total (los totales deben coincidir con los de la factura). Adjunto a esta se discriminan los ítems recibidos con la siguiente información: nombre del bien, cantidad entregada.
  - Cuando el almacén decide despachar los bienes a las diferentes áreas solicitantes, registra cada una de las entregas en Salidas de Almacén con la siguiente información:
  - Número de Salida, Empleado responsable del bien a entregar, fecha de salida, fecha de entrega. Por cada entrega se detalla cada uno de los ítems con la siguiente información: nombre del bien, cantidad entregada.
  - Una entrada de almacén puede generar muchas salidas de almacén, por ejemplo: Pueden ingresar 500 pacas de papel higiénico, pero como se debe repartir entre varias áreas, cada una requiere de una salida de almacén.
- El área de inventarios funciona de la siguiente forma:
  - Es la encargada de administrar y controlar la ubicación de los bienes dentro de la empresa, por esto antes de que el bien salga del almacén debe ser codificado a través de un código único que lo haga identificable dentro de la empresa.
  - La ubicación del bien se identifica por la siguiente información: responsable del bien, fecha de entrega, dirección del bien (ubicación).

<div align="center">
<img src="img/er-grande.png" width="900px"/>
</div>

Se pide:
1. Transforma el digagrama que se aporta en sub-diagramas más simples.
2. Realiza la tranformación de cada uno de ellos.
3. Une todas las transformaciones en una resultante.

<!-- 
<details>
      <summary>Paso 1</summary>
  </br>
  <img src="img/paso1.png">
  </br>
   </br>
</details>

<details>
      <summary>Paso 2</summary>
  </br>
  <img src="img/paso1.png">
  </br>
   </br>
</details>

<details>
      <summary>Paso 3</summary>
  </br>
  <img src="img/paso1.png">
  </br>
   </br>
</details>
-->

</div>