# Análisis ConnectaTel

## Descripción del proyecto

Análisis exploratorio de datos (EDA) para la empresa de telecomunicaciones **ConnectaTel**. El objetivo principal es identificar el perfil demográfico de los clientes y sus patrones de consumo para optimizar las ofertas comerciales.

---

## Estructura del repositorio y datasets

* `plans.csv` : Información de planes actuales (precio, minutos incluidos, GB incluidos, costo extra).
* `users.csv` : Información de clientes (edad, ciudad, fecha de registro, plan, churn).
* `usage.csv` : Detalle del uso real de servicios (llamadas y mensajes).

---

## Tecnologías utilizadas

* **Python 3.x:** Lenguaje principal.
* **Pandas:** Limpieza, preprocesamiento y manipulación de datos.
* **Seaborn & Matplotlib:** Visualización estadística (boxplots e histogramas).
* **Jupyter Notebook:** Entorno de desarrollo.

---

## Preprocesamiento y limpieza de datos

* **Tratamiento de Sentinels:** Eliminación de valores `-999` en la columna de edad para evitar distorsionar la desviación estándar y el promedio.
* **Normalización de Fechas:** Conversión de columnas objeto a `datetime` (ej. `reg_date`) para calcular la antigüedad del cliente.
* **Limpieza de Texto:** Reemplazo de caracteres especiales como `?` por nulos/`Desconocido` en la columna de ciudades.
* **Gestión de Outliers:** Análisis de valores extremos en consumo mediante el método **IQR** (Rango Intercuartílico).

---

## Análisis Exploratorio (EDA)

* **Segmentación:** Categorización por rango de edad (*Jóvenes, Adultos, Adultos Mayores*) y nivel de uso (*Bajo, Medio, Alto*).
* **Visualización:** Análisis de distribución de variables numéricas mediante Boxplots e Histogramas.

---

## Hallazgos clave (Insights)

1. **Perfil Demográfico:** El segmento dominante es de **Adultos (30-59 años)**, representando el **50% de la base**.
   * *Oportunidad:* Se detectó una baja penetración en el segmento **Joven (<30 años)**, lo que sugiere ajustar la oferta digital.
2. **Análisis de Consumo y Atípicos:**
   * Se identificaron llamadas atípicas de hasta **155 min**, superando el límite del Plan Básico (100 min).
   * Los *outliers* de mensajes y número de llamadas se mantuvieron por representar comportamientos reales de usuarios intensivos.

---

## Ejecución del notebook

### Opción A: Google Colab (Recomendado)
1. Sube el archivo `.ipynb` a Google Drive.
2. Haz clic derecho y selecciona **Abrir con -> Google Colaboratory**.
3. Sube los archivos `.csv` a la sección de archivos de Colab (icono de carpeta a la izquierda).

### Opción B: Local (Jupyter Notebook)
1. Clona este repositorio.
2. Instala las librerías necesarias:
   ```bash
   pip install pandas matplotlib seaborn notebook
