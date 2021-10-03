# Proyecto del Primer Cuatrimestre Fundamentos de Programación (Curso  \<XX\>/\<YY\>)

Aquí debes añadir la descripción del dataset


## Estructura de las carpetas del proyecto

* **/src**: Contiene los diferentes módulos de Python que conforman el proyecto.
  * **\<modulo1.py\>**: Describe aquí el módulo principal.
  * **\<modulo1_test.py\>**: Describe aquí el módulo de pruebas.
  * **\<modulo2.py\>**: Añade descripciones para el resto de módulos que pueda tener tu proyecto. Por ejemplo, sería conveniente tener un módulo separado con funciones genéricas para dibujar gráficas y/o otro con funciones genéricas de conversión de tipos. 
* **/data**: Contiene el dataset o datasets del proyecto
    * **\<dataset1.csv\>**: Añade una descripción genérica del dataset.
    * **\<dataset2.csv\>**: Añade una descripción del resto de datasets que puedas tener.
    
## Estructura del *dataset*

Aquí debes describir la estructura del dataset explicando qué representan los datos que contiene y la descripción de cada una de las columnas.

El dataset está compuesto por \<N\> columnas, con la siguiente descripción:

* **\<columna 1>**: de tipo \<tipo\>, representa....
* **\<columna 2>**: de tipo \<tipo\>, representa....
....

## Funciones implementadas
Añade aquí descripciones genéricas de las funciones, que luego debes acompañar con comentarios de tipo documentación en el código 

### \<modulo1\>

* **cadena_vacia**: Comprueba si una cadena está vacía
* **parsear_booleano**: Convierte el objeto a un booleano usandoel ``built-in`` bool.
* **parsear_categorias**: Crea una tupla a partir de una cadena dividida por comas
* **parsear_fecha**: Convierte una cadena a un objeto ``datetime``
* **parsear_ean**: Si un producto no tiene código, genera un código aleatorio para él. Si el EAN pasado es válido, elimina espacios vacíos y comas.
* **parsear_numero_fabricante**: Genera un código para cada fabricante si el fabricante no tiene código.
* **leer_datos**. Recorre las filas del CSV y llama a las funciones de conversión de datos para cada una de las columnas del CSV
* **agrupar_datos_categoria**: Devuelve una tupla con múltiples 'namedtuple' del tipo 'Category'
* **obtener_datos_productos**: Devuelve una tupla con múltiples 'namedtuple' del tipo 'Product'.
* **agrupar_datos_fabricantes**: Devuelve una tupla con múltiples 'namedtuple' del tipo 'Manufacturer'
* **obtener_datos_reviews**: Devuelve una tupla con múltiples 'namedtuple' del tipo 'BasicReview'
* **procesar_datos_agregados**: Llama a todas las funciones que filtran los datos con estructura 'agregada' (ver documentación del módulo para más información) 
    y agrupa los resultados en un diccionario. Esta función almacena los resultados en memoria para acelerar futuros accesos al dataset.
* **procesar_datos_basicos**: Llama a todas las funciones que filtran los datos con estructura 'básica' (ver documentación del módulo para más información) 
    y agrupa los resultados en una tupla. Esta función almacena los resultados en memoria para acelerar futuros accesos al dataset.
* **get_datos_agregados**: Devuelve el dataset agregado y procesado en un diccionario.
* **get_datos_basicos**: Devuelve información básica del dataset en una tupla con 'namedtuple' del tipo 'FullReview'.
* **get_raw_dataset**:  Devuelve una tupla con varios diccionarios del dataset original, uno para cada línea del dataset, solamente con los datos parseados
    en los correspondientes tipos de Python, sin relación alguna entre ellos

### Funciones de filtrado (módulo ``productos``)

* **obtener_nombre_categorias**: Dado una tupla con múltiples 'namedtuple' del tipo 'Category', obtener los nombres
* **aleatorizar_datos**: Dado una tupla o lista, la aleatoriza
* **agrupar_codigos_fabricante**: Dada una tupla con múltiples tuplas del tipo 'Manufacturer', obtener un diccionario cuya clave sea el código del fabricante
    y el valor la tupla del tipo 'Manufacturer' que corresponda con ese 'manufacturerNumber'.
* **agrupar_productos_fabricante**: Dada una tupla con múltiples tuplas del tipo 'Product', obtener un diccionario cuya clave sea el código del fabricante
    y el valor la tupla del tipo 'Product' que corresponda con ese 'manufacturerNumber'.
* **agrupar_productos_codigo**: Dada una tupla con múltiples tuplas del tipo 'Product', obtener un diccionario cuya clave sea el código del producto
    y el valor la tupla del tipo 'Product' que corresponda con ese 'ean'.
* **is_None**: Dado un parámetro, comprueba si es de tipo 'None' o no.
* **agrupar_productos_reviews**: Dada una tupla con múltiples tuplas del tipo 'FullReview', obtener un diccionario cuya clave sea el código del producto
    y el valor las reseñas que pertenecen a dicho producto.
* **agrupar_productos_categoria_valoraciones**: Dada una tupla con múltiples tuplas del tipo 'FullReview', y una categoría,
    obtener un diccionario cuya clave sea el código del producto y el valor las reseñas
    de los productos que pertenecen a una categoría.
* **productos_del_fabricante**: Dado un 'namedtuple' del tipo 'Manufacturer' y varias 'namedtuple' del tipo 'Product',
    devuelve una tupla con varias 'namedtuple' del tipo 'Product' que pertenezcan al fabricante.
* **numero_productos_fabricante**: Dado un 'namedtuple' del tipo 'Manufacturer' y varias 'namedtuple' del tipo 'Product',
    devolver el número de productos que pertenecen a un fabricante.
* **media_reseñas**: Dado una tupla con múltiples 'namedtuple' del tipo 'Reviews',
    devolver la media de las valoraciones.
* **mejor_y_peor_producto_categoria**: Dada una categoría por su tupla de tipo 'Category', devolver el nombre y la valoración de los mejores y los peores productos, respectivamente.
* **producto_con_mas_reseñas**: Devuelve el 'namedtuple' del tipo 'Product' del producto con más reseñas.
* **agrupar_productos_de_categorias**: Devuelve un diccionario cuya clave son los nombres de las categorías y los valores son tuplas con múltiples tuplas 'namedtuple' del tipo 'Product'.
* **contar_productos_de_categorias**: Devuelve un diccionario cuya clave son los nombres de las categorías y los valores es un entero que indica el número
    de productos que posee esa categoría.
* **producto_con_mas_nota_en_reviews**: Devuelve una 'namedtuple' del tipo 'Product' para el producto cuya suma de las valoraciones es la más alta del
    dataset completo.
* **porcentaje_productos_recomendados**: Devuelve el porcentaje de reseñas que recomiendan el producto
* **top_productos_fabricantes**: Dadas tuplas con 'namedtuple' de tipo 'Product', 'Manufaturer' y 'FullReview', devuelve un diccionario
    cuya clave es el nombre del fabricante y el valor es una lista ordenada de mayor a menor con
    los productos más exitosos de dicho fabricante, basándose en la suma de las valoraciones dadas

### Funciones gráficas (módulo ``graficas``)

* **grafica_numero_reviews_por_mes**: Dado un entero (que representa un año del calendario gregoriano) y una tupla con varios 'namedtuple' de tipo 'Review',
    muestra una gráfica en la que aparece la evolución del número de reseñas realizadas durante los meses
    (representados en formato númerico) de ese año.
