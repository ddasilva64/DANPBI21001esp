# Modelado de datos

### Modelado de datos

**El Flujo de BI consta de**

* ETL
* Modelado de datos
* Visualización de datos

ETL se maneja con Power Query, mientras que el modelado de datos se realiza con Power Pivot

**Modelado de datos**: Análisis complejos entre varias tablas conectadas por un campo en común

**Relaciones entre tablas**

* **Primary keys (claves primarias)**: Se utilizan para definir la clave principal de la tabla. Las columnas que tienen este perfil no pueden contener valores nulos ni puede haber valores duplicados. Es decir, debe contener registros únicos
* **Foreign keys (claves foráneas)**: Una clave foránea es una columna o conjunto de columnas, que contiene valor que hace referencia a una fila de otra tabla

### Relaciones y filtros

El modelo de datos se puede hacer de dos maneras; uno que es el modelo estrella y el otro, llamado copo de nieve o algo parecido a una cascada

**Para ello es necesario conocer dos aspectos claves**

* **Hechos**: Responde a la pregunta "¿Qué quiero obtener o buscar?"
* **Dimensiones**: Responde al nivel o clasificación que me interesa, que puede ser tiempo o tipo de dato

![Hecho y dimensión](https://i.imgur.com/gTFNcvu.png)

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
