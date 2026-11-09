# 🚲 BIKI Valladolid - Análisis de Datos, Machine Learning y Simulación Logística

Este repositorio contiene un análisis avanzado de datos, modelado predictivo y simulación  del sistema de bicicletas **BIKI** de la ciudad de Valladolid, gestionado por la empresa municipal **AUVASA**. A través de este proyecto se evalúa el estado operativo de la red, la penetración de su aplicación móvil, preferencias de los usuarios, optimización de rutas según perfiles demográficos y el riesgo de colapso en estaciones clave mediante métodos estadísticos y de Machine Learning.

El análisis abarca el comportamiento histórico real del servicio desde su lanzamiento en **febrero de 2023 hasta agosto de 2026** (se actualizará con los datos de los meses siguientes). Los principales hallazgos revelan:
1. **Fidelización del Usuario:** El servicio ha superado la fase de adopción masiva llegando a más de 17.000 usuarios registrados, y se mantiene estable con una base de 10.000 a 12.000 usuarios activos mensuales.
2. **Dominio Eléctrico:** La bicicleta eléctrica domina el mercado con más del 82% de los viajes mensuales, debido a la topografía de la ciudad (ej. desniveles hacia el barrio de Parquesol) y a la búsqueda de confort frente a extremos climáticos.
3. **Estacionalidad Académica:** Se detecta un incremento interanual de uso de entre el **37% y el 45% durante los meses de septiembre y octubre**, impulsado directamente por el retorno de la comunidad universitaria y escolar.

---

## 🛠️ Stack y Librerías Utilizadas

El proyecto está desarrollado completamente en **Python** dentro de un entorno Jupyter Notebook, utilizando el siguiente stack tecnológico:

*   **Manipulación de Datos:** `pandas`, `numpy`, `io`.
*   **Machine Learning:** `scikit-learn` (`KMeans`, `StandardScaler`).
*   **Ciencia de Redes:** `networkx` (análisis de centralidad de intermediación).
*   **Modelado Estadístico:** Simulación de Montecarlo (distribuciones normales de probabilidad).
*   **Visualización de Datos:** `matplotlib`, `seaborn`, `plotly.express`.
*   **Análisis Geoespacial:** `folium`, `geopy` (mapas interactivos basados en OpenStreetMap).

---

## 🔍 Estructura del Análisis e Implementación Técnica

El cuaderno de Jupyter se divide en bloques analíticos:

### 1. Análisis de Estado y Distribución de Estaciones
Se calculan los porcentajes de ocupación en tiempo real para las 96 estaciones fijas de la red, identificando automáticamente los puntos críticos de **saturación** (ej. *Facultad de Medicina* con >95% de ocupación) y de **vaciamiento** (ej. *Plaza de Santa Cruz* con <14%).

### 2. Segmentación Avanzada con Machine Learning (K-Means)
Se implementa un modelo de **Clustering K-Means** (normalizando los datos con `StandardScaler`) para clasificar de manera automática las estaciones en 4 perfiles operativos según su capacidad, ocupación y anclajes libres:
*   *Nodos Críticos / Alta Saturación*
*   *Zonas de Vaciamiento / Alta Disponibilidad*
*   *Capacidad Media / Uso Estable*
*   *Baja Capacidad / Estaciones Periféricas (Alfoz)*

### 3. Ciencia de Redes y Rutas Óptimas por Perfil
Utilizando la librería `networkx`, se modela la red como un grafo interconectado por distancias ciclistas. Se diseñan y trazan rutas óptimas para tres perfiles de usuario identificados en Valladolid:
*   **Estudiante UVA (Norte):** Ruta llana de corta distancia ideal para bicicletas mecánicas.
*   **Estudiante UEMC / Personal Sanitario (Sureste):** Ruta periférica larga idónea para flota eléctrica.
*   **Trabajador Pendular (Oeste):** Ruta directa con fuerte pendiente hacia el barrio de Parquesol, requiriendo asistencia eléctrica obligatoria.

### 4. Simulación de Montecarlo: Riesgo de Colapso Logístico
Se desarrollan **10.000 iteraciones logísticas** basadas en la distribución normal de la demanda en hora punta para evaluar la probabilidad de fallo por falta de anclajes o vehículos. El modelo calcula automáticamente:
*   **Probabilidad de Stockout (Colapso):** Determina el riesgo porcentual de fallo en estaciones saturadas (ej. Plaza Circular).
*   **Stock de Seguridad:** El colchón de unidades necesario para absorber la volatilidad climatológica o social.
*   **Punto de Reposición Óptimo (ROP):** El inventario ideal que los operarios de AUVASA deben mantener en la estación para garantizar un 95% de confianza en el servicio.

### 5. Simulación de Expansión Geográfica (Alfoz)
Se proyecta y simula mediante Montecarlo el comportamiento de una futura estación en el municipio colindante de **Zaratán (Plaza de la Ronda)**, estimando su volatilidad por pendientes y determinando que su capacidad inicial requeriría un objetivo logístico real de 35 anclajes para mitigar un riesgo de colapso del 12.3%.

### 6. Cartografía Geoespacial Interactiva
Generación de mapas interactivos (`mapa_rutas_biki.html`) mediante `folium` que permiten visualizar sobre la geografía real de Valladolid la ubicación de las estaciones, su estado crítico por colores (Rojo: Saturado, Azul: Vacío, Verde: Estable) y el trazado de las redes de conectividad del campus.

---

## 🚀 Cómo Ejecutar el Proyecto

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com
   cd biki-valladolid-analytics
   ```

2. **Instalar las dependencias:**
   Se recomienda usar un entorno virtual. Puedes instalar los paquetes necesarios ejecutando:
   ```bash
   pip install pandas numpy matplotlib seaborn plotly scikit-learn networkx folium geopy
   ```

3. **Abrir el cuaderno:**
   Ejecuta Jupyter Notebook o JupyterLab y abre el archivo `.ipynb` para ver el análisis paso a paso y generar los mapas interactivos HTML locales.
   ```bash
   jupyter notebook
   ```


