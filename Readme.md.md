# Homicidios por siniestros viales en la Ciudad Autónoma de Buenos Aires, Argentina

<h1 align="center"> Proyecto N ° 2 Henry </h1>


<p align="center">
  <img src="BD/Logo.png" alt="STEAM" width="400">
</p>

## Introducción

 En este proyecto simulamos que en nuestro rol de Data Analyst nos han contratado para realizar nuestro primer proyecto de análisis exploratorio de datos. El cliente, el Observatorio  de la Movilidad y Seguridad Vial (en adelante, OMSV), perteneciente al Gobierno de Buenos Aires, a partir de la entrega de bases de datos de víctimas e información de los sinisestros viales de la ciudad Autónoma de Buenos Aires (en adelante, CABA), nos pide recoger información que les permita a las autoridades locales tomar medidas para disminuir la cantidad de victimas fatales.

En Argentina, cada año mueren cerca de 4.000 personas en siniestros viales. Si bien se han hecho esfuerzos en pos de disminuir la cantidad de accidentes con resultado de muerte, esta sigue siendo la principal causa de muertes violentas en Argentina. El Ministerio de Seguridad de la Nación revela que entre 2018 y 2022 se registraron casi 20.000 muertes que equivalen a 11 personas por día que resultaron víctimas fatales por accidentes de tránsito. Los expertos en la materia indican que en Argentina es dos o tres veces más alta la probabilidad de que una persona muera en un siniestro vial que en un hecho de inseguridad delictiva.


## Objetivo:

El objetivo de este proyecto de data analyst es generar información relevante que les permita a las autoridades locales tomar medidas para disminuir la cantidad de victimas fatales en siniestros viales. 

El OMSV define siniestro vial como cualquier hecho de tránsito con implicación de al menos un vehículo  en movimiento,  que tenga lugar en la vía pública o en una vía privada  a la que la población tenga derecho de acceso y que tenga como consecuencia al menos una persona herida o muerta. 
Los siniestros viales, también conocidos como accidentes de tráfico o accidentes de tránsito, son eventos que involucran vehículos en las vías públicas y que pueden tener diversas causas, como colisiones entre automóviles, motocicletas, bicicletas o peatones, atropellos, choques con objetos fijos o caídas de vehículos. Estos incidentes pueden tener consecuencias que van desde daños materiales hasta lesiones graves o fatales para los involucrados. Una víctima, por lo tanto, es cualquier persona herida o muerta como resultado de un siniestro vial.

Como contexto, la Ciudad Autónoma de Buenos Aires posee 15 comunas, cuya población, según censo realizado en el año 2022, corresponde a 3,121,707 de habitantes. 

## Fuente de Datos

Para este proyecto se trabajó con la base de datos **Buenos Aires Data** que se encuentra en formato de Excel y contiene dos pestañas de datos:

* **HECHOS**: contiene un id único por siniestro vial, y la información concerniente como víctimas asociadas al siniestro vial, la fecha y hora del hecho, lugar, ubicación geográfica, involucrados en el hecho e identifica qué rol cumplía la víctima al momento del hecho.  
* **VICTIMAS**: contiene una fila por cada víctima de los hechos, describiendo características de ésta, como la edad, sexo, rol, fecha de fallecimiento.


## Tecnologías utilizadas

Para la elaboración de este proyecto se utilizó lenguaje python, con sus librerías Pandas, Numpy, Mathplotlib y Seaborn, como las principales para los procesos de extracción, transformación y carga de los datos, como así también para el análisis exploratorio de los datos. 
Para la construcción de un dashboard interactivo se utiliza Power BI.


## Fases del Proyecto

Las etapas de este proyecto se resumen a continuación: 

- Extracción, Transformación y Carga (ETL): Proceso de carga de datos y tratamiento preliminar para su adecuado consumo. 

- Análisis Exploratorio de Datos (EDA): Investigar las relaciones que hay entre las variables del dataset, y detectar patrones. 

- Elaboración del Dashboard en Power BI junto con la ellaboración de los tres KPI.

## ETL (Extracción, Transformación y Carga)

La etapa de extracción de datos y su transformación fue la etapa más desafiante y que tomó mayor tiempo de trabajo, debido a que los datos no venían listos para empezar a procesarlos. Las tareas realizadas consisteron en identificar la forma correcta para leer los archivos, desanidado de columnas, análisis de las bases de datos para su preproceso, eliminación de columnas innecesarias para nuestro análisis, ajuste de tipos de datos, tratamiento y análisis preliminar de datos faltantes y nulos y limpieza. 


## EDA (Análisis Exploratorio de Datos)
En esta etapa se realizó un análisis profundo de las dos bases de datos con las que trabajamos con la finalidad de identificar información relevante de los datasets. Esta tarea implicó primero,realizar tratamiento de elementos nulos, duplicados, elementos faltantes, identificando por ejemplo, que existían patrones claros de tipos de datos faltantes del tipo MNAR, dado que existía unarelación entre el lugar del hecho y si existía el dato altura o cruce relacionados. Dado lo sensible de la información tratada, se decidió no eliminar filas para preservar la cantidad de víctimas originales. Se decidió en la mayor parte de los casos ajustar los tipos de datos para luego dejar vacíos los campos para que no tengamos problemas al llevar el conjunto de datos a Power BI. Una vez desarrolladas estas estrategias, se realizaron representaciones gráficas con el objetivo de obtener una comprensión más profunda y visual de la naturaleza de los datos y de las características del negocio. Este proceso permitió identificar ciertos patrones, tendencias y particularidades esenciales, brindando así una base sólida para la siguiente etapa de desarrollo del proyecto.


## Análisis de los Datos
 
- El 97% de los accidentes viales tienen como resultado una víctima fatal o lesionada. Tres es el número máximo de víctimas. 
- El 20.6% de los accidentes viales sucedieron en 2016. En términos globales, el mes en que suceden más accidentes viales es el mes de diciembre, con 78 casos que corresponden a un 11% del total. En tanto el día más frecuente del  en que suceden accidentes viales es el día 20 de cada mes, en tanto el nombre del día de la semana que más siniestros posee, es el día Lunes.
- La fecha en que ocurrieron más siniestros viales fue el día 18 de diciembre de 2018, con tres sucesos. 
- A las 7 de la mañana es el horario más frecuente en siniestros viales, representa un 5% de los accidentes listados en la base de datos, con 41 casos documentados.
- El mes de diciembre donde más han ocurrido más hechos viales, más que doblando la cantidad de hechos viales que el mes más cercano, el mes de agosto.
- Si tomamos franjas horarias de 6 horas cada una, la mayor cantidad de siniestros viales ocurren en el horario que va entre las 06:00 de la mañana y hasta las 12:00, cuando las personas se trasladan a la ciudad y existe una mayor concentración de personas y vehículos. Aquí podemos ver que el día Lunes es el más acontecido de hechos viales.
- Al crear una nueva columna identificando los días en Laborales y No Laborales, el gráfico nos muestra que una gran cantidad de personas son víctimas de siniestros viales en los días laborales.
- Al hacer un gráfico de palabras, la avenida más frecuente es la Avenida Gral Paz. También son frecuentes las avenidas que contienen las palabras  Moreno, Rivadavia, libertador. 
- El 61% de los accidentes listados ocurren en avenidas, que corresponden a 429 casos, 352 siniestros viales corresponden a zonas en donde existen encrucijadas, que corresponden al 50.6% del total de siniestros viales.
- El 77% de las víctimas fatales fueron de sexo masculino, de los cuales casi el 50% tenía entre 25 y 44 años de edad. En relación al tipo de usuario, el 42% fueron motociclistas. El 62% de los homicidios ocurrió en algún punto de las avenidas de CABA, siendo el 82% de ellos en un cruce de la autopista con alguna otra calle. En ese sentido, el 75% de los hechos ocurrieron en cruces de calles.
- Los participantes en siniestros viales que más se repiten están asociados a la dupla peatón-pasajeros. También son importantes los siniestros viales ocurridos entre moto-auto, moto-cargas y peatón-auto. 
- La mayor parte de las víctimas corresponden a personas conduciendo motos y peatones


## KPI

En función de lo analizado en el punto anterior, se plantearon dos objetivos en relación a la disminución de la cantidad de víctimas fatales de los siniestros viales, desde los cuales se proponen dos indicadores de rendimiento clave o KPI.

* *Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior*

    Las tasas de mortalidad relacionadas con siniestros viales suelen ser un indicador crítico de la seguridad vial en una región. Se define como Tasa de homicidios en siniestros viales al número de víctimas fatales en accidentes de tránsito por cada 100,000 habitantes en un área geográfica durante un período de tiempo específico, en este caso se toman 6 meses. Su fórmula es:

    $\text{Tasa de homicidios en siniestros viales} = \frac{\text{Número de homicidios en siniestros viales}}{\text{Población total}}·100.000$

    Como *Población Total* se calculó la población para el año 2021 a partir de los censos poblacionales del año 2010 y 2022.

    Al calcular la tasa de siniestros viales, durante los primeros 6 meses del año 2021, hubo aproximadamente 1.77 víctimas en accidentes de tránsito por cada 100,000 habitantes. El objetivo a cumplir reducido en un 10% será **1.60**. Se calcula el KPI para este período y se obtiene que la *Tasa de homicidios en siniestros viales* fue de **1.35**, lo que significa que para el segundo semestre de 2021 se cumple con el objetivo propuesto.

* *Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior*

   Se define a la **Cantidad de accidentes mortales de motociclistas** como el número absoluto de accidentes fatales en los que estuvieron involucradas víctimas que viajaban en moto en un determinado periodo temporal. La fórmula para medir la evolución de los accidentes mortales con víctimas en moto es:

    $\text{Cantidad de accidentes mortales de motociclistas} = -\frac{\text{Víctimas moto año anterior - Víctimas moto año actual}}{\text{Víctimas moto año anterior}}·100$

    Donde:
    - $\text{Víctimas moto año anterior}$: Número de accidentes mortales con víctimas en moto en el año 2020
    - $\text{Víctimas moto año actual}$: Número de accidentes mortales con víctimas en moto en el año 2021

    En primer lugar, se calculó la *Cantidad de accidentes mortales de motociclistas* para el año 2020, el cual resultó en 29, de esta manera el objetivo a cumplir es de 22 (es decir, la reducción del 7% de la cantidad de accidentes para 2020). El calcular la *Cantidad de accidentes mortales de motociclistas* para el año 2021 resultó de **59%** lo que significa que aumentó un 59% la cantidad de muertes de conductores de motociclistas respecto del 2020 (56 motociclistas)


* *Reducir en un 10% la tasa de víctimas en siniestros viales de peatones del último año, en CABA, en comparación con la tasa de víctimas peatones de siniestros viales del último año comparable 2019.

     - $\text{Cantidad de accidentes mortales de víctimas peatones} = -\frac{\text{Víctimas peatones año anterior - Víctimas peatones año actual}}{\text{Víctimas peatones año anterior}}·100$

Se calculó la *Cantidad de accidentes mortales de peatones* para el año 2019, el cual resultó en 35, de esta manera el objetivo a cumplir es de 31 (es decir, la reducción del 10% de la cantidad de accidentes de peatones para 2021). El calcular la *Cantidad de accidentes mortales de peatones* para el año 2021 resultó de 6% lo que significa que no se cumplió el indicador (sólo se redujo a 33 peatones).  

    

## Conclusiones y recomendaciones

Entre los años 2016 a 2021 se registraron 717 víctimas fatales en accidentes de tránsito. El 70% de las víctimas se registraron durante la semana. En cuanto a la franja horaria, el 12% de los hechos ocurre entre las 6 y las 8 de la mañana, pero durante los fines de semana. Diciembre es el mes que resulta con el máximo de fallecimientos en el período analizado.

El 77% de las víctimas fatales fueron de sexo masculino, de los cuales casi el 50% tenía entre 25 y 44 años de edad. En relación al tipo de usuario, el 42% fueron motociclistas. El 62% de los homicidios ocurrió en algún punto de las avenidas de CABA, siendo el 82% de ellos en un cruce de la autopista con alguna otra calle. En ese sentido, el 75% de los hechos ocurrieron en cruces de calles.

El 61% de los accidentes listados ocurren en avenidas, que corresponden a 429 casos, 352 siniestros viales corresponden a zonas en donde existen encrucijadas, que corresponden al 50.6% del total de siniestros viales.El 

En función de lo anterior, se hacen las siguientes recomendaciones:

* Focalizar recursos para mejorar la infraestructura en zonas en donde existen encrucijadas en las que esté involucrada una avenida. 
* Aumentar los controles vehiculares y de velocidad en horarios de 6 a 9 de la mañana diariamente, dado que una gran cantidad de accidentes ocurre en esta franja. Especial atención merece el día Lunes.
* Controlar las medidas de seguridad con las que se desplazan los motociclistas, y aumentar los controles de este tipo de vehículos.
* Disminuir la velocidad a la que pueden transitar los vehículos de carga en avenidas y calles, ya que son causante de una gran cantidad de accidentes de peatones y motociclistas.
* Dirigir las campañas de seguridad hacia el sexo masculino, especialmente en cuanto a conducción en moto.
