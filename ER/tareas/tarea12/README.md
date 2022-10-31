<div align="justify">

# Gestión Docente

<div align="center">
<img src="img/docente.png" width="400px"/>
</div>

Diseñar una Base de Datos para representar la información docente de un colegio, sabiendo que:
La formación abarca ocho cursos (1º, 2º, 3º .. 8º) en los que se imparten diversas asignaturas, tales como Matemáticas, Física, Ciencias Naturales, Sociales, Dibujo, etc., dándose el caso de algunas asignaturas de distintos cursos que tienen el mismo nombre.
Cada curso se reparte en varios grupos de alumnos a los que se asigna una letra: p.e. 3ºA, 2ºD, 5ºC, 1ºB, y se ubican en un aula fija para todo el curso. Las aulas, identificadas por un número, tienen una determinada capacidad de número de alumnos. De ellas interesa conocer, además, si disponen o no de conexión a la red de computadores del centro, y de pantalla para la proyección de transparencias.
Los profesores del centro, de los que se dispone de su nombre y apellidos, DNI, dirección y teléfono, pueden impartir varias asignaturas distintas a grupos distintos. Además, cada curso tiene un profesor coordinador y cada grupo un profesor tutor.
Acerca de los alumnos, además de su nombre y apellidos, dirección y teléfono, se desea reflejar el curso en que están matriculados y el grupo al que están asignados. También se desea representar qué alumno es el delegado de cada grupo. Como puede darse el caso, de alumnos con el mismo nombre y apellidos, cada alumno tiene asociado un (único) número de matrícula que facilita su identificación.

Se pide:
1. Proponer las frases que describan el problema.
2. Identifica las posibles __entidades, relaciones, valores de domino,etc__.
3. Generar los entidades y relaciones de cada frase que hayas detectado, sin indicar cardinalidad, etc.
4. Monta correctamente todas las entidades y sus relaciones.
5. Colocar los atributos a cada entidad e interrelación.
6. Indica la cardinalidad de las relaciones, y explicar aquellas que se requieran necesarias.

<!--
<details>
      <summary>FRASES A TENER EN CUENTA</summary>

  Frases importantes:
  - La formación abarca ocho cursos (1º, 2º, 3º .. 8º) en los que se imparten diversas asignaturas, tales como Matemáticas, Física, Ciencias Naturales, Sociales, Dibujo, etc., dándose el caso de algunas asignaturas de distintos cursos que tienen el mismo nombre.
    > Nota: En un curso se imparte asignaturas, es decir (Curso impartir Asignatura)
  - Cada curso se reparte en varios grupos de alumnos a los que se asigna una letra: p.e. 3ºA, 2ºD, 5ºC, 1ºB, y se ubican en un aula fija para todo el curso. 
    > Nota: Cada curso consta de varios grupos, es decir (Curso constar Grupo ).
  - Cada curso tiene un profesor coordinador. 
    > Nota: Cada curso tiene un profesor que es su coordinador (Profesor coordinar Curso)
  - Cada grupo un profesor tutor .
    > Nota: Tal y como dice la frase (Profesor tutor Grupo).
  - Los profesores del centro, de los que se dispone de su nombre y apellidos, DNI, dirección y teléfono, pueden impartir varias asignaturas distintas a grupos distintos. 
    > Nota: Los profesores imparten asignaturas. (Profesor imparte Asignatura)  
  - Cada curso se reparte en varios grupos de alumnos a los que se asigna una letra: p.e. 3ºA, 2ºD, 5ºC, 1ºB, y se ubican en un aula fija para todo el curso.
    > Nota: Cada curso de ubica en un aula. (Curso ubicar Aula).
  - Acerca de los alumnos, además de su nombre y apellidos, dirección y teléfono, se desea reflejar el curso en que están matriculados y el grupo al que están asignados. 
    > Nota: Se desea reflejar sobre el alumno el curso sobre el que están matriculador. (Curso matricular Alumno).
  - También se desea representar qué alumno es el delegado de cada grupo.
    > Nota: Se desea conocer el delegado del curso. En este caso se puede representar de dos formas diferentes.
    - Opción 1: Alumno es delegado Alumno.
    - Opción 2: Curso deleago Alumno.
  </br>
</details>

<details>
      <summary>PASO 2</summary>
  </br>
  <img src="img/docente.drawio.png">
  </br>
   </br>
</details>

<details>
      <summary> PASO 3</summary>
  </br>
  <img src="img/docente.drawio.png">
  </br>
   </br>
</details>

<details>
      <summary>SOLUCION</summary>
  </br>
  <img src="img/docente.drawio.png">
  </br>
   </br>
</details>

<details>
      <summary>SOLUCION B</summary>
  </br>
  <img src="img/docente.drawio.png">
  </br>
   </br>
</details>
-->
</div>