# Proyecto del Primer Cuatrimestre Fundamentos de Programación (Curso  \<22\>/\<23\>)
Autor/a: \<Lucía Noya Cano\>   uvus:\<lucnoycan\>

El proyecto tiene como objetivo listar de los estudiantes registrados en estudios superiores en universidades y colegios franceses al cual se puede acceder a través de la siguiente URL (https://www.kaggle.com/datasets/mpwolke/cusersmarildownloadsetudiantscsv?resource=download). El fichero original consta de 
25 columnas, ninguna de tipo fecha, por lo que se ha añadido una, creada por la función de fecha aleatoria, por otro lado, se han eliminado varias columnas al estar varias duplicadas y algunas con información irrelevante, y modificado una columna de tipo entero transformándola a tipo real pues el csv no contenía ningún dato de dicho tipo, quedando finalmente 13 columnas de las 25 totales. Por último, al ser datos franceses estaban registrados en francés por lo que han sido traducido algunos para que sean más fáciles a la hora de comprenderlos.
## Estructura de las carpetas del proyecto

* **/src**: Contiene los diferentes módulos de Python que conforman el proyecto.
  * **\<modulo1.py\>**: Contiene funciones que permiten trabajar con los datos del fichero.
  * **\<modulo1_test.py\>**: Contiene funciones de test para probar las funciones del módulo modulo1.py. En este módulo está el main.
* **/data**: Contiene el dataset o datasets del proyecto
    * **\<dataset1.csv\>**: Contiene los datos registrados de los estduiantes franceses.
    
    
## Estructura del *dataset*

El dataset recoge los datos personales de un único estudiante anónimo, pues no incluye su nombre y apellidos. Están registrados 13 datos por persona.
Por lo que el dataset está compuesto por 13 columnas, con la siguiente descripción:

* **\<rentree 1>**: de tipo \<int\>, representa el año de entrada en la institución
* **\<fecha_nacimiento>**: de tipo \<date\>, representa la fecha de nacimiento del estudiante
* **\<nivel_geo>**:de tipo \<str\>, representa el nivel geográfico del que procede el estudiante
* **\<nombre_geo>**: de tipo \<str\>, representa el lugar de procedencia del estudiante
* **\<regroupeme>**: de tipo \<str\>, representa la agrupación por estudios de los estudiante
* **\<formacion>**: de tipo \<str\>, representa el tipo de formación que ha tenido dicho estudiante
* **\<secteur>**: de tipo \<str\>, representa el sector del que proviene el estudiante
* **\<establecimiento_privado>**: de tipo \<bool\>, representa si el estudiante está en un establecimiento privado o no
* **\<num_gen>**: de tipo \<int\>, representa cuántos géneros hay en la institución de la que proviene el estudiante
* **\<sexo_estudiante>**: de tipo \<str\>, representa el sexo de dicho estudiante
* **\<effectif>**: de tipo \<float\>, representa la eficacia de la institución
* **\<diffusable>**: de tipo \<bool\>, representa si es distribuible o no.
* **\<geo_id>**: de tipo \<str\>, representa el id de la región del estudiante


## Tipos implementados

Para trabajar con los datos del dataset se ha definido la siguiente tupla con nombre:

`estudiante = namedtuple('Estudiante', 'rentree, fecha_nacimiento, nivel_geo, nombre_geo, regroupement, formacion, secteur, establecimiento_privado, num_gen ,sexo_estudiante, effectif, diffusable, geo_id	') `

en la que los tipos de cada uno de los campos son los siguientes:

`estudiante =(int, date, str,str, str, str, str, bool, int, str, float, bool, str)`


## Funciones implementadas
En este proyecto se han implementado las siguientes funciones, que están clasificadas según los bloques y tipos de funciones que se requieren en cada una de las entregas.
El módulo principal es el módulo modulo1.py, así que aquí es donde se hará referencia a cada uno de los bloques de las entregas.

### \<modulo 1\>

 * **lee_fichero(fichero)**: lee los datos del fichero csv y devuelve una lista de tuplas de tipo Info con los datos del fichero. Para implementar esta función se han definido las siguientes funciones auxiliares:
    * **parsea_bool(cad)**: Función para convertir de cadena a booleano.
    * **parsea_fecha(cad)**: Función para convertir de cadena a fecha.   

### \<test modulo 1\>

En el módulo de pruebas se han definido las siguientes funciones de pruebas, cada una de las cuales se usa para probar la función con que tiene el mismo nombre (pero sin comenzar por `test_` del módulo `modulo1`. Por ejemplo, la función `test_lee_fichero` prueba la función `lee_fichero`.
