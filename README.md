# estudio_bicicletas_biki_valladolid
Estudio de funcionamiento de servicio de alquiler de bicicletas BIKI en Valladolid 
# 🚴‍♂️ Análisis de Estado, Distribución y Tendencias de BIKI Valladolid

Este repositorio contiene un análisis de datos exhaustivo y visual sobre el sistema de bicicletas públicas de Valladolid (**BIKI**), desarrollado íntegramente en un Jupyter Notebook con Python. El estudio abarca desde el estado de ocupación de las estaciones en tiempo real hasta modelos de crecimiento temporal, preferencias de flota (mecánica vs. eléctrica) y un simulador de rentabilidad de tarifas.

---

## 📊 Estructura del Análisis

El proyecto está dividido en bloques estratégicos, que responden a preguntas clave sobre la movilidad ciclista en la ciudad:

### 🔍 Bloque 1: Análisis de Estado y Distribución de las Estaciones
* **Objetivo:** Identificar estaciones críticas por saturación (falta de anclajes libres) o vaciamiento (falta de bicicletas).
* **Métricas:** Cálculo del porcentaje de ocupación real.
* **Resultados Clave:** Identificación de las 5 estaciones más saturadas  y las 5 más vacías.

### 📈 Bloque 2: Tendencia Temporal y Crecimiento Histórico
* **Objetivo:** Analizar la evolución mensual de usuarios registrados desde la inauguración del servicio (febrero de 2023) hasta la actualidad (julio de 2026).
* **Visualización:** Gráfico evolutivo de series temporales comparativas por años.
* **Puntos Clave:** Mapeo del crecimiento orgánico del sistema y detección de picos de demanda estacionales (repuntes drásticos en septiembre/octubre vinculados al inicio del curso universitario y escolar).

### ⚡ Bloque 3: Preferencias de Uso (Mecánicas vs. Eléctricas)
* **Objetivo:** Evaluar la cuota de mercado real que domina cada tipo de vehículo en la ciudad.
* **Visualización:** Gráficos de barras interactivos que contrastan los viajes mensuales de ambas flotas durante 2025.
* **Resultados Clave:** Dominio de la **asistencia al pedaleo**, acaparando las bicicletas eléctricas una **media anual del 82.56%** de los viajes, debido principalmente a la topografía de la ciudad y la comodidad en distancias largas.

### 👥 Bloque 4: Análisis Demográfico y Perfiles de Usuario
* **Objetivo:** Clasificar las necesidades de los usuarios según su rol y trazar las rutas óptimas basándose en la ubicación de las estaciones.
* **Modelos de Perfil creados:**
  1. *Estudiante UVA (Campus Miguel Delibes):* Perfil llano, idóneo para tarifa plana y uso diario recurrente con bicicleta mecánica.
  2. *Estudiante UEMC / Personal Sanitario (Eje Río Hortega):* Ruta periférica de mayor distancia (3.8 km), donde la bicicleta eléctrica es la opción más competitiva.
  3. *Trabajador Pendular (Parquesol):* Salvando el fuerte desnivel del barrio mediante el uso obligatorio de motor eléctrico.
* **Visualización:** Matriz interactiva de esfuerzo de rutas (gráfico de burbujas en Plotly) y gráfico de barras agrupadas para distancias a facultades.

### 💰 Bloque 5: Impacto de Tarifas y Umbral de Rentabilidad
* **Objetivo:** Determinar mediante un simulador matemático en qué punto exacto le conviene económicamente a un ciudadano pasar de la tarifa de "Usuario Ocasional" a un "Bono Mensual (Tarifa Plana)".
* **Resultados del simulador:**
  - 🚲 **Bici Mecánica:** El bono se amortiza y es rentable a partir de los **48 viajes al mes**.
  - ⚡ **Bici Eléctrica:** El bono se amortiza y es rentable a partir de los **30 viajes al mes**.

---

## 🛠️ Tecnologías y Librerías Utilizadas

El análisis ha sido desarrollado utilizando el ecosistema de ciencia de datos de **Python 3**:
* **Pandas:** Procesamiento, limpieza de datos y manipulación de DataFrames.
* **Matplotlib & Seaborn:** Generación de gráficos estáticos de series temporales y diagramas de barras de alta calidad.
* **Plotly Express:** Creación de cuadros de mando y gráficos de dispersión/burbujas interactivos con soporte de *hovertemplate*.
* **IO (StringIO / BytesIO):** Gestión eficiente de flujos de datos en memoria para la carga de datos consolidados.

---

## 🚀 Cómo Ejecutar el Proyecto

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com
   cd biki-valladolid-analysis
   ```

2. **Instalar las dependencias necesarias:**
   Asegúrate de tener instalado `pip` y ejecuta:
   ```bash
   pip install pandas matplotlib seaborn plotly
   ```

3. **Abrir el cuaderno:**
   Ejecuta Jupyter Notebook o abre el archivo `.ipynb` directamente en tu IDE preferido (VS Code, JupyterLab, etc.):
   ```bash
   jupyter notebook analisis_biki.ipynb
   ```

---

## 📋 Conclusiones del Estudio

* **La Consolidación de BIKI:** El sistema ha experimentado un crecimiento estructural ascendente, duplicando con creces su base de usuarios activos desde su lanzamiento.
* **La "Eléctrico-dependencia":** Valladolid se ha transformado en una ciudad que prioriza el pedaleo asistido para ahorrar tiempos de viaje en distancias medias y salvar barreras geográficas (como la subida a Parquesol).
* **Uso Inteligente del Servicio:** El análisis de tarifas demuestra que para un usuario cotidiano (2 viajes por día laborable), la adquisición de bonos mensuales amortiza la inversión rápidamente, de forma especial en la flota eléctrica.
