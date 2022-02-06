# Preparación de datos

### ¿Qué es ETL?

* **Extract (extraer)**: Desde prácticamente cualquier fuente de datos, desde archivos planos hasta complejos, bases de datos o servicios cloud&#x20;
* **Transform (transformar)**: Permite modificar o enriquecer la información extraída sin modificar la fuente&#x20;
* **Load(cargar)**: Una vez realizada la transformación, se encarga de cargar el resultado en el modelo de datos

### Transformar datos con Power Query

**Consulta de poder**

Es una tecnología de conexión de datos que nos permite descubrir, conectar, combinar y refinar fuentes de datos dispares para satisfacer nuestras necesidades de análisis

**¿Qué hace Power Query?**

* **Extracto**: Desde prácticamente cualquier fuente de datos
* **Transformar**: Desde fusionar, combinar, limpiar o enriquecer los datos
* **Subir**: Los datos para su posterior análisis en Power BI

**Puntos a considerar**

* El propósito de Power Query es obtener datos de una variedad de fuentes y prepararlos para un análisis posterior
* El propósito de esta herramienta no es analizar los datos
* Magia: Colección de pasos realizados para llegar a un resultado, también permite retroceder o avanzar sin modificar la fuente de datos. Similar al proceso que realiza una macro en Excel

![Consulta de energía](https://i.imgur.com/zIjUUnw.jpg)

### Transformaciones

### Combinaciones

**Adjuntar**

* Permite unir dos o más mesas
* Se recomienda que ambos tengan la misma estructura, de no ser así el sistema agrega los campos de todos los demás con valores nulos al conjunto final
* Es similar a una operación estándar de SQL **UNION**
* Los resultados pueden ser una nueva consulta o agregarse a un paso existente

**Combinar**

* La funcionalidad de combinar consultas. Nos permite tomar dos tablas y cruzarlas usando una columna común
* Suele usarse para complementar información en una tabla
* Es el equivalente más cercano a la función **JOIN** del estándar SQL

**Combinar binarios**

* Esta funcionalidad nos permite extraer las tablas de los archivos a través de un proceso automatizado
* Suele usarse a través del conector de carpetas
* Es especialmente útil cuando la fuente de información está demasiado fragmentada para la operación de agregar
