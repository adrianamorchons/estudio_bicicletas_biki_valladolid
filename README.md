# Análisis de Estado, Tendencias y Simulación Logística del Sistema BIKI (Valladolid)

Este proyecto realiza un análisis integral de ciencia de datos, modelado predictivo, econometría y viabilidad financiera sobre el sistema de bicicletas públicas **BIKI de Valladolid** (gestionado por AUVASA). El estudio abarca desde la auditoría en tiempo real de la red actual hasta el modelado de elección de flota, enrutamiento ciclista por callejero y simulación económica para la expansión metropolitana hacia **Arroyo de la Encomienda** y **Zaratán**.

---

## 📊 Estructura del Análisis

La investigación se estructura en **cinco grandes bloques metodológicos**:

### 1. Diagnóstico Geográfico, Climatológico y Operativo de la Red
* **Auditoría en Tiempo Real (Protocolo GBFS):** Integración directa con los *endpoints* públicos oficiales (`station_information` y `station_status`) de AUVASA para monitorizar la disponibilidad instantánea de las **104 estaciones activas** (con respaldo automático *offline*).
* **Detección de Puntos Críticos:** Identificación de asimetrías operativas por saturación o vaciamiento:
  * *Zonas críticas por saturación:* Facultad de Medicina (**95,65 %** de ocupación), Polideportivo Ponce de León (**91,30 %**) y Barrio Arcas Reales (**90,91 %**).
  * *Zonas críticas por vaciamiento:* Plaza de Santa Cruz (**13,33 %**) y Calle de Andalucía (**15,38 %**).
* **Preferencias de Flota y Climatología:** El histórico de 2025 confirma un dominio de la bicicleta eléctrica (**82,8 %** de media anual), impulsado por la topografía (acceso a Parquesol) y la fatiga térmica estival (**86,84 %** en agosto), mientras que el calendario académico dispara el uso mecánico en septiembre y octubre (**20,81 %** y **20,14 %**).


---

### 2. Modelado de Tendencias y Regresión Predictiva
* **Predicción de Colapso de Capacidad:** Modelo de **Regresión Lineal** ($Y = 212,89X + 6.286,53$) entrenado sobre la serie histórica de altas mensuales. Con un crecimiento medio de **213 usuarios nuevos al mes**, el sistema alcanza el umbral crítico de estrés logístico (**15.696 usuarios**, equivalente a 9 usuarios por anclaje sobre 1.744 anclajes fijos) en el **mes 44,2 (septiembre de 2026)**, justificando la ampliación estructural de la red.


---

### 3. Machine Learning, Redes y Simulación Estadística
* **Segmentación de Estaciones (Clustering K-Means):** Clasificación no supervisada en **4 perfiles operativos** (*Nodos Críticos Saturados*, *Nodos Centrales Equilibrados*, *Estaciones Estándar/Periféricas* y *Macro-estaciones Atípicas* como Plaza del Poniente o el futuro macro-nodo de Avda. de Salamanca).
* **Ciencia de Redes (`NetworkX`):** Cálculo de centralidad de intermediación para identificar estaciones puente críticas (como **Calle Arca Real**, **Plaza Circular** y **Calle Joaquín Velasco Martín**).
* **Simulación de Montecarlo (Gestión de Inventario):** Modelado de **10.000 escenarios** en hora punta. Para **Plaza Circular** (26 anclajes) se estima un **4,5 %** de riesgo de colapso, determinando un *stock* de seguridad de **9 unidades** y un punto de reposición óptimo de **27 unidades** (95 % de confianza). Para la futura estación de **Zaratán – Plaza de la Ronda**, la simulación aconseja dimensionar **35 anclajes** (frente a los 30 iniciales) para cubrir el punto óptimo de **34 unidades**.


---

### 4. Modelo de Elección Discreta (Logit) y Enrutamiento Real (OSRM)
* **Regresión Logística + Montecarlo:** Simulación de **10.000 viajes por corredor** combinando distancia, pendiente, incomodidad térmica (desviación respecto a 18 ºC) y sensibilidad al precio:
  * *Centro – Campus Miguel Delibes (UVa):* **59,5 % eléctrica** / **40,5 % mecánica** (único eje llano con alta presencia estudiantil).
  * *Plaza Circular – HURH / UEMC:* **97,2 % eléctrica**.
  * *Zaratán / Arroyo – Valladolid Centro:* **98,2 % eléctrica**.
  * *Parquesol – Facultad de Medicina (Ruta real OSRM de 5,60 km):* **98,97 % eléctrica**, validando el trazado real por callejero y carriles bici.


---

### 5. Estudio Demográfico y Viabilidad Financiera (CAPEX, OPEX y Payback)
* **Potencial Demográfico del Alfoz:** Análisis de pirámides poblacionales censales destacando el perfil joven de **Arroyo de la Encomienda** (23.304 hab., edad media 37,8 años) y **Zaratán** (6.386 hab., edad media 38,8 años).
* **Proyección Económica a 5 Años:** Con una inversión inicial (**CAPEX**) de **425.400 €** (4 estaciones en Arroyo y 2 en Zaratán) y unos costes operativos (**OPEX**) de **53.880 €/año**, el proyecto alcanza el punto de equilibrio (*break-even*) en el **mes 6 del Año 2** y genera un **beneficio neto acumulado de 2.241.861,62 € al cierre del Año 5**.


---

## 🛠️ Tecnologías y Librerías Utilizadas

El proyecto ha sido desarrollado en **Python 3.12** utilizando el siguiente ecosistema técnico:

* **Manipulación y Exportación de Datos:** `pandas`, `numpy` y `openpyxl` (generación de informes consolidados en `.xlsx` y `.csv`).
* **Visualización Estática e Interactiva:** `matplotlib`, `seaborn` y `plotly` (gráficos interactivos, histogramas de riesgo, curvas financieras y diagramas divergentes).
* **Modelado Geoespacial y Enrutamiento:** `folium` (**Leaflet.js**), `requests` y API pública de **OSRM** (*Open Source Routing Machine*) para trazado real sobre carril bici.
* **Machine Learning y Ciencia de Redes:** `scikit-learn` (`StandardScaler`, `KMeans`, `LinearRegression`) y `networkx`.

---

## 🚀 Cómo Ejecutar el Proyecto

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com
   cd estudio_bicicletas_biki_valladolid
   ```

2. **Instalar las dependencias:**
   ```bash
   pip install pandas numpy notebook matplotlib seaborn plotly scikit-learn networkx folium requests openpyxl
   ```

3. **Ejecutar el Notebook:**
   Abre el cuaderno en Jupyter o VS Code para reproducir el análisis paso a paso:
   ```bash
   jupyter notebook analisis_servicio_biki_valladolid.ipynb
   ```

---

## MAPA INTERACTIVO GENERADO CON LEAFLET: Simulación Biki Valladolid (recorrido real) 

Haz clic en la imagen para abrir el mapa interactivo en pantalla completa (con zoom y etiquetas):

[![Simulación Biki Valladolid](preview_mapa.png)](https://github.io)

👉 **[Explorar el mapa interactivo aquí](https://github.io)**

