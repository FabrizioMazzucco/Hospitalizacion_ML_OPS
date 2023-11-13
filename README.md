<h1 align=center> **Hospitalizacion ML OPS** </h1> 

<p align=center><img src=https://img.freepik.com/vector-gratis/gente-caminando-sentada-edificio-hospital-exterior-cristal-clinica-ciudad-ilustracion-vector-plano-ayuda-medica-emergencia-arquitectura-concepto-salud_74855-10130.jpg><p>

  **Introducción:**
  En este proyecto hemos sido contratados para una consultora de ciencia de datos donde el cliente desea saber las características más importantes que tienen los pacientes de cierto tipo de enfermedad que terminan en hospitalización. 
  Fue definido como caso aquel paciente que fue sometido a biopsia prostática y que en un periodo máximo de 30 días posteriores al procedimiento presentó fiebre, infección urinaria o sepsis; requiriendo manejo médico ambulatorio u hospitalizado para la resolución de la complicación y como control al paciente que fue sometido a biopsia prostática y que no presentó complicaciones infecciosas en el período de 30 días posteriores al procedimiento. Dado que tienen en su base de datos algunos datos referentes a los pacientes y resultados de exámenes diagnósticos, de pacientes hospitalizados y no hospitalizados, nos han entregado esta información. 
  Nuestro objetivo es encontrar las características más importantes de los pacientes que terminan hospitalizados y crear un modelo de clasificación para predecir la hospitalización de futuros pacientes.

  **Pasos del proyecto:**
1. *ETL*

Realizamos un proceso de ETL para normalizar nuestros datos donde extrajimos datos del excel proporcionado por el cliente y lo trabajamos para que nos quede en formato csv. El excel proporcionado se llama Hospitalización.xlsx y el csv se llama Datos_Limpios.csv.
En esta normalización pasamos todas las variables a numéricas otorgándole índices que se encuentran en el diccionario de datos para asi poder buscar un patron con una matriz de correlación en el EDA. Además también reemplazamos los valores vacíos y algunos outliers por nulos.

2. *EDA*

Primero para el EDA hicimos un recuento de los valores nulos y posteriormente un mapa de calor de estos valores nulos asi identificando que las últimas filas eran solo de valores nulos. Realizamos un describe para ver outliers y como se conformaban nuestras tablas numéricas.
Finalmente realizamos una matriz de correlación con la columna de hospitalización si o no, para ver los datos que nos pueden servir para nuestro modelo. Puntualmente vemos que las únicas columnas que tienen una correlación con la hospitalización son: 'NUMERO DE DIAS POST BIOPSIA EN QUE SE PRESENTA LA COMPLICACIÓN INFECCIOSA', 'FIEBRE', 'ITU', 'TIPO DE CULTIVO', 'AGENTE AISLADO','PATRON DE RESISTENCIA' y 'DIAS HOSPITALIZACION MQ'que son las columnas que usaremos en nuestro modelo.

3. *Modelo de clasificación*

Primero creamos nuestro modelo de Regresión Logística. Luego separamos nuestros datos en entrenamiento y testeo. Entrenamos nuestro modelo y testeamos para analizar su funcionamiento. 
Vemos que el modelo tiene una precisión de 0,98. 
Creamos una matriz de confusión para ver la cantidad de test acertados y vemos que: 152 se clasificaron como positivos siendo positivos, 0 se clasificaron como negativos siendo positivos, 3 se clasificaron como positivos siendo negativos y 7 se clasificaron como negativos siendo negativos.
Finalmente creamos el siguiente reporte:

                  precision    recall  f1-score   support

         0.0       0.98      1.00      0.99       152
         1.0       1.00      0.70      0.82        10

    accuracy                           0.98       162
    
   macro avg       0.99      0.85      0.91       162
   
weighted avg       0.98      0.98      0.98       162


0.0 = No hospitalizado y 1.0 = Si hospitalizado. 

Precision dice cual es el porcentaje de acertividad para cada etiqueta. 

Recall representa la proporción de muestras de esa clase que fueron correctamente identificadas por el modelo.

F1-Score es la media armónica entre precision y recall.

Support es la cantidad de muestras de cada etiqueta.

Accuracy muestra la precision del modelo en general.

Macro avg es el promedio no ponderado de las métricas.

Weighted avg es el promedio ponderado de las métricas.

*Mi linkedin*: www.linkedin.com/in/fabrizio-mazzucco-403b0825a
