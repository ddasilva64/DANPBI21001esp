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
