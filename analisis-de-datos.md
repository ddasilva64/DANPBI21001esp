# Análisis de datos

### Análisis de datos con Power BI

![Ejemplo 1 de analítica de datos](https://i.imgur.com/0SdDUWR.png)

**Detalles**:

1. Dimensiones
   1. Eje X: Total ventas
   2. Eje Y: Cantidad ventas
   3. Eje de reproducción: Mes
   4. Leyenda (comparación): Vendedor
2. Analítica (lupa). Esto añade el cuadrante
   1. Línea promedio 1: Cantidad ventas
   2. Línea promedio 2: Total ventas

Con el botón de reproducción (esquina inferior izquierda), reproduce la evolución de cada mes del año seleccionado

![Ejemplo 2 de analítica de datos](https://i.imgur.com/nNyFaZH.png)

**Detalles gráfico 1**

1. Dimensiones
2. Eje: Mes y año
3. Valores: Total ventas

**Detalles gráfico 2**

1. Dimensiones
2. Eje: Mes y año
3. Valores: Total ventas
4. Previsión
   1. Duración de la previsión: 12 puntos
   2. Ignora el último: 7 puntos
   3. Intervalo de confianza: 95%
   4. Estilo banda de confianza: Rellena
   5. Transparencia: 80%

### Análisis de datos con Python/R

Power BI ofrece la posibilidad de integrar herramientas de BI, con lenguajes como Python o R

Para hacer un ejemplo de script en R, descargar e instalar R y R Studio. Las url estás disponibles en la sección  Lecturas o herramientas recomendadas

![Obtenemos los datos del ejemplo de un fichero CSV](https://i.imgur.com/3SvvvNo.png)



![Cargamos el fichero deseado](https://i.imgur.com/uKPzu5t.png)

![Vamos a especificar datos y a crear una tabla (almacén) de medidas](https://i.imgur.com/6aO2Vbh.png)

![Tabla de medidas](https://i.imgur.com/gG51DZF.png)

![Creamos nuestra primera medida](https://i.imgur.com/jwkDF6t.png)

Para comprobar la medida creamos una tabla y vemos que funciona OK

![Tabla de comprobación de la medida](https://i.imgur.com/MhW7Rsx.png)

![No resumir, para ver detalle de la edad](https://i.imgur.com/JyOolet.png)

![La edad en detalle con la medida calculada](https://i.imgur.com/MfFb7H4.png)

Ahora llevaremos estas dos variables a un gráfico hecho con R

![Copiamos el script R que tenemos en un TXT](https://i.imgur.com/fjemhYv.png)

![Habilitamos el script que vamos a crear](https://i.imgur.com/TF4PGrt.png)

![Ahora llevamos las variables edad y suma de líneas (no resumido)](https://i.imgur.com/mcut0Rh.png)

![Pegamos script y pulsamos play (esquina superior derecha)](https://i.imgur.com/Qdl4bUc.png)

