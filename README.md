# Análisis de Estado, Tendencias y Simulación Logística del Sistema BIKI (Valladolid)

Este proyecto realiza un análisis integral de datos, modelado predictivo y simulación del sistema de bicicletas públicas **BIKI de Valladolid** (gestionado por AUVASA). Utilizando técnicas de Ciencia de Datos y Machine Learning, el estudio abarca desde la detección de puntos de estrés en la red actual hasta la proyección de colapsos del sistema y simulaciones para la expansión geográfica al alfoz.

---

## 📊 Estructura del Análisis

El core de la investigación se divide en tres grandes áreas de análisis avanzado:

### 1. Diagnóstico Geográfico y Operativo de la Red
* **Detección de Puntos Críticos:** Identificación de estaciones bajo estrés por saturación (alta ocupación) o vaciamiento (falta de flota).
  * *Zonas críticas por saturación:* Facultad de Medicina (95.65% de ocupación), Polideportivo Ponce de León (91.30%) y Barrio Arcas Reales (90.91%).
  * *Zonas críticas por vaciamiento:* Plaza de Santa Cruz (13.33% de ocupación) y Calle de Andalucía (15.38%).
* **Preferencias de Flota:** Evaluación de cuota de mercado entre bicicletas mecánicas y asistidas (eléctricas). El modelo demuestra un dominio absoluto de la bicicleta eléctrica, acaparando una **media anual del 82.56% de los viajes**, debido a la topografía (ej. acceso a Parquesol) y comodidad del usuario.

### 2. Modelado de Tendencias y Regresión Predictiva
* **Correlación Climatológica y Social:** Análisis de estacionalidad cruzando datos de uso con registros de temperatura media mensual de Valladolid. El modelo revela un coeficiente de Pearson moderado-bajo, demostrando que los hábitos están guiados por el calendario laboral/escolar (picos masivos de adopción en septiembre y octubre de +37.7% y +45.8% interanual) por encima de las variables térmicas.
* **Predicción de Colapso del Sistema:** Implementación de un modelo de **Regresión Lineal** basado en el histórico de altas (febrero 2023 - septiembre 2026). Con una tasa de crecimiento de **213 usuarios nuevos al mes** ($y = 212.89x + 6286.53$), el sistema cruzó el umbral crítico de estrés logístico (9 usuarios por anclaje fijo) en **septiembre de 2026** al alcanzar los 18,443 registros, confirmando la necesidad de ampliar la infraestructura.

### 3. Machine Learning y Simulaciones Estadísticas
* **Segmentación de Estaciones (Clustering K-Means):** Agrupación no supervisada utilizando Scikit-Learn (basada en capacidad total, % de ocupación y docks libres). El algoritmo clasificó la red de forma matemática en 4 perfiles logísticos:
  * *Nodos Críticos / Alta Saturación* (Vaciado urgente).
  * *Zonas de Vaciamiento / Alta Disponibilidad* (Inyección de flota).
  * *Capacidad Media / Uso Estable* (Equilibrio orgánico).
  * *Baja Capacidad / Estaciones Periféricas* (Alfoz).
* **Simulación de Montecarlo (Gestión de Inventario):** Modelado de 10,000 escenarios diarios de operación en hora punta. Para el nodo de Plaza Circular, se calculó una **probabilidad de stockout del 4.36%**, determinando que se requiere un **stock de seguridad de 9 bicicletas** y un **punto de reposición óptimo de 27 unidades** para mitigar la volatilidad.
* **Simulación de Expansión (Zaratán):** Proyección estadística para la futura estación de Plaza de la Ronda (Zaratán). El modelo determinó que una base inicial de 30 anclajes tendría un **10.84% de probabilidad de colapso**, recomendando un objetivo logístico real de **34 unidades mínimas** (35 anclajes físicos con un 60% de ocupación matutina: 15 eléctricas y 3 mecánicas) para absorber la demanda del alfoz.

---

## 🛠️ Tecnologías y Librerías Utilizadas

El análisis y desarrollo de los modelos se ha realizado bajo el entorno de **Python 3.12** utilizando el siguiente ecosistema de librerías:

* **Manipulación de Datos:** `pandas`, `numpy`
* **Visualización de Datos e Indicadores:** `matplotlib`, `seaborn`
* **Mapas Interactivos Geoespaciales:** `folium`, `geopy`
* **Machine Learning (Clustering):** `scikit-learn` (StandardScaler, KMeans)
* **Ciencia de Redes:** `networkx`

---

## 🚀 Cómo Ejecutar el Proyecto

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com
   cd REPOSITORIO_BIKI
   ```

2. **Instalar las dependencias:**
   ```bash
   pip install pandas numpy notebook matplotlib seaborn scikit-learn networkx folium geopy
   ```

3. **Ejecutar el Notebook:**
   Abra el cuaderno de Jupyter para reproducir el análisis paso a paso:
   ```bash
   jupyter notebook analisis_biki_valladolid.ipynb
   ```

---

## 🗺️ Visualización de Mapas Interactivos

Al ejecutar las celdas del **Bloque 12**, el script generará automáticamente un archivo HTML dinámico en la raíz del proyecto:
* `mapa_rutas_biki.html`: Contiene la georreferenciación de las estaciones, cuadrantes de color inteligente según su nivel de criticidad en tiempo real y el trazado de las rutas óptimas por perfil de usuario (UVA Norte, UEMC Sureste y Parquesol Oeste).

Puedes abrirlo directamente en tu navegador desde la terminal con:
```bash
python -c "import webbrowser, os; webbrowser.open('file://' + os.path.abspath('mapa_rutas_biki.html'))"
```
