# Preparación de datos

### ¿Qué es ETL?

* **Extract (extraer)**: Desde prácticamente cualquier fuente de datos, desde archivos planos hasta complejos, bases de datos o servicios cloud&#x20;
* **Transform (transformar)**: Permite modificar o enriquecer la información extraída sin modificar la fuente&#x20;
* **Load(cargar)**: Una vez realizada la transformación, se encarga de cargar el resultado en el modelo de datos

### Transformar datos con Power Query

**Power Query**

Es una tecnología de conexión de datos que permite detectar, conectar, combinar y refinar distintas fuentes de datos para satisfacer las necesidades de análisis

**¿Qué hace Power Query?**

* **Extrae**: Desde prácticamente cualquier fuente de datos
* **Transforma**: Fusiona, combina, limpia o enriquece los datos
* **Carga**: Los datos para su posterior análisis en Power BI

**Puntos a considerar**

* El **objetivo** del **Power Query** es **obtener datos** de una variedad de fuentes **y prepararlos para su posterior análisis**
* El **objetivo** de esta herramienta **no es analizar los datos**
* **Magia**: Es la **colección de pasos** que se realizan **para llegar a un resultado**, además **permite retroceder o avanzar estos, sin modificar el origen de datos**. Es similar al proceso que realiza un macro en Excel

![Power Query](https://i.imgur.com/zIjUUnw.jpg)

### Transformaciones

**Transformar**: **Dar forma a los datos**

**Transformaciones comunes**:

* Cambiar el nombre de las columnas o las tablas
* Cambiar el tipo de dato (convertir texto en números, por ejemplo)
* Quitar filas
* Configurar la primera fila como encabezado
* Agregar columnas
* Dividir columnas
* Reemplazar valores
* Filtrar datos

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

**Combinaciones comunes**:

* Anexar consultas
* Combinar consultas
* Combinar binarios
