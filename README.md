# 🚲 Pucela sobre Ruedas: Panel de Movilidad BIKI Valladolid

Análisis avanzado de datos, modelado predictivo y plataforma web interactiva en tiempo real sobre el sistema de bicicletas públicas **BIKI** de Valladolid. 

Este proyecto combina un exhaustivo estudio de **Data Science** (Clustering, Regresiones y Simulaciones Estocásticas) desarrollado en un entorno de Jupyter Notebook, con una aplicación web en producción desplegada de forma continua a través de **Replit Agent**.

---

## 📊 Arquitectura y Componentes del Proyecto

El ecosistema está diseñado de forma modular para garantizar la consistencia entre la fase de investigación de datos y el despliegue del software en vivo:

```text
├── app.py                     # Servidor Web Flask y lógica de sincronización GBFS
├── estaciones.csv             # Dataset consolidado de la red estática (96 estaciones)
├── requirements.txt           # Dependencias del entorno de producción
├── simulacion_zaratan_biki.html # Resultados gráficos de la simulación de Montecarlo
├── templates/
│   └── index.html             # Interfaz de usuario (Dashboard Web Avanzado)
└── BIKI_Movilidad_Notebook.ipynb # Cuaderno de investigación, Machine Learning y EDAs
```

---

## 🚀 Características Principales por Componentes

### 1. Panel Web en Tiempo Real (Despliegue en Replit)
*   **Integración Viva con AUVASA:** Conectado directamente a la API de datos abiertos y los feeds públicos **GBFS** (*General Bikeshare Feed Specification*) de Valladolid para reflejar las métricas exactas de bicicletas y anclajes disponibles en la calle en el preciso instante de la consulta.
*   **Semaforización Geoespacial Inteligente:** Generación de mapas dinámicos a través de `Folium` que cambian el color de los nodos según su nivel de estrés logístico (Verde: Equilibrio | Naranja: Ocupación Alta | Rojo/Azul: Saturación o Vacamiento Crítico).
*   **Análisis Paramétrico de Corredores:** Implementación de capas de visualización interactivas sobre teoría de grafos para mapear las rutas óptimas de los perfiles urbanos más vulnerables (Corredor UVa Norte, Corredor Sureste UEMC/HURH y Eje de Esfuerzo de Parquesol).

### 2. Cuaderno de Ciencia de Datos (`BIKI_Movilidad_Notebook.ipynb`)
El núcleo de la investigación se segmenta en bloques estratégicos que responden matemáticamente al comportamiento del sistema:

*   **Bloque 1: Diagnóstico Logístico de las Estaciones:** Análisis de capacidad nominal e identificación algorítmica de asimetrías operativas. Se detectan puntos de estrés crítico (Facultad de Medicina, 95.65% de ocupación) frente a zonas vacías de desabastecimiento (Plaza de Santa Cruz, 13.33% de ocupación).
*   **Bloque 2: Penetración de la App y Evolución Temporal:** Curva de crecimiento interanual de usuarios desde el lanzamiento en 2023 (5,331 usuarios iniciales), pasando por una fase de estabilización en 2024 (10,000 - 12,000 usuarios) hasta la expansión al Alfoz en 2026, alcanzando un histórico acumulado de 17,075 descargas efectivas.
*   **Bloque 3: Preferencias de Flota:** Evaluación de cuota de mercado por vehículo, confirmando el dominio absoluto de la asistencia al pedaleo con una **media del 82.56% de viajes en bicicleta eléctrica** frente al 17.44% de las mecánicas.
*   **Bloque 4: Arquetipos Geográficos de Usuario:** Modelado de perfiles de usuario (Estudiante UVa Norte, Personal Sanitario Sureste, y Trabajador Pendular Parquesol) en base a la topografía vial, distancias de traslado y nudos de tráfico pesado.
*   **Bloque 5: Correlación Climatológica y Factor Social:** Demostración científica (mediante coeficiente de Pearson) de que el calendario social y académico gobierna la red por encima del clima. Los meses de septiembre y octubre registran picos de **crecimiento interanual del 37.7% y 45.8%**, superando la actividad de los meses con mejores temperaturas veraniegas (julio/agosto).
*   **Bloque 6: Simulaciones Matemáticas de Tarifas:** Creación de un simulador de gasto mensual para fijar el umbral de rentabilidad. El paso de Tarifa Ocasional a Bono Mensual se amortiza a partir del **viaje 48 en mecánica y del viaje 30 en eléctrica**.
*   **Bloque 7: Segmentación Avanzada mediante Machine Learning (K-Means):** Clasificación no supervisada de la red a través de `scikit-learn` en 4 clústeres operativos (Nodos Críticos, Uso Estable, Zonas de Vacamiento y Estaciones Periféricas) para optimizar las tareas de rebalanceo de flota de los operarios de AUVASA.
*   **Bloque 8: Ciencia de Redes (NetworkX):** Análisis topológico para calcular la centralidad de intermediación de la red vial de BIKI, detectando qué estaciones actúan como "puentes estructurales" de movilidad entre distritos de Valladolid.
*   **Bloque 9: Simulación de Riesgo de Montecarlo:** Modelado estocástico de 10,000 escenarios diarios con volatilidad climática. Establece un Punto de Reposición Óptimo en el cual AUVASA debe intervenir en cuanto una estación de 26 anclajes alcance las 27 unidades teóricas (sumando un stock de seguridad de 9 unidades) para blindar el sistema al 95% de confianza. Incorpora además la simulación de expansión geográfica futura hacia la Plaza de la Ronda de Zaratán (Ref. 1101).

---

## 🛠️ Tecnologías y Librerías Utilizadas

*   **Entorno de Desarrollo:** Jupyter Notebook, Replit Workspace & Replit Agent.
*   **Lenguaje y Manipulación de Datos:** Python 3.11, Pandas, NumPy, Io, Base64.
*   **Visualización Interactiva y Científica:** Plotly Express, Seaborn, Matplotlib, Folium.
*   **Modelado Estadístico y ML:** Scikit-Learn (K-Means, StandardScaler), NetworkX.
*   **Arquitectura Web:** Flask (Servidor Web), Bootstrap 5 (Frontend).

---

## 💻 Instrucciones de Instalación y Ejecución Local

Para replicar el análisis completo o desplegar la aplicación en un servidor local, sigue estos pasos:

1. Clonar el repositorio:
   ```bash
   git clone https://github.com
   cd pucela-sobre-ruedas
   ```

2. Instalar las dependencias requeridas del sistema:
   ```bash
   pip install -r requirements.txt
   ```

3. **Para ejecutar el Cuaderno de Ciencia de Datos:**
   Abre tu entorno de Jupyter o VS Code y ejecuta todas las celdas de `BIKI_Movilidad_Notebook.ipynb` para recalcular las simulaciones de Montecarlo, las regresiones y la segmentación K-Means.

4. **Para lanzar el Dashboard Web en vivo:**
   Ejecuta el servidor Flask desde tu terminal:
   ```bash
   python app.py
   ```
   Abre en tu navegador la dirección local `http://127.0.0.1:5000` para interactuar de forma directa con el panel dinámico geoespacial.
