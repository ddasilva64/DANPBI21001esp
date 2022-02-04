# Conceptos básicos

### Business Intelligence con Power BI

**Business Intelligence**: Es la capacidad de transformar datos en información y a su vez, convertir esta información en conocimiento, para agilizar el tiempo en cuanto a la toma de decisiones

![Pirámide del conocimiento](https://i.imgur.com/cn72R3p.jpg)

**Flujo BI**

* **ETL**
  * **Extracción** de datos de fuentes de datos
  * **Transformación** de datos (consolidación de fuentes, limpieza y transformación de datos)
  * **Carga** de datos en el almacén de datos de Power BI
  * Herramientas: PowerCenter, SQL Server Integration Services (SSIS), Oracle Data Integrator (ODI), Power Query (en Power BI)

![ETL en Power BI](https://i.imgur.com/OONplWt.png)

* **Modelado**
  * Relaciones
  * KPI´s
  * Optimización (para responder a todas las preguntas de negocio)
  * Herramientas: Erwin Data Modeler, PowerDesigner (herramienta de modelado SAP), Power Pivot (en Power BI)
    * **Data Warehouse**: Suele servir como la base de datos central de una empresa o, en otras palabras, la base de datos donde se almacenan todos los datos útiles de una organización
    * **Data Mart**: Almacena conjuntos de datos específicos y concisos utilizados para el análisis de un departamento o línea de negocio específicos, como el departamento de ventas

![Modelado en Power BI](https://i.imgur.com/g6tBXTY.png)

* **Informe (puesta en funcionamiento)**:
  * Visualización de datos
  * Informes
  * Dashboards
  * Storytelling
  * Herramientas: Power BI, Qlik, Tableau, etc.
    * **Dashboard**: Un dashboard es una herramienta empresarial usada para ayudar a rastrear, analizar y mostrar datos, generalmente para obtener una visión más profunda del estado general de la organización, de un departamento o incluso de un proceso específico. _**En Power BI, corresponde al informe**_
    * **Balanced scorecard**: Es una herramienta para monitorear las decisiones estratégicas que toma la empresa con base en indicadores previamente establecidos y que normalmente deben permear por lo menos cuatro aspectos – financiero, clientes, procesos internos y aprendizaje y crecimiento -. _**En Power BI, corresponde al dashboard**_

**Power BI**: Es una **solución de Business Intelligence** **integral** y completa que brinda una vista detallada de los datos más críticos dentro de una organización

**Suite empresarial**

* **Power BI Desktop**: Herramienta de escritorio **orientada al entorno de desarrollo**, que nos permite conectarnos a diversas fuentes de datos y generar informes
* **Power BI Service**: Servicio en la nube que nos permite establecer **todo el entorno colaborativo**
* **Power BI Mobile**: Aplicación móvil que nos permite **ver e interactuar con un reporte desde cualquier dispositivo móvil (Android y Apple)**

**Componentes de Power BI**

* **Power Query ETL**: Extracción, transformación y carga de datos
* **Modelado Power Pivot (DAX)**: Responde todas las preguntas empresariales

### Arquitectura de Power BI

**Arquitectura de Power BI gratis**

* Incluye 1 GB de almacenamiento
* No es posible colaborar con otros usuarios simultáneamente (informes, dashboards y dataset), pero es posible publicar en sitios web (sin seguridad)
* El intercambio de informes solo es posible en modo público (sin seguridad)

**Arquitectura Power BI PRO**

* Incluye 10 GB de almacenamiento
* Se puede compartir con usuarios internos siempre que también tengan una licencia PRO
* Gateway opcional
* Puede actualizar datos hasta 8 veces al día
* El creador (en Desktop) y el usuario (en Service) deben tener, cada uno, una licencia

**Arquitectura Power BI PREMIUM**

* Incluye 100 TB de almacenamiento
* Se puede compartir con usuarios internos sin necesidad de que tengan Power BI PRO
* Mayor escalabilidad y rendimiento que la capacidad compartida en el servicio Power BI
* Puede actualizar datos hasta 48 veces al día
* El creador (en Desktop) y el usuario (en Service) deben tener, cada uno, una licencia

**Aviso**: Nada de esto se puede iniciar con una cuenta de correo electrónico personal, sino solo con una cuenta de correo electrónico empresarial o educativa

![Arquitectura Power BI](https://i.imgur.com/x4S1XfN.png)

### Tipos de conexión

**Tipos de conexiones**

Power BI nos permite conectarnos a una amplia variedad de fuentes de datos, desde archivos de Excel, bases de datos de SQL Server, sitios web, etc.

**Tipos de conexión**

* **Live Connection o dinámica**: lea desde SSAS o desde un dataset del servicio Power BI, en otras palabras, los datos se almacenan fuera de Power BI (como en Direct Query)
* **Direct Query**: No se copian los datos, ya que cada interacción hace una consulta a la base de datos
* **Importación**: Los datos se copian localmente dentro del modelo de Power BI (este es el modelo más común)
* **Modelos Compuestos**: Combinan tecnologías de Importación y Direct Query. También permite usar múltiples datasets

|                                             | **Live Connection**                                                                               | **Direct Query**                                                                                              | **Importar**                                                                            | **Compuesto**                                                                             |
| :-----------------------------------------: | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
|                                             | para soluciones empresariales                                                                     | informe completo                                                                                              | informe completo                                                                        | combina DQ e Importación                                                                  |
|                                             | no hay datos almacenados en la memoria                                                            | no hay datos almacenados en la memoria                                                                        | no hay datos almacenados en la memoria                                                  | mayores volúmenes de datos                                                                |
|                                             | informe completo                                                                                  | sin transformación de datos                                                                                   | transformación completa de datos                                                        | sin servicios de análisis                                                                 |
|                                             | sin transformación de datos                                                                       | modelado de datos limitado                                                                                    | modelado completo de datos                                                              |                                                                                           |
|                                             | sin modelado de datos                                                                             | bajo rendimiento                                                                                              | de alto rendimiento                                                                     |                                                                                           |
|                                             | de alto rendimiento                                                                               | datos almacenados en la fuente                                                                                | datos almacenados en Power BI                                                           |                                                                                           |
|                                             | datos almacenados en la fuente                                                                    | consultas enviadas a la fuente                                                                                | consultas no enviadas a la fuente                                                       |                                                                                           |
|                                             | consultas enviadas a la fuente                                                                    | no se requiere actualización                                                                                  | actualización requerida                                                                 |                                                                                           |
|                                             | no se requiere actualización                                                                      |                                                                                                               | admite preguntas y respuestas e información rápida                                      |                                                                                           |
|               fuente de datos               | ![Conectividad en vivo de fuente de datos](https://i.imgur.com/6p3iPRs.png)                       | ![Consulta directa de fuente de datos](https://i.imgur.com/SuWtLZ5.png)                                       | <p></p><p><img src="https://i.imgur.com/FNIrr9R.png" alt="Data source Import"></p>      | ![Compuesto de origen de datos](https://i.imgur.com/nJalAvm.png)                          |
| componente almacenado en la fuente de datos | ![Componente almacenado en la fuente de datos Live Connectivity](https://i.imgur.com/uOq6szv.png) | ![Componente almacenado en el origen de datos Compuesto](https://i.imgur.com/oMSfzis.png)                     |                                                                                         | ![Componente almacenado en el origen de datos Compuesto](https://i.imgur.com/oMSfzis.png) |
|      componente almacenado en Power BI      | ![Componente almacenado en Power BI Live Connectivity](https://i.imgur.com/BJWgiCM.png)           | <p></p><p><img src="https://i.imgur.com/nxKlSPc.png" alt="Component stored within Power BI Direct Query"></p> | ![Componente almacenado en la importación de Power BI](https://i.imgur.com/RxA0ZLe.png) | ![Componente almacenado en la importación de Power BI](https://i.imgur.com/RxA0ZLe.png)   |

**Avisos**:

* Con _**conectividad de Importación**_, el archivo PBIX y el dataset son alojados en la memoria, **es el más rápido de todos los tipos de conectividad**, pero el dataset de Power BI debe programarse para actualizarse, y siempre debemos tener en cuenta el uso de la memoria. Con **licencias PRO**, el dataset de Power BI **no puede exceder 1 GB**, sin embargo, con **Power BI PREMIUM** esto puede alcanzar niveles de **400 GB**

![Importar iconos](https://i.imgur.com/ojeJtvh.png)
