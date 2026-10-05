# Θ Proyecto Theta | Análisis de Viajes Compartidos en Chicago

## Descripción

Zuber es una nueva empresa de viajes compartidos que busca expandir su participación en el mercado de transporte urbano de Chicago. Para comprender mejor la dinámica de la movilidad en la ciudad, se analizaron datos históricos de compañías de taxis, barrios de destino y condiciones climáticas.

Este proyecto combina consultas SQL y análisis exploratorio en Python para identificar patrones de demanda, reconocer las zonas con mayor actividad y evaluar el impacto de las condiciones meteorológicas sobre la duración de los viajes.

## Objetivos

- Analizar la participación de las principales compañías de taxis de Chicago.
- Identificar los barrios con mayor número de viajes finalizados.
- Comprender los patrones de movilidad urbana de la ciudad.
- Visualizar los resultados mediante gráficos exploratorios.
- Evaluar el impacto del clima sobre la duración de los viajes.
- Aplicar una prueba estadística para validar una hipótesis de negocio.
- Generar conclusiones basadas en datos que apoyen la toma de decisiones de Zuber.

## Herramientas utilizadas

- SQL
- PostgreSQL
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- BeautifulSoup
- Requests
- Jupyter Notebook

## Datos utilizados

### project_sql_result_01.csv

Información sobre compañías de taxis.

- `company_name`
- `trips_amount`

### project_sql_result_04.csv

Información sobre barrios donde finalizaron los viajes.

- `dropoff_location_name`
- `average_trips`

### project_sql_result_07.csv

Información sobre viajes entre Loop y el Aeropuerto Internacional O'Hare.

- `start_ts`
- `weather_conditions`
- `duration_seconds`

## Metodología

### 1. Extracción de datos mediante SQL

Se realizaron consultas SQL sobre una base de datos relacional compuesta por las tablas:

- `trips`
- `cabs`
- `neighborhoods`
- `weather_records`

Las consultas permitieron:

- Identificar las compañías con mayor cantidad de viajes.
- Determinar los barrios con más finalizaciones de recorridos.
- Integrar información meteorológica con los registros de viajes.
- Preparar los datos necesarios para la prueba de hipótesis.

### 2. Preparación de datos

- Importación de archivos CSV.
- Revisión de tipos de datos.
- Verificación de consistencia.
- Exploración inicial de variables.

### 3. Análisis exploratorio

Se analizaron:

- Empresas de taxis con mayor actividad.
- Barrios con mayor número de finalizaciones de viajes.
- Patrones de movilidad urbana en Chicago.

### 4. Prueba de hipótesis

Se evaluó la siguiente hipótesis:

> La duración promedio de los viajes desde el Loop hasta el Aeropuerto Internacional O'Hare cambia durante los sábados lluviosos.

Para ello se compararon las duraciones de los viajes realizados bajo condiciones climáticas favorables y desfavorables mediante una prueba estadística de comparación de medias.

## Principales hallazgos

### Empresas de taxis

El análisis muestra que **Flash Cab** fue la empresa con la mayor cantidad de viajes realizados durante el período estudiado.

A partir de Flash Cab se observa una disminución gradual en el número de viajes realizados por las demás compañías. La reducción no es especialmente pronunciada entre los principales competidores, pero se vuelve más evidente a partir de **Taxi Affiliation Services** y continúa descendiendo hasta llegar a **Blue Ribbon Taxi Association Inc.**, que presenta uno de los volúmenes de viajes más bajos entre las empresas analizadas.

Estos resultados sugieren que el mercado de taxis en Chicago presenta una concentración importante en unas pocas compañías líderes.

### Barrios con mayor cantidad de finalizaciones

Los resultados muestran que **Loop** es el barrio con la mayor cantidad de viajes finalizados, superando los **10.000 viajes** durante el período analizado.

En segundo lugar se encuentra **River North**, también con una actividad considerablemente elevada.

La importancia de Loop puede explicarse por su papel como centro económico, comercial y turístico de Chicago. En esta zona se encuentran puntos de referencia destacados como:

- Millennium Park
- Chicago Cultural Center
- Art Institute of Chicago
- Willis Tower
- Chicago Theatre

La concentración de oficinas, comercios, atracciones turísticas y actividades económicas contribuye a explicar el elevado volumen de viajes que finalizan en este barrio.

### Patrones de movilidad urbana

Los resultados muestran que la demanda de transporte no se distribuye de manera uniforme dentro de la ciudad.

Determinados barrios concentran una proporción significativa de los recorridos, lo que proporciona información valiosa para comprender los patrones de movilidad urbana y las zonas de mayor actividad dentro de Chicago.

## Visualizaciones desarrolladas

### 1. Empresas de taxis y número de viajes

Gráfico de barras utilizado para comparar la cantidad de viajes realizados por las principales compañías de taxis de Chicago durante el 15 y 16 de noviembre de 2017.

Esta visualización permitió identificar a Flash Cab como la empresa líder en volumen de viajes y observar la distribución de la actividad entre los principales competidores.

### 2. Top 10 barrios por número de finalizaciones

Gráfico de barras utilizado para identificar los diez barrios con mayor promedio de viajes finalizados durante noviembre de 2017.

La visualización permitió determinar que Loop y River North concentran la mayor actividad de finalización de recorridos, destacándose como zonas clave dentro de la movilidad urbana de Chicago.

## Prueba de hipótesis

### Hipótesis nula (H₀)

La duración promedio de los viajes desde el Loop hasta el Aeropuerto Internacional O'Hare es la misma durante los sábados lluviosos y los sábados con condiciones climáticas favorables.

### Hipótesis alternativa (H₁)

La duración promedio de los viajes desde el Loop hasta el Aeropuerto Internacional O'Hare es diferente durante los sábados lluviosos y los sábados con condiciones climáticas favorables.

### Nivel de significancia

```text
α = 0.05
```

### Resultado

```text
p-value = 6.517970327099473e-12
```

Equivalente a:

```text
0.000000000006517970327099473
```

Dado que:

```text
p-value < α
```

se rechaza la hipótesis nula.

### Interpretación

Existe evidencia estadística suficiente para concluir que las condiciones climáticas influyen significativamente en la duración de los viajes entre el Loop y el Aeropuerto Internacional O'Hare.

Los resultados sugieren que los viajes realizados durante días lluviosos presentan comportamientos distintos respecto a aquellos realizados bajo condiciones climáticas favorables.

Una posible explicación es que la lluvia genere:

- Mayor congestión vehicular.
- Reducción de la velocidad promedio de circulación.
- Incremento de la demanda de transporte.
- Condiciones de conducción más complejas.

Estos efectos pueden ser aún más notorios en una zona de alta actividad y tráfico como Loop.

## Archivos principales

- `theta_chicago_rideshare_analysis.ipynb`
- `project_sql_result_01.csv`
- `project_sql_result_04.csv`
- `project_sql_result_07.csv`

## Conclusión

El análisis permitió identificar patrones relevantes del mercado de transporte urbano en Chicago y comprender mejor el comportamiento de los pasajeros.

Los resultados muestran que **Flash Cab** es la compañía con mayor volumen de viajes dentro de la muestra analizada. A partir de esta empresa se observa una disminución gradual en la cantidad de recorridos realizados por las demás compañías, evidenciando una concentración importante del mercado en unos pocos actores.

Respecto a los destinos de los viajes, **Loop** se posiciona como el barrio con mayor número de finalizaciones, superando los 10.000 viajes. Este resultado es consistente con la importancia económica, comercial y turística de la zona, considerada el corazón de la actividad urbana de Chicago. **River North** ocupa la segunda posición, confirmando la relevancia de las áreas centrales dentro de la demanda de transporte.

Finalmente, la prueba estadística confirmó que las condiciones climáticas tienen un impacto significativo sobre la duración de los viajes entre el Loop y el Aeropuerto Internacional O'Hare. El valor p obtenido fue considerablemente inferior al nivel de significancia establecido, proporcionando evidencia suficiente para rechazar la hipótesis nula.

En conjunto, los resultados sugieren que tanto la ubicación geográfica como los factores meteorológicos desempeñan un papel importante en la dinámica del transporte urbano. Esta información puede ayudar a Zuber a comprender mejor la demanda, anticipar cambios operativos y fortalecer su estrategia competitiva dentro del mercado de movilidad compartida en Chicago.
