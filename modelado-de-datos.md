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

### Lenguaje DAX

Es un lenguaje de expresión donde utiliza fórmulas analíticas y funciones operativas que permiten el cálculo de uno o más valores, creado para manipular un modelo de datos tabular y está basado en Excel; de ahí su similitud en términos de estructura de formulación. Podemos encontrar este lenguaje en Power BI, SAS Tabular y Excel en el plugin Power Query

**¿Por qué DAX?**

* Relaciones de Navegación
* Cálculo de Dimensiones
* Gestión de las Dimensiones del Tiempo (Time Intelligence)

**¿Qué podemos crear?**

* **Columnas calculadas**: permite que los métodos conecten tablas con múltiples columnas clave y creen nuevas columnas en el modelo de datos
* **Tablas Calculadas**: crea una tabla derivada de otra tabla
* **Medidas**: admite inteligencia de tiempo y crea cálculos dinámicos, que es el más utilizado en Power BI

**Convenciones del idioma (formato general)**

* 'nombre de tabla' \[nombre de columna] Ejemplo: 'productos de mesa'\[Precio]

El nombre de la tabla se puede omitir cuando se usa en columnas calculadas, pero no se recomienda hacerlo.

### Usar CALCULATE

### Inteligencia del tiempo

Se refiere a las técnicas, herramientas y metodologías que nos permiten analizar de forma exhaustiva nuestras mediciones a través del concepto de “tiempo”, es decir, está presente en todas las soluciones de inteligencia de negocios como punto de partida para explorar la información:

* A partir de analizar la evolución de nuestras medidas en el tiempo, se utiliza una nueva dimensión (tablas) Fechas y calendario de forma continua sin que falte un solo día entre las fechas, esto funciona en nuestro modelo
* Supervisar el crecimiento o disminución en detalle
* Hacer proyecciones

### Iteradores X
