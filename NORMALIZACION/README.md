<div align="justify">

# NORMALIZACION

El diseño de una BD relacional se puede realizar aplicando al mundo real, en una primera fase, un modelo como el modelo E/R, a fin de obtener un esquema conceptual; en una segunda fase, se transforma dicho esquema al modelo relacional mediante las correspondientes reglas de transformación. También es posible, aunque quizás menos recomendable, obtener el esquema relacional sin realizar ese paso intermedio que es el esquema conceptual. En ambos casos, es conveniente (obligatorio en el modelo relacional directo) aplicar un conjunto de reglas, conocidas como __Teoría de normalización__, que nos permiten asegurar que un esquema relacional cumple unas ciertas propiedades, evitando:

- La __redundancia__ de los datos: repetición de datos en un sistema.
- __Anomalías de actualización__: inconsistencias de los datos como resultado de datos redundantes y actualizaciones parciales.
- __Anomalías de borrado__: pérdidas no intencionadas de datos debido a que se han borrado otros datos.
- __Anomalías de inserción__: imposibilidad de adicionar datos en la base de datos debido a la ausencia de otros datos.

En la práctica, _si la BD se ha diseñado haciendo uso de modelos semánticos como el modelo E/R_ __NO__ _suele ser necesaria la normalización_. Por otro lado __SI__ _nos proporcionan una base de datos creada sin realizar un diseño previo, es muy probable que necesitemos normalizar_.

En la teoría de bases de datos relacionales, _las formas normales_ __(FN)__ _proporcionan los criterios para determinar el grado de vulnerabilidad de una tabla a inconsistencias y anomalías lógicas. Cuanto más alta sea la forma normal aplicable a una tabla, menos vulnerable será a inconsistencias y anomalías_.
 > P.Examen: Esta afirmación es un posible pregunta de examen.

Edgar F. Codd definió originalmente las tres primeras formas normales __(1FN, 2FN, y 3FN) en 1970__. Estas formas normales se han resumido como requiriendo que todos los atributos sean atómicos, dependan de la clave completa y en forma directa (no transitiva). _La forma normal de_ __Boyce-Codd (FNBC)__ fue introducida en __1974__ por los dos autores que aparecen en su denominación. Las cuarta y quinta formas normales __(4FN y 5FN)__ _se ocupan específicamente de la representación de las relaciones muchos a muchos y uno a muchos entre los atributos y fueron introducidas por Fagin en 1977 y 1979 respectivamente_. __Cada forma normal incluye a las anteriores__.

 > P.Examen: Esta última afirmación es un posible pregunta de examen.

../_images/tema2-060.png

Antes de dar los conceptos de formas normales veamos unas definiciones previas:
- __Dependencia funcional__: _A → B_, representa que __B es funcionalmente dependiente de A__. _Para un valor de A siempre aparece un valor de B._
  > Ejemplo: Si A es el D.N.I., y B el Nombre, está claro que para un número de D.N.I, siempre aparece el mismo nombre de titular.

- __Dependencia funcional completa__: _A → B_, __si B depende de A en su totalidad__. _Tiene sentido plantearse este tipo de dependencia cuando A está compuesto por más de un atributo_.
  > Supongamos que A corresponde al atributo compuesto: D.N.I._Empleado + Cod._Dpto. y B es Nombre_Dpto. En este caso B depende del Cod_Dpto., pero no del D.N.I._Empleado. Por tanto no habría dependencia funcional completa.

- __Dependencia transitiva__: _A→B→C_. __Si A→B y B→C, Entonces decimos que C depende de forma transitiva de A__.       
  > Sea A el D.N.I. de un alumno, B la localidad en la que vive y C la provincia. Es un caso de dependencia transitiva A→ B → C.

- __Determinante funcional__: _todo atributo, o conjunto de ellos, de los que depende algún otro atributo_.

  > El D.N.I. es un determinante funcional pues atributos como nombre, dirección, localidad, etc, dependen de él.

- __Dependencia multivaluada__: _A→→B_. _Son un tipo de dependencias en las que un determinante funcional no implica un único valor, sino un conjunto de ellos_. __Un valor de A siempre implica varios valores de B.__
  > CursoBachillerato →→ Modalidad. Para primer curso siempre va a aparecer en el campo Modalidad uno de los siguientes valores: Ciencias, Humanidades/Ciencias Sociales o Artes. Igual para segundo curso.

## Primera Forma Normal: 1FN

Una Relación está en 1FN si y sólo si cada atributo es atómico.

  > Supongamos que tenemos la siguiente tabla con datos de alumnado de un centro de enseñanza secundaria.

Alumnos

DNI | Nombre | Curso | FechaMatrícula	Tutor | Localidad | Provincia | Teléfonos
---|---|---|---|---|---|---|
11111111A | Eva | 1ESO-A | 01-Julio-2016 | Isabel | Écija | Sevilla | 660111222  |
22222222B | Ana | 1ESO-A | 09-Julio-2016 | Isabel | Écija | Sevilla | 660222333 660333444 660444555 |
33333333C | Susana | 1ESO-B | 11-Julio-2016 | Roberto | Écija | Sevilla |   |
44444444D | Juan | 2ESO-A | 05-Julio-2016 | Federico | El Villar | Córdoba |   |
55555555E | José | 2ESO-A | 02-Julio-2016 | Federico | El Villar | Córdoba | 661000111 661000222 |

Como se puede observar, esta tabla no está en 1FN puesto que el campo Teléfonos contiene varios datos dentro de una misma celda y por tanto no es un campo cuyos valores sean atómicos. La solución sería la siguiente:

Alumnos
DNI	Nombre	Curso	FechaMatrícula	Tutor	LocalidadAlumno	ProvinciaAlumno
11111111A	Eva	1ESO-A	01-Julio-2016	Isabel	Écija	Sevilla
22222222B	Ana	1ESO-A	09-Julio-2016	Isabel	Écija	Sevilla
33333333C	Susana	1ESO-B	11-Julio-2016	Roberto	Écija	Sevilla
44444444D	Juan	2ESO-A	05-Julio-2016	Federico	El Villar	Córdoba
55555555E	José	2ESO-A	02-Julio-2016	Federico	El Villar	Córdoba
Teléfonos
DNI	Teléfono
11111111A	660111222
22222222B	660222333
22222222B	660333444
22222222B	660444555
55555555E	661000111
55555555E	661000222
2.6.2. Segunda Forma Normal: 2FN
Una Relación esta en 2FN si y sólo si está en 1FN y todos los atributos que no forman parte de la Clave Principal tienen dependencia funcional completa de ella.

Ejemplo: Seguimos con el ejemplo anterior. Trabajaremos con la siguiente tabla:

Alumnos
DNI	Nombre	Curso	FechaMatrícula	Tutor	LocalidadAlumno	ProvinciaAlumno
11111111A	Eva	1ESO-A	01-Julio-2016	Isabel	Écija	Sevilla
22222222B	Ana	1ESO-A	09-Julio-2016	Isabel	Écija	Sevilla
33333333C	Susana	1ESO-B	11-Julio-2016	Roberto	Écija	Sevilla
44444444D	Juan	2ESO-A	05-Julio-2016	Federico	El Villar	Córdoba
55555555E	José	2ESO-A	02-Julio-2016	Federico	El Villar	Córdoba
Vamos a examinar las dependencias funcionales. El gráfico que las representa es el siguiente:

../_images/tema2-062.png
Siempre que aparece un DNI aparecerá el Nombre correspondiente y la LocalidadAlumno correspondiente. Por tanto DNI → Nombre y DNI → LocalidadAlumno. Por otro lado siempre que aparece un Curso aparecerá el Tutor correspondiente. Por tanto Curso → Tutor. Los atributos Nombre y LocalidadAlumno no dependen funcionalmente de Curso, y el atributo Tutor no depende funcionalmente de DNI.
El único atributo que sí depende de forma completa de la clave compuesta DNI y Curso es FechaMatrícula: (DNI,Curso) → FechaMatrícula.
A la hora de establecer la Clave Primaria de una tabla debemos escoger un atributo o conjunto de ellos de los que dependan funcionalmente el resto de atributos. Además debe ser una dependencia funcional completa. Si escogemos DNI como clave primaria, tenemos un atributo (Tutor) que no depende funcionalmente de él. Si escogemos Curso como clave primaria, tenemos otros atributos que no dependen de él.

Si escogemos la combinación (DNI, Curso) como clave primaria, entonces sí tenemos todo el resto de atributos con dependencia funcional respecto a esta clave. Pero es una dependencia parcial, no total (salvo FechaMatrícula, donde sí existe dependencia completa). Por tanto esta tabla no está en 2FN. La solución sería la siguiente:

Alumnos
DNI	Nombre	Localidad	Provincia
11111111A	Eva	Écija	Sevilla
22222222B	Ana	Écija	Sevilla
33333333C	Susana	El Villar	Córdoba
44444444D	Juan	El Villar	Córdoba
55555555E	José	Écija	Sevilla
Matrículas
DNI	Curso	FechaMatrícula
11111111A	1ESO-A	01-Julio-2016
22222222B	1ESO-A	09-Julio-2016
33333333C	1ESO-B	11-Julio-2016
44444444D	2ESO-A	05-Julio-2016
55555555E	2ESO-A	02-Julio-2016
Cursos
Curso	Tutor
1ESO-A	Isabel
1ESO-B	Roberto
2ESO-A	Federico
2.6.3. Tercera Forma Normal: 3FN
Una Relación esta en 3FN si y sólo si está en 2FN y no existen dependencias transitivas. Todas las dependencias funcionales deben ser respecto a la clave principal.

Ejemplo: Seguimos con el ejemplo anterior. Trabajaremos con la siguiente tabla:

Alumnos
DNI	Nombre	Localidad	Provincia
11111111A	Eva	Écija	Sevilla
22222222B	Ana	Écija	Sevilla
33333333C	Susana	El Villar	Córdoba
44444444D	Juan	El Villar	Córdoba
55555555E	José	Écija	Sevilla
Las dependencias funcionales existentes son las siguientes. Como podemos observar existe una dependencia funcional transitiva: DNI → Localidad → Provincia

../_images/tema2-064.png
Para que la tabla esté en 3FN, no pueden existir dependencias funcionales transitivas. Para solucionar el problema deberemos crear una nueva tabla. El resultado es:

Alumnos
DNI	Nombre	Localidad
11111111A	Eva	Écija
22222222B	Ana	Écija
33333333C	Susana	El Villar
44444444D	Juan	El Villar
55555555E	José	Écija
Localidades
Localidad	Provincia
Écija	Sevilla
El Villar	Córdoba
RESULTADO FINAL

Alumnos
DNI	Nombre	Localidad
11111111A	Eva	Écija
22222222B	Ana	Écija
33333333C	Susana	El Villar
44444444D	Juan	El Villar
55555555E	José	Écija
Localidades
Localidad	Provincia
Écija	Sevilla
El Villar	Córdoba
Teléfonos
DNI	Teléfono
11111111A	660111222
22222222B	660222333
22222222B	660333444
22222222B	660444555
55555555E	661000111
55555555E	661000222
Matrículas
DNI	Curso	FechaMatrícula
11111111A	1ESO-A	01-Julio-2016
22222222B	1ESO-A	09-Julio-2016
33333333C	1ESO-B	11-Julio-2016
44444444D	2ESO-A	05-Julio-2016
55555555E	2ESO-A	02-Julio-2016
Cursos
Curso	Tutor
1ESO-A	Isabel
1ESO-B	Roberto
2ESO-A	Federico
../_images/tema2-066.png
2.6.4. Forma Normal de Boyce-Codd: FNBC
Una Relación esta en FNBC si está en 3FN y no existe solapamiento de claves candidatas. Solamente hemos de tener en cuenta esta forma normal cuando tenemos varias claves candidatas compuestas y existe solapamiento entre ellas. Pocas veces se da este caso.

Ejemplo: Tenemos una tabla con información de proveedores, códigos de piezas y cantidades de esa pieza que proporcionan los proveedores. Cada proveedor tiene un nombre único. Los datos son:

Suministros
CIF	Nombre	CódigoPieza	CantidadPiezas
S-11111111A	Ferroman	1	10
B-22222222B	Ferrotex	1	7
M-33333333C	Ferropet	3	4
S-11111111A	Ferroman	2	20
S-11111111A	Ferroman	3	15
B-22222222B	Ferrotex	2	8
B-22222222B	Ferrotex	3	4
El gráfico de dependencias funcionales es el siguiente:

../_images/tema2-067.png
El atributo CantidadPiezas tiene dependencia funcional de dos claves candidatas compuestas, que son:

(NombreProveedor, CodigoPieza)
(CIFProveedor, CódigoPieza)
Existe también una dependencia funcional en doble sentido (que no nos afecta): NombreProveedor <-> CIFProveedor.

Para esta tabla existe un solapamiento de 2 claves candidatas compuestas. Para evitar el solapamiento de claves candidatas dividimos la tabla. La solución es:

Proveedores
CIF	Nombre
S-11111111A	Ferroman
B-22222222B	Ferrotex
M-33333333C	Ferropet
Suministros
CIF	CódigoPieza	CantidadPiezas
S-11111111A	1	10
B-22222222B	1	7
M-33333333C	3	4
S-11111111A	2	20
S-11111111A	3	15
B-22222222B	2	8
B-22222222B	3	4
2.6.5. Cuarta Forma Normal: 4FN
Una Relación esta en 4FN si y sólo si está en 3FN (o FNBC) y las únicas dependencias multivaluadas son aquellas que dependen de las claves candidatas.

Ejemplo: Tenemos una tabla con la información de nuestros alumnos y alumnas y las asignaturas que cursan así como los deportes que practican.

Alumnado
Estudiante	Asignatura	Deporte
11111111A	Matemáticas, Lengua	Baloncesto
22222222B	Matemáticas	Fútbol, Natación
Alumnado
Estudiante	Asignatura	Deporte
11111111A	Matemáticas	Natación
11111111A	Matemáticas	Baloncesto
11111111A	Lengua	Natación
11111111A	Lengua	Baloncesto
22222222B	Matemáticas	Fútbol
22222222B	Matemáticas	Natación
Para normalizar esta tabla, debemos darnos cuenta que la oferta de asignaturas está compuesta por un conjunto de valores limitado. Igual sucede con los deportes. Por tanto existen dos dependencias multivaluadas:

Estudiante →→ Asignatura
Estudiante →→ Deporte
Por otro lado no existe ninguna dependencia entre la asignatura cursada y el deporte practicado. Para normalizar a 4FN creamos 2 tablas:

EstudiaAsignatura
Estudiante	Asignatura
11111111A	Matemáticas
11111111A	Lengua
22222222B	Matemáticas
PracticaDeporte
Estudiante	Deporte
11111111A	Natación
11111111A	Baloncesto
22222222B	Fútbol
22222222B	Natación
Diagrama E/R equivalente

../_images/tema2-068.png
2.6.6. Quinta Forma Normal: 5FN
La quinta forma normal (5FN), es una generalización de la anterior. También conocida como forma normal de proyección-unión (PJ/NF). Una tabla se dice que está en 5NF si y sólo si está en 4NF y cada dependencia de unión (join) en ella es implicada por las claves candidatas. Ejemplo: Tenemos una tabla con varios proveedores que nos proporcionan piezas para distintos proyectos. Asumimos que un Proveedor suministra ciertas Piezas en particular, un Proyecto usa ciertas Piezas, y un Proyecto es suplido por ciertos Proveedores, entonces tenemos las siguientes dependencias multivaluadas:

Proveedor →→ Pieza
Pieza →→ Proyecto
Proyecto →→ Proveedor
Se puede observar como se produce un ciclo:

Proveedor →→ Pieza →→ Proyecto →→ Proveedor (nuevamente)
Suministros
Proveedor	Pieza	Proyecto
E1, E4, E6	PI3, PI6	PR2, PR4
E2, E5	PI1, PI2	PR1, PR3
E3, E7	PI4, PI5	PR5, PR6
Suministros
Proveedor	Pieza	Proyecto
E1	PI3	PR2
E1	PI3	PR4
E1	PI6	PR2
E1	PI6	PR4
E4	PI3	PR2
E4	PI3	PR4
E4	PI6	PR2
E4	PI6	PR4
E6	PI3	PR2
E6	PI3	PR4
E6	PI6	PR2
E6	PI6	PR4
E2	PI1	PR1
E2	PI1	PR3
E2	PI2	PR1
E2	PI2	PR3
E5	PI1	PR1
E5	PI1	PR3
E5	PI2	PR1
E5	PI2	PR3
E3	PI4	PR5
E3	PI4	PR6
E3	PI5	PR5
E3	PI5	PR6
E7	PI4	PR5
E7	PI4	PR6
E7	PI5	PR5
E7	PI5	PR6
Descomponemos la tabla en 3 tabla nuevas: Proveedor-Pieza, Pieza-Proyecto, Proyecto-Proveedor.

Proveedor-Pieza
Proveedor	Pieza
E1	PI3
E1	PI6
E4	PI3
E4	PI6
E6	PI3
E6	PI6
E2	PI1
E2	PI2
E5	PI1
E5	PI2
E3	PI4
E3	PI5
E7	PI4
E7	PI5
Pieza-Proyecto
Pieza	Proyecto
PI3	PR2
PI3	PR4
PI6	PR2
PI6	PR4
PI1	PR1
PI1	PR3
PI2	PR1
PI2	PR3
PI4	PR5
PI4	PR6
PI5	PR5
PI5	PR6
Proyecto-Proveedor
Proyecto	Proveedor
PR2	E1
PR4	E1
PR2	E4
PR4	E4
PR2	E6
PR4	E6
PR1	E2
PR3	E2
PR1	E5
PR3	E5
PR5	E3
PR6	E3
PR5	E7
PR6	E7
El producto natural de estas 3 tablas nos da la tabla original. Proveedor-Pieza |x| Pieza-Proyecto |x| Proyecto-Proveedor = Suministros

Diagrama E/R equivalente

../_images/tema2-069.png
</div>
