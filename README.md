# 🚴‍♂️ Análisis de Estado, Distribución y Tendencias de BIKI Valladolid

Este repositorio contiene un análisis de datos exhaustivo y visual sobre el sistema de bicicletas públicas de Valladolid (**BIKI**), desarrollado íntegramente en un Jupyter Notebook con Python. El estudio abarca desde el estado de ocupación de las estaciones en tiempo real hasta modelos de crecimiento temporal, preferencias de flota, segmentación avanzada de la red y simulaciones estocásticas de fiabilidad logística.

---

## 📊 Estructura del Análisis

El proyecto está dividido en bloques estratégicos que responden a preguntas clave sobre la movilidad ciclista en la ciudad:

### 🔍 Bloque 1: Análisis de Estado y Estaciones Críticas
* **Objetivo:** Identificar estaciones críticas por saturación (falta de anclajes libres) o vaciamiento (falta de bicicletas).
* **Métricas:** Cálculo del porcentaje de ocupación real en tiempo real.
* **Resultados Clave:** Mapeo del % de ocupación por estación. Se identifican nodos saturados (p. ej., Facultad de Medicina, Polideportivo Ponce de León) frente a estaciones con infrautilización crónica o vacías (Plaza de Santa Cruz).

### 📈 Bloque 2: Tendencia Temporal y Crecimiento Histórico
* **Objetivo:** Analizar la evolución mensual de usuarios registrados y activos concurrentes desde la inauguración del servicio (febrero de 2023) hasta la actualidad (2026).
* **Puntos Clave:** Mapeo del crecimiento orgánico tras el boom inicial de lanzamiento, identificando una estabilización del servicio en una base sólida de usuarios fidelizados y fuertes repuntes estacionales (septiembre/octubre) vinculados al inicio del curso escolar y universitario.

### ⚡ Bloque 3: Preferencias de Uso (Mecánicas vs. Eléctricas)
* **Objetivo:** Evaluar la cuota de mercado real que domina cada tipo de vehículo en la ciudad.
* **Resultados Clave:** Dominio absoluto de la **asistencia al pedaleo**, acaparando las bicicletas eléctricas una **media superior al 80%** de los viajes mensuales. Esto demuestra el impacto directo de la topografía urbana (desniveles a barrios periféricos) en las decisiones de los usuarios.

### 👥 Bloque 4: Análisis Demográfico y Perfiles de Usuario
* **Objetivo:** Clasificar las necesidades de los usuarios según su rol y trazar rutas óptimas basándose en la ubicación de las estaciones y criterios de seguridad vial.
* **Arquetipos creados:**
  1. *Estudiante UVA (Campus Miguel Delibes / Zona Norte):* Perfil llano de corta distancia, idóneo para tarifa plana y uso de flota mecánica.
  2. *Estudiante UEMC / Personal Sanitario (Eje Río Hortega / Sureste):* Desplazamiento periférico de media distancia donde la bicicleta eléctrica ofrece mayor velocidad competitiva frente al coche.
  3. *Trabajador Pendular (Parquesol / Oeste):* Desplazamiento condicionado por el fuerte desnivel del barrio, requiriendo el uso obligatorio del motor eléctrico.

### 💰 Bloque 5: Impacto de Tarifas y Umbral de Rentabilidad
* **Objetivo:** Determinar mediante un simulador matemático en qué punto exacto le conviene económicamente a un ciudadano pasar de la tarifa de "Usuario Ocasional" a un "Bono Mensual (Tarifa Plana)".
* **Resultados del simulador:**
  - 🚲 **Bici Mecánica:** El bono se amortiza y es rentable a partir de los **48 viajes al mes**.
  - ⚡ **Bici Eléctrica:** El bono se amortiza y es rentable a partir de los **30 viajes al mes**.

### 🤖 Bloque 6: Modelado Avanzado y Analítica Predictiva
* **Segmentación K-Means (Machine Learning):** Algoritmo no supervisado que agrupa las estaciones en 4 perfiles logísticos diferenciados (*Capacidad media*, *Baja ocupación*, *Nodos críticos de alta saturación* y *Baja capacidad periférica*) para optimizar las tareas de balanceo de la flota.
* **Ciencia de Redes (NetworkX):** Análisis topológico para calcular la centralidad de intermediación de la red vial de BIKI, detectando qué estaciones actúan como "puentes estructurales" de movilidad entre distritos de Valladolid.
* **Simulación de Montecarlo:** Modelado estocástico basado en 10,000 escenarios operacionales para predecir márgenes de colapso, calcular el *Stock de Seguridad* necesario en hora punta y evaluar la resiliencia logística ante picos imprevistos de demanda o condiciones climáticas adversas.

---

## 🛠️ Tecnologías y Librerías Utilizadas

El análisis ha sido desarrollado utilizando el ecosistema de ciencia de datos de **Python 3.12**:
* **Pandas & NumPy:** Procesamiento, limpieza y manipulación avanzada de estructuras de datos.
* **Matplotlib & Seaborn:** Generación de gráficos estáticos de series temporales y distribución.
* **Plotly Express:** Creación de cuadros de mando y gráficos de dispersión interactivos (matrices de esfuerzo).
* **Scikit-Learn:** Implementación de modelos de clustering (`KMeans`) y escalado de variables (`StandardScaler`).
* **NetworkX:** Construcción y análisis de métricas de centralidad en grafos de transporte.
* **IO (StringIO / BytesIO):** Gestión eficiente de flujos de datos en memoria para la consolidación de dataframes.

---

## 🚀 Cómo Ejecutar el Proyecto

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com
   cd estudio_bicicletas_biki_valladolid
   ```

2. **Instalar las dependencias necesarias:**
   Asegúrate de tener instalado `pip` y ejecuta:
   ```bash
   pip install pandas numpy matplotlib seaborn plotly scikit-learn networkx
   ```

3. **Abrir el cuaderno:**
   Ejecuta Jupyter Notebook o abre el archivo directamente en tu IDE preferido (VS Code, JupyterLab, etc.):
   ```bash
   jupyter notebook analisis_biki.ipynb
   ```

---

## 📈 Conclusiones del Estudio

* **Consolidación Estructural:** Tras una explosión inicial en su lanzamiento, BIKI se ha consolidado en Valladolid como un pilar de transporte público masivo, mostrando picos cíclicos de demanda estrechamente vinculados al calendario académico de la ciudad.
* **Dependencia de la bicicleta eléctrica:** Con más del 80% de cuota de mercado, la bicicleta asistida se ha convertido en una necesidad de diseño logístico impuesta por las barreras geográficas y distancias periféricas (como los accesos a Parquesol o el Eje del Hospital Río Hortega).
* **Inteligencia Operativa:** La combinación de perfiles K-Means y simulaciones demuestra que la gestión de BIKI requiere estrategias de equilibrio dinámico y preventivo  en los nodos puente identificados antes de las horas punta.

## 🔮 Próximas líneas de investigación

* **Impacto por Expansión al Alfoz (Caso Zaratán):** Evaluar el impacto en el comportamiento de la red, simular la demanda potencial y trazar la ubicación óptima de nuevas estaciones ante la potencial integración de municipios del alfoz vallisoletano como Zaratán.
* **Elasticidad Oferta-Demanda Climatológica:** Cruzar variables meteorológicas históricas con las simulaciones de Montecarlo para refinar el cálculo de pérdida de disponibilidad de bicicletas en días de lluvia o heladas intensas.
