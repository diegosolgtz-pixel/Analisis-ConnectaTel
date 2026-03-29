# Analisis-ConnectaTel
Análisis de Clientes y Consumo - ConnectaTel 📊
Este proyecto realiza un análisis exploratorio de datos  para una empresa de telecomunicaciones (ConnectaTel). El objetivo principal es identificar el perfil demográfico de los clientes y sus patrones de consumo.

📋 Data sets Utilizados
plans.csv → información de los planes actuales (precio, minutos incluidos, GB incluidos, costo por extra)

users.csv → información de los clientes (edad, ciudad, fecha de registro, plan, churn)

usage.csv → detalle del uso real de los servicios (llamadas y mensajes)


🛠️ Tecnologías Utilizadas
Python 3.x

Pandas: Limpieza y manipulación de datos.

Seaborn & Matplotlib: Visualización estadística.

Jupyter Notebook: Entorno de desarrollo.


🧹 Preprocesamiento y Limpieza de Datos 
En esta etapa se realizaron acciones críticas para asegurar la calidad de la información:

Tratamiento de Sentinels: Se identificaron y eliminaron valores -999 en la columna de edad, los cuales distorsionaban la desviación estándar y el promedio.

Normalización de Fechas: Conversión de columnas de tipo objeto a formato datetime (ej. reg_date) para permitir cálculos de antigüedad.

Limpieza de Texto: Se reemplazaron caracteres especiales como '?' en la columna de ciudades por valores nulos o "Desconocido".

Gestión de Outliers: Análisis de valores extremos en consumo mediante el método IQR (Rango Intercuartílico).

📈Análisis Exploratorio (EDA) 
Segmentación de usuarios por edad (Jóvenes, Adultos, Adultos Mayores).

Clasificación por nivel de uso (Bajo, Medio, Alto).

Visualización de distribución de variables numéricas mediante Boxplots e Histogramas.

🔍 Hallazgos Clave (Insights)
1. Perfil Demográfico
Segmento Dominante: El 50% de la base son Adultos (30-59 años).

Oportunidad: Baja penetración en el segmento Joven (<30 años), lo que sugiere una revisión necesaria en la oferta digital.

2. Análisis de Consumo y Outliers
Se identificaron valores atípicos en la duración de llamadas (máximos de 155 min), los cuales superan el límite del Plan Básico (100 min).

Los outliers de mensajes y cantidad de llamadas se mantuvieron en el análisis por representar comportamientos reales de usuarios intensivos.

🚀 Ejecución del Notebook
Puedes visualizar y ejecutar este análisis de dos formas:

Opción A: Google Colab (Recomendado)
Sube el archivo .ipynb a tu Google Drive.

Haz clic derecho y selecciona "Abrir con" -> Google Colaboratory.

Sube los archivos .csv a la sección de archivos de Colab (icono de carpeta a la izquierda).

Opción B: Local (Jupyter Notebook)
Clona este repositorio.

Asegúrate de tener instalado Python y las librerías necesarias: pip install pandas matplotlib seaborn.

Ejecuta jupyter notebook en tu terminal.

🔄 Guía de Reproducción
Para obtener los mismos resultados presentados en este reporte:

Carga los tres datasets originales sin modificaciones previas.

Ejecuta las celdas de Limpieza primero (reemplazo de -999, ? y conversión de fechas).

Corre las funciones de agrupación (groupby) para unir la actividad de consumo con la tabla de perfiles de usuario.

Genera las gráficas de segmentación para validar la distribución de los grupos
