
# Siniestros Viales - Buenos Aires

## Introducción

Para el proyecto se simula el papel de un Analista de Datos dentro del equipo de analistas de una empresa consultora. El objetivo es brindar información valiosa a partir de los datasets proporcionados para el Observatorio de Movilidad y Seguridad Vial (OMSV), un centro de estudios vinculado a la Secretaría de Transporte del Gobierno de la Ciudad Autónoma de Buenos Aires (CABA).

Esta información contribuye a las autoridades locales tomar medidas para reducir la cantidad de víctimas fatales en los siniestros de tráfico ocurridos en CABA. 

Siendo así, en este proyecto se presentará un conjunto de información en un dashboard interactivo, que fue extraída, limpiada, cargada y analizada a profundiad para poder tomar decisiones a partir de ellos. 

## Desarrollo 

Los siniestros viales se presentan en Buenos Aires con sus diferentes factores influyentes como en la mayoría de países; así que estos siniestros ponen día a día la vida de la población en peligro. 

La población de CABA es de 3,120,612 habitantes en una superficie de 200 km², lo que resulta en una densidad de aproximadamente 15,150 personas por km²; así que representa una gran proporción de población.

Para este proyecto se trabajó con la Bases de Víctimas Fatales en Siniestros Viales la cual está en formato de Excel y contiene dos pestañas de datos:

**HECHOS**: contiene por fila la información por siniestro ocurrido con su id único y las demás variables de tiempo, espacio, hora, cantidad de participantes, víctimas, etc. 

**VICTIMAS**: contiene por fila la información asociada a cada víctima de los hechos y las variables edad, sexo y modo de desplazamiento asociadas a cada víctima, y está vinculada a la tabla de HECHOS por el id del siniestro.

## ETL Y EDA 

Se realizó la Extracción, Transformación y Carga (ETL) de datos tanto para la tabla de "HECHOS" como para la tabla "VÍCTIMAS". 

Se realizó también el proceso de Análisis Exploratorio de Datos, el cual es una fase fundamental en un proyecto de análisis de datos, pues nos ayuda a conocer a profundidad los datos de los cuales extraeremos la información crucial para desarrollar la toma de decisiones.

Estos procesos están documentados en la carpeta de este repositorio divididas en dos partes, una para el ETL principalmente y la segunda parte para el EDA como tal; se encuentran como EDA_1 y EDA_2.

## Análisis de Datos

En la fase del análisis se hizo enfoque en las variables más importantes como lo son el tiempo, espacio, cantidad de víctimas mortales, cantidad de hechos, clasificados por sexo, rol y tipo de calle.

Primero se hizo un análisis temporal para comprender la distribución de homicidios en diferentes escalas de tiempo (por año, mes, día de la semana y hora). La distribución anual de víctimas mortales mestá alrededor del 60% para los primeros tres años del conjunto de datos, seguida con una notoria disminución en el año 2020 debido a la cuarentena por la pandemia del COVID-19. Ese mismo año se genera un pico en diciembre pero esta tendencia no es constante en los siguientes años. 

También se observó que al rededor del 70% de las víctimas fatales ocurrieron de lunes a viernes, en las horas cercanadas a la salida y entrada de jornadas laborales. 

En la distribución por semana no se ve diferencias muy altas entre los días, ya que la cantidad de víctimas en sábados y domingos muy parecida; esto se puede relacionar también con las jornadas laborales, pues en los fines de semana hay más flexibilidad horaria en el tránsito.

Al analizar el género que prebalece en la distribución de los datos, se puede evidenciar que la gran mayoría de afectados son los del genero masculino con alrededor del  76%. También observando la edad, prevalecen edades entre 25 y 40 años. Casi el 50% de las víctimas eran conductores, siendo al rededor del 75% en moto y cerca del 20% en auto. Otro dato importante es que de los conductores de moto, la gran mayoría son hombres estando cerca del 90%.

Por último se encontró que Las víctimas edades mayores están más concentradas cuando son pasajeros, mientras que las víctimas más jóvenes suelen estar relacionadas más frecuentemente en las categorías de motos, autos y los otros vehículos. 

Esta información es relevante para identificar patrones de comportamiento en la población que lleven lugar a diseñar estrategias para mitigar estos hechos. Estos análisis puede proporcionar información muy crucial para la protección de la vida en la población de CABA, ayudando a identificar los factores de riesgo más importantes.

## KPI's

En esta etapa se plantearon tres indicadores con el objetivo de reducir el número de víctimas fatales en los siniestros viales.

 * Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior

La Tasa de Homicidios en los siniestros viales se define como el número de víctimas mortales en accidentes de tránsito por cada 100,000 habitantes en una región geográfica durante un periodo específico, en este caso, se consideran 6 meses. 

Así que se calcularía dividiendo el número de homicidios sobre la población total y luego se multiplica por 100,000.

El dato de la población total se extrajo mediante webscrapping con la herramienta de Power BI.

Para el primer semestre del año 2021, la Tasa de Homicidios fue de 1.75, indicando que durante los primeros 6 meses del año hubo aproximadamente 1.75 homicidios en accidentes de tránsito por cada 100,000 habitantes. El objetivo establecido es reducir esta tasa para el siguiente semestre de 2021 en un 10%, alcanzando así la cifra de 1.56. En este KPI para este periodo, se obtiene que la Tasa de Homicidios que fue de 1.35, lo que significa que se logró cumplir objetivo propuesto para el segundo semestre de 2021.

* Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior.

Se hace importante proponer la analizar la cantidad de accidentes mortales que involucran a las víctimas mortales por moto, ya que son en gran proporción los más afectados en los siniestros. Para ello, se define la cantidad de accidentes mortales por motos como el número absoluto de accidentes fatales en los cuales estuvieron involucradas víctimas que se desplazaban en moto durante un periodo temporal específico. 

En este contexto, considerando el año 2021 como el año actual y el año 2020 como el año anterior, se inició calculando la Cantidad de Accidentes Mortales de Motociclistas para el año 2020. Al calcular la Cantidad de Accidentes Mortales de Motociclistas para el año 2021, se obtuvo un valor de -70.08, lo que indica un aumento del 70.37% en la cantidad de muertes de conductores de motocicletas en comparación con el año 2020. Este resulado negativo deja ver que no se cumplió con el objetivo propuesto, así que resultaría pertinente estudiar otras aristas para mejorar este indicador.

* Reducir en un 10% la tasa de homicidios en los cruces en el último año, en CABA, respecto al año anterior:

En el EDA se pudo ver que al rededor del 75% de las víctimas mortales transitaban por cruces al momento del hecho. Así se considera pertinente calcular la Tasa de homicidios en Cruces. Este indicador se calcula de la siguiete manera: dividiendo el numero de accidentes mortales en cruces entre el total de la población, para luego ser multiplicado por 100,000.

Primero se calculó la Tasa de homicidios en cruces para el año 2020, la cual resultó en 1.92. A partir de esto se determinó el objetivo para el siguiente año, que es la reducción del 10%. Finalmente, al calcular la Tasa de homicidios en cruces para el año 2021, dio un resultado de 2.11, lo que quiere decir que no se cumplió el objetivo, ya que aumentó con respecto al año anterior. 

## Herramientas utilizadas

En este proyecto se utilizó pandas en jupyter notebooks para hacer los procesos de ETL y EDA, y posteriormente Power BI para realizar el dashboard con la información para ser visualizada y analizada. 

## Conclusiones 

Para los datos proporcionados, se pudo ver que para los años 2016 y 2021, se registraron 717 víctimas fatales en accidentes de tránsito. Al rededor del 70% de estos hechos ocurrieron durante la semana. Diciembre destacó como el mes con el mayor número de fallecimientos en el periodo analizado.

La gran mayoría de las victimas fueron del género masculino con cerca del 77%, la mayoría entre edades de los 25 y 40 años. En relación al tipo de participante, más del 40% eran motociclistas. El 62% de los homicidios tuvieron como escenario las avenidas de CABA, con el 75% de ellos ocurriendo en cruces.

Para el segundo semestre del año 2021, se cumplió con el objetivo de reducir la tasa de homicidios en siniestros viales. Sin embargo, los objetivos de disminuir la cantidad de accidentes mortales de motociclistas y en cruces para el año 2021 respecto del año 2020 no se cumplieron.

## Recomendaciones

Para esto se recomeinda a las autoridades pertinentes tener un control más efectivo de este tipo de siniestros, tomando decisiones basadas en este tipo de análisis, informando a la población haciendo campañas de detección tempranda de factores de riesgo y fomentando las medidas de prevención. 
