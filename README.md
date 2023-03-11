# Big-Data-Architecture

# Arquitectura de predictor de índoces bursátiles

# Brainstorm
* Flujo predictivo de índices bursátiles
  - Comparación de tendencias
  - Buscar APIs, Scripting
* Ventas
  - Comparación de precios en el tiempo
  - Picos de ventas en el año
  - Mas baratos

# Diseño del DAaaS

## Definición la estrategia del DAaaS
La idea es conseguir un servicio de predicción que ayude a la hora de tomar decisiones en estrategias de operaciones bursátiles con índices. Puede ser beneficioso para ahorrar tiempo en el análisis de qué transacciones realizar.
* Predicción de histórico de precios de índices.

## Arquitectura DAaaS
Listado de componentes:
* [RaspBerry]Crawling/Scraping de https://www.bloomberg.com/europe
* [Cloud Storage] Base de datos en SQL
* [Dataproc] Hadoop procesado de datos
* [Cloud Vertex AI] Modelo de series temporales con TensorFlow
* API de consulta de valores

## DAaaS Operating Model Design and Rollout
1. RaspBerry lanza todos los viernes a las 18:
  * El scapping sobre la web de bloomber
  * Conecta con storage
  * Lanza los jobs del dataproc de hadoop
  * Reentrenar el modelo de Vertex AI
  * Recoge los resultados en el storage
2. Los datos en el storage se procesan en el dataproc de hadoop y son cargados de nuevo en el storage
3. Los datos resultantes se reflejan en una interfaz de web

## Desarrollo de la plataforma DAaaS
La aplicación tendrá en cuenta el histórico de los índices bursátiles más significativos y hará una predicción de cara a los próximos cinco días que reflejará en un interfaz de web.

# Link a Diagrama
https://drive.google.com/file/d/1zBK-0PL1-QlC-3n4rxeJs3zaRI4BQrFX/view?usp=sharing
