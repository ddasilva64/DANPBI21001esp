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

### Tipos de datos

* A diferencia de otros programas como Excel, donde los tipos de datos son muy flexibles, en Power BI necesitamos definirlos bien, antes de poder utilizarlos
* Como en las bases de datos relacionales, **cada columna debe tener bien definido su tipo para evitar errores**
* Clases:
  * **Entero**: Representa un valor entero de 64 bits (**8 bytes**). Dado que es un entero, no tiene dígitos a la derecha de la posición decimal. **Permite 19 dígitos**; números enteros positivos o negativos entre – 9.223.372.036.854.775.807 $$– (2^{63}+1)$$y 9.223.372.036.854.775.806 $$(2^{63} – 2)$$. Puede representar la precisión más grande posible de los distintos tipos de datos numéricos. Al igual que con el tipo Número decimal fijo, el tipo Número entero **puede ser útil en casos en los que necesitemos controlar el redondeo**
  * **Decimal**: Representa un número de punto flotante de 64 bits (**8 bytes**). Es el tipo de número más común. Aunque se ha diseñado para controlar los números con valores fraccionarios, también controla números enteros. El tipo Número decimal puede controlar valores negativos de $$– 1,79E^{+308}$$ a $$– 2,23E ^{308}$$, y valores positivos de $$– 2,23E^{–308}$$ a $$1,79E^{+308}$$. Por ejemplo, los números como 34, 34.01 y 34.000367063 son números decimales válidos. **La precisión más grande que se puede representar en un tipo de número decimal es de 15 dígitos**. El separador decimal puede colocarse en cualquier parte del número. El tipo de número decimal se corresponde con la forma en la que Excel almacena sus números. Tengamos en cuenta que un número de punto flotante binario no puede representar todos los números dentro de su intervalo admitido con una precisión del 100 %. Por lo tanto, pueden producirse pequeñas diferencias en la precisión al representar determinados números decimales
  * **Decimal fijo**: También conocido como **tipo de moneda**, este tipo de datos **tiene una ubicación fija para el separador decimal**. **El separador decimal siempre tiene cuatro dígitos a la derecha y permite 19 dígitos de importancia**. El valor más grande que puede representar es 922.337.203.685.477,5807 (positivo o negativo). A diferencia del número decimal, el tipo número decimal fijo siempre es preciso y, por tanto, es **útil en casos en los que la imprecisión de la notación de punto flotante podría introducir errores**
  * **Texto**: **Cadena** de datos de carácter **Unicode**. Pueden ser cadenas, números o fechas representadas en un formato de texto. La longitud máxima de cadena es de 268.435.456 caracteres Unicode (donde cada carácter Unicode es de 2 bytes) o 536.870.912 bytes
  * **Fecha/tiempo**: **Representa un valor de fecha y hora**. El valor de fecha y hora se almacenan como un tipo de número decimal, por lo que puede convertir de uno a otro. La parte de hora de una fecha se almacena como una fracción en múltiplos enteros de 1/300 segundos (3,33 ms). Se admiten las fechas entre los años 1900 y 9999
  * **Tiempo**: **Representa solo la hora (sin fecha)**. Cuando se convierte en el modelo, el valor de hora es el mismo que el valor de fecha y hora sin dígitos a la izquierda de la posición decimal
  * **Fecha/hora/zona horaria**: **Representa una fecha y hora UTC con un desplazamiento de zona horaria**. Se convierte en fecha y hora cuando se carga en el modelo
  * **Duración**: **Representa un período de tiempo**, que se convierte en un tipo de número decimal cuando se carga en el modelo. Como tipo de número decimal, se puede agregar o restar de un campo Fecha y hora con los resultados correctos. Dado que es un tipo de número decimal, puede usarlo fácilmente en visualizaciones que muestran magnitud
  * **Booleano**: Valor booleano de True o False
  * **Binario**: El tipo de datos binario se puede usar para representar **cualquier otro dato con un formato binario**
  * **Cualquiera**: El tipo de datos Any es el estado dado a una columna que **no tiene una definición de tipo de datos explícita**. Any es el tipo de datos que clasifica todos los valores. Se recomienda definir siempre explícitamente los tipos de datos de columna para las consultas de orígenes no estructurados y evitar tener columnas con el tipo de datos Any como salida de la consulta

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

**Combinar**: Conectarse a **dos o más orígenes de datos**, **darles la forma** necesaria **y consolidarlos** después en una consulta útil

**Combinaciones comunes**:

* Anexar consultas
* Combinar consultas
* Combinar binarios

**Anexar**

* Permite unir dos o más tablas
* Se recomienda que ambas tengan la misma estructura, si no, el sistema añade al conjunto final los campos no coincidentes con valores nulos
* Es similar a una operación **UNION** del estándar SQL
* Los resultados pueden ser una nueva consulta o agregarse a un paso existente

**Combinar**

* La funcionalidad de combinar consultas. Nos permite tomar dos tablas y cruzarlas usando una columna común
* Suele usarse para complementar información en una tabla
* Es el equivalente más cercano a la función **JOIN** del estándar SQL

**Combinar binarios**

* Esta funcionalidad nos permite extraer las tablas de los archivos a través de un proceso automatizado
* Suele usarse a través del conector de carpetas
* Es especialmente útil cuando la fuente de información está demasiado fragmentada para la operación de agregar
