# Análisis Comportamiento de Clientes para ConnectaTel
🎯 Objetivo del proyecto

Este proyecto evalúa el comportamiento de los clientes de ConnectaTel, una empresa de telecomunicaciones en Latinoamérica, utilizando datos registrados hasta el año 2024.

El análisis busca:

Construir un perfil estadístico de los clientes.
Detectar comportamientos atípicos (outliers) en el uso de los servicios.
Crear segmentos de clientes por edad y nivel de uso.
Identificar patrones de consumo que permitan diseñar estrategias de retención.
Generar recomendaciones accionables sobre los planes actuales y posibles mejoras u oportunidades comerciales (ej. upsell).
## 📊 Datasets utilizados

El análisis combina tres fuentes de datos ubicadas en /datasets/:

Archivo	Contenido
plans.csv	Información de los planes actuales: precio mensual, minutos y GB incluidos, y costos por unidad extra.
users_latam.csv	Información de los clientes: edad, ciudad, fecha de registro, plan contratado y fecha de cancelación (churn).
usage.csv	Detalle del uso real de los servicios: llamadas y mensajes por usuario.

## 🧩 Etapas del análisis

El notebook está organizado en 8 pasos secuenciales:

**1. Cargar y explorar**
Importación de librerías (pandas, seaborn, matplotlib), carga de los tres datasets y revisión inicial de su estructura (.shape, .info(), .head()).

**2. Identificación de problemas de calidad de datos**
Conteo y proporción de valores nulos, detección de valores sentinel (ej. -999 en edad, "?" en ciudad) y revisión/estandarización de fechas fuera de rango.

**3.Limpieza básica de datos**
Corrección de sentinels (imputación de edad por mediana, ciudad nula reemplazada por pd.NA), marcado de fechas imposibles como NaT, y evaluación de nulos en duration/length como posiblemente MAR (Missing At Random).

**4. Summary statistics de uso por usuario**
Agregación de la tabla usage por user_id (total de mensajes, llamadas y minutos), y resumen estadístico de variables numéricas y categóricas durante 2024.

**5.Visualización de distribuciones y outliers**
Histogramas de edad y variables de uso, y boxplots para detectar valores extremos en llamadas, mensajes y minutos.

**6. Segmentación de clientes**
Creación de la columna grupo_uso (Bajo uso / Uso medio / Alto uso) y grupo_edad (Joven / Adulto / Adulto Mayor), con visualización de la distribución de cada segmento.

**7. Insight ejecutivo para stakeholders**
Traducción de los hallazgos en conclusiones de negocio: problemas de calidad de datos detectados, perfil de los segmentos, oportunidades de upsell (ej. usuarios del plan Básico que exceden su uso) y recomendaciones sobre retención del segmento de "uso medio" (73.59% de la base de clientes).

**8. Documentación y versionado**
Publicación del notebook y este README en un repositorio de GitHub.
