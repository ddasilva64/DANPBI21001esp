# Modelado de datos

### Modelado de datos

**El Flujo de BI consta de**

* ETL
* Modelado de datos
* Visualización de datos

ETL se maneja con Power Query, mientras que el modelado de datos se realiza con Power Pivot

**Modelado de datos**: Análisis complejos entre varias tablas conectadas por un campo en común

### Relaciones y filtros

**Relaciones entre tablas**

* **Primary keys (claves primarias)**: Se utilizan para definir la clave principal de la tabla. Las columnas que tienen este perfil no pueden contener valores nulos ni puede haber valores duplicados. Es decir, debe contener registros únicos
* **Foreign keys (claves foráneas)**: Una clave foránea es una columna o conjunto de columnas, que contiene valor que hace referencia a una fila de otra tabla

**Tipos de relaciones**:

* **1:1 (de 1 a 1)**: Ambas tablas se conectan por sus claves primarias. Actúa como una extensión de estas
* **1:n (de 1 a varios)**: Ocurre cuando se conecta una clave primaria con la clave foránea de otra tabla
* **m:n (de varios a varios)**: Ocurre cuando ambas tablas se relacionan por sus claves foráneas (ninguna de las columnas tiene valores únicos). Evitar este tipo de relaciones

**Conflictos a resolver**:

1. **Relaciones m:n**: Mediante concatenación de capos clave o mediante tablas asociativas
2. **Relaciones inactivas**:&#x20;
   1. Borrarlas porque no son necesarias&#x20;
   2. Pueden ser relaciones no resueltas m:n&#x20;
   3. Muy interesante la herramienta Model Documenter

**Diseño de modelos de datos**:

* Existen distintos tipos (estrella, copo de nieve, etc.)
* En **Power BI** nos enfocamos en el modelo de **esquema de estrella**, que es el que resulta más eficiente

**Componentes del modelo en estrella**:

* **Tablas de hechos**: También conocidas como **tablas transaccionales** o (fact en inglés). Responden a la pregunta **¿Qué quiero obtener o buscar?**
* **Tablas dimensión**: También conocidas como **tablas de búsqueda**. Responden al nivel o **clasificación que nos interesa**, que puede ser **tiempo o tipo de dato**

![Hecho y dimensión](https://i.imgur.com/gTFNcvu.png)

**Motor del modelo de datos**

* Su nombre es **Vertipaq**
* Se encarga de todas las operaciones de análisis de datos (DAX)
* Utiliza tecnología in-memory que provee un elevado almacenamiento y rendimiento en consulta de datos
* Permite ciclos de desarrollo corto

### Solucionar problemas de modelado

1. **Diseño de Modelo de Datos**: El Modelo de Esquema en Estrella es el más utilizado en Power Bi porque está compuesto por una tabla de dimensiones (Búsqueda) y una tabla de Hechos (transaccional) donde la integración de ambas sobresale el uno a -muchas relaciones y por lo tanto, evita la redundancia de datos
2. **Data Model Engine**: VERTIPAQ se encarga de las operaciones de análisis de datos (DAX) y utiliza tecnología (in-memory) que proporciona un alto rendimiento para almacenar y consultar datos

**Necesidad del modelado de datos**:

* Si se carga un único dashboard, se tendrá un mal rendimiento para volúmenes de datos grandes y con redundancia de datos
* Modelar adecuadamente evita estos problemas

### Lenguaje DAX

**DAX (Data Analysis Expression)**:

* Lenguaje de expresiones analíticas de Power BI: **Utiliza fórmulas analíticas y funciones operativas** que permiten el cálculo de uno o más valores
* Creado **para manipular un modelo de datos tabular**
* Está basado en Excel; de ahí su similitud en términos de estructura de formulación. Podemos encontrar este lenguaje en Power BI, SAS Tabular y Excel en el plugin Power Query

**¿Por qué DAX?**:

* Relaciones de Navegación
* Pensado para llegar a mayor cantidad de usuarios
* Cálculo dinámico de dimensiones, por ejemplo **Time Intelligence**
* Menor curva de aprendizaje para los analistas de datos. Aprovecha el conocimiento existente de trabajar con fórmulas Excel
  * Por ejemplo: = IF (Ventas > 0, “GANÓ”, “PERDIÓ”)

**¿Qué podemos crear con DAX?**

* **Columnas calculadas**: Permite que los métodos creen nuevas columnas en el modelo de datos. Además permite que se conecten tablas con múltiples columnas clave en una nueva columna
* **Tablas Calculadas**: Crea una tabla derivada de otra tabla. Por ejemplo, este sistema nos permite crear tablas sin duplicados de un campo de otra tabla, para romper relaciones m:n
* **Medidas**: Admite inteligencia de tiempo y crea cálculos dinámicos, que es lo más utilizado en Power BI

**Convenciones del lenguaje (formato general)**:

* 'nombre de tabla' \[nombre de columna] Ejemplo: 'Tabla productos'\[Precio]
* El nombre de la tabla se puede omitir cuando se usa en columnas calculadas, pero no se recomienda hacerlo.

### Usar CALCULATE

* Se trata de una función que solo tiene dos parámetros. Nos permite realizar una acción llamada “modificador de contexto de filtro”.
* Permite crear un contexto de fila dentro de nuestros cálculos

### Inteligencia del tiempo

* Por Inteligencia de tiempo, hacemos referencia a las técnicas, herramientas y metodologías que nos permiten analizar nuestras medidas minuciosamente a través del tiempo
* El concepto de “tiempo” está presente en todas las soluciones de inteligencia de negocios. Sirve como punto de partida para explotar la información

**Tabla de fechas**

* Para poder utilizar este tipo de análisis dentro de Power BI, necesitaremos primero de crear una nueva dimensión
* A estas tablas se les conoce como tablas de fechas o tabla calendario, y funciona como una nueva dimensión para nuestro modelo
* Una tabla de fechas se identifica por tener todas las fechas existentes en nuestro modelo (o al menos las necesarias para el análisis) de manera continua. Es decir, sin que falte ni un solo día entre las fechas
* Permite supervisar el crecimiento o disminución en detalle
* Permite hacer proyecciones

### Iteradores X

**Funciones iterativas**

* Este tipo de funciones son especiales dentro de DAX y permiten crear operaciones a nivel de fila y calcular un resultado a partir de ellas
* Las funciones iterativas también son conocidas como funciones X, por su terminación dentro de su nombre en DAX
* Algunas de estas funciones son: SUMX, AVERAGEX, MAXX, MINX, STDEVX.S, PERCENTILEX.EXC y CONCATENATEX

**Simulaciones de SUM y SUMX en Excel**:



![Tabla de productos](https://i.imgur.com/xWCFLYp.png)

1. Necesitamos calcular la suma del importe de todos los productos. ¿Qué función debemos utilizar?. ¿Podemos usar indistintamente una u otra?

**SUM**:

* Agrega todos los números en una columna
* El parámetro es la columna que contiene los números a sumar. La función acepta valores numéricos o de fecha y devuelve como resultado un valor decimal. Las filas pueden contener valores en blanco. Los valores de la columna no se pueden filtrar.
* Suma de Importe := SUM(\[Importe])

**SUMX**:

* Devuelve la suma de una expresión evaluada por cada fila de una tabla
* El parámetro es la tabla que contiene los valores para los cuales se evaluará la expresión. Puede ser el nombre de una tabla o una expresión que devuelve una tabla.El parámetro es una columna que contiene los números que desea sumar o una expresión que se evalúa como una columna.Solo se cuentan los números de la columna. Se omiten los espacios en blanco, los valores lógicos y el texto.
* Suma de Importe 1 := SUMX(Tabla1; \[Importe])
* Podemos observar que las dos funciones devuelven el mismo resultado.Lo que diferencia a ambas funciones es la forma en que realizan el calculo:La función SUMX es un iterador, recorrerá cada fila evaluando una expresión mientras que la función SUM() sumará directamente los valores de la columna.Para este caso la función SUM() es la recomendada

![Resultado de la simulación 1](https://i.imgur.com/W3gMtjR.png)

2\. Calcular la suma del Importe del modelo anterior solo para la categoría vino blanco

**SUM**:

* La función SUM() no nos permite filtrar las filas de la tabla sobre la que queremos realizar el cálculo y debemos combinarla con la función CALCULATE(). Importe de vino blanco := CALCULATE(SUM(\[Importe]) ; Filter(Tabla1;\[Categoría]=”vino blanco”)) **SUMX**:
* En cambio, la función SUMX () sí que nos lo permite: Importe frutas := SUMX(Filter(Tabla1; \[Categoría]=”vino blanco”); \[Importe])
* En este caso pudiera usarse cualquiera de las dos, si se aplica de la manera mencionada

3\. Calcular las ventas totales. En este modelo, a diferencia del anterior, no tenemos una columna con el importe de cada fila, pero podemos calcularlo usando las columnas Precio venta y Cantidad en la expresión:\[Precio venta]\*\[Cantidad]

![Resultado de la simulación 2](https://i.imgur.com/YD5FtQt.png)

**SUM**:

* Sintaxis: SUM(\[Precio venta]\*\[Cantidad])
* La función SUM() nos devuelve un error porque solo admite como parámetro una columna

**SUMX**:

* En cambio, la función SUMX () sí que nos lo permite porque admite una expresión además de una columna:
* Sintaxis: SUMX(Tabla2;\[Precio venta]\*\[Cantidad])
* En este caso la función SUMX() es la recomendada
