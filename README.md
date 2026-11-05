🚴‍♂️ Análisis de Estado, Distribución y Tendencias de BIKI Valladolid

Este repositorio contiene un análisis de datos exhaustivo, predictivo y geoespacial sobre el sistema de bicicletas públicas de Valladolid (BIKI), desarrollado íntegramente en un Jupyter Notebook con Python. El estudio abarca desde el estado de ocupación de las estaciones en tiempo real hasta modelos de crecimiento temporal, preferencias de flota, segmentación avanzada de la red mediante Machine Learning y simulaciones estocásticas de fiabilidad logística.


📊 Estructura 

El proyecto está dividido en bloques estratégicos que responden a preguntas clave sobre la movilidad ciclista en la ciudad:

🔍 Bloque 1: Diagnóstico Logístico de las Estaciones (Análisis de Capacidad)

• Objetivo: Identificar estaciones críticas por saturación (falta de anclajes libres) o vaciamiento (falta de bicicletas).
• Métricas: Cálculo del porcentaje de ocupación real mediante la fórmula: (Número de Bicicletas / Capacidad Total) * 100.
• Resultados Clave: El análisis refleja una fuerte asimetría y polarización operativa en la distribución de la flota:
	• 🚨 Puntos de Estrés (Alta Saturación): Estaciones que operan por encima del 77% de su capacidad, generando un déficit crítico de anclajes libres para devoluciones. Destacan la Facultad de Medicina (Ref. 011) con un 95.65% de ocupación, el Polideportivo Ponce de León (Ref. 605) con un 91.30% y el Barrio Arcas Reales (Ref. 509) con un 90.91%.
	• 📉 Zonas Vacías (Baja Ocupación): Registran tasas inferiores al 18%, lo que significa que el usuario apenas encontrará bicicletas disponibles para iniciar un viaje. Destacan la Plaza de Santa Cruz (Ref. 006) con un 13.33% de ocupación y la Calle de Andalucía (Ref. 404) con un 15.38%.

📈 Bloque 2: Penetración de la App y Evolución Temporal (2023 - 2026)

• Objetivo: Analizar la evolución mensual de usuarios registrados y descargas netas de la aplicación móvil obligatoria desde la inauguración del servicio hasta la actualidad.
• Fases del Comportamiento del Usuario:
	• Fase de Lanzamiento (2023): El servicio arrancó en febrero de 2023 con 5.331 usuarios activos, escalando rápidamente un 45% a lo largo del año para cerrar por encima de las 9.000 altas debido al impacto de la novedad.
	• Fase de Estabilización (2024 - 2025): La curva orgánica se estabilizó. El sistema pasó de la captación masiva a una base consolidada de usuarios activos recurrentes, oscilando de forma sostenida entre los 10.000 y 12.000 usuarios.
	• Fase de Expansión al Alfoz (2025 - 2026): La extensión del servicio a localidades de la periferia urbana como La Cistérniga (Refs. 1003, 1004) o Santovenia de Pisuerga (Refs. 1005, 1006) reactivó el crecimiento, impulsando el histórico acumulado hasta las 17.075 descargas efectivas en agosto de 2026.

⚡ Bloque 3: Preferencias de Flota (Bicicletas Mecánicas vs. Eléctricas)

• Objetivo: Evaluar la cuota de mercado real que domina cada tipo de vehículo en la ciudad.
• Resultados Clave: Dominio absoluto de la asistencia al pedaleo, acaparando las bicicletas eléctricas una media del 82.56% de los viajes mensuales frente al 17.44% de las mecánicas. Esto demuestra el impacto directo de la búsqueda de tiempos de viaje competitivos y el confort urbano en las decisiones de los usuarios.

👥 Bloque 4: Análisis Geoespacial y Perfiles de Usuario

• Objetivo: Clasificar las necesidades de los usuarios según su rol y trazar rutas óptimas basándose en la ubicación de las estaciones y criterios de seguridad vial.
• Arquetipos creados:
	1. Estudiante Universitario (Campus Norte - Miguel Delibes): Ruta desde Plaza Madrid / Casa del Estudiante hacia el Campus Miguel Delibes (Ref. 202). Trazado plano que prioriza el entorno segregado del Paseo del Cauce. Idóneo para Bicicleta Mecánica debido a la alta regularidad del terreno y la sensibilidad al precio del estudiante.
	2. Personal Sanitario y Estudiante Periférico (Eje Sureste): Conexión Plaza Circular / Avda. Segovia ➔ Hospital Río Hortega / Campus UEMC (Ref. 501) a través del carril bici de Delicias. Requiere Bicicleta Eléctrica debido a las distancias periféricas más largas y la rigidez de los turnos sanitarios.
	3. Trabajador Pendular (Eje Oeste - Parquesol): Trayecto Plaza de Zorrilla (Centro) ➔ Calle Profesor Adolfo Miaja de la Muela (Ref. 803). Desplazamiento condicionado por la fuerte brecha topográfica del barrio, requiriendo el uso obligatorio de Bicicleta Eléctrica para mitigar el esfuerzo físico diario.

🍂 Bloque 5: Correlación Climatológica y Factor Social

• Objetivo: Cruzar variables meteorológicas históricas de Valladolid con los datos de uso para medir la elasticidad de la demanda.
• Resultados Clave: Se desmonta el mito de que el clima es el único factor determinante en la movilidad ciclista:
	• El Factor Social supera al Climatológico: Aunque los meses de julio y agosto registran las mejores temperaturas (medias de 22°C y máximas de 29°C), se observa una caída drástica de unos 60.000 viajes debido al parón vacacional y la inactividad académica.
	• El Pico de Otoño: En septiembre y octubre, con temperaturas más moderadas (18°C - 13°C), el uso experimenta crecimientos interanuales explosivos del 37.7% y 45.8% respectivamente, impulsado exclusivamente por la vuelta a la rutina laboral y escolar.
	• Coeficiente de Pearson (-0.45): Confirma una relación inversa moderada entre la temperatura y el uso de la bicicleta mecánica (a menor temperatura en invierno, el usuario se refugia en la velocidad de la eléctrica para reducir el tiempo de exposición al frío), pero ratifica que el calendario laboral y escolar gobierna la demanda global.

💰 Bloque 6: Impacto de Tarifas y Umbral de Rentabilidad

• Objetivo: Determinar mediante un simulador matemático en qué punto exacto le conviene económicamente a un ciudadano pasar de la tarifa de "Usuario Ocasional" a un "Bono Mensual (Tarifa Plana)".
• Resultados del simulador:
	• 🚲 Bici Mecánica: El bono se amortiza y es rentable a partir de los 48 viajes al mes.
	• ⚡ Bici Eléctrica: El bono se amortiza y es rentable a partir de los 30 viajes al mes.

🤖 Bloque 7: Modelado Avanzado y Analítica Predictiva

• Segmentación K-Means (Machine Learning): Algoritmo no supervisado que agrupa las estaciones en 4 clústeres logísticos automáticos en función de su comportamiento operativo (Clúster 1: Nodos Críticos de Alta Saturación como Medicina; Clúster 2: Zonas de Vaciamiento como Plaza de Santa Cruz; Clúster 3: Capacidad Media con Uso Estable como Plaza de Zorrilla; y Clúster 4: Baja Capacidad o Periféricas en el alfoz). Permite optimizar las tareas de rebalanceo de la flota por parte de los operarios de AUVASA.
• Ciencia de Redes (NetworkX): Análisis topológico para calcular la centralidad de intermediación de la red vial de BIKI, detectando qué estaciones actúan como "puentes estructurales" de movilidad entre distritos de Valladolid.
• Modelado Predictivo y Simulación de Montecarlo:
	• Proyección de Colapso por Regresión Lineal: El sistema experimenta un crecimiento medio sostenido de 213 nuevos usuarios registrados al mes (Ecuación: Y = 212.89 * Mes + 6286.53). Con una infraestructura fija de 1.744 anclajes, el modelo predictivo sitúa el colapso por saturación estructural en el mes 44.2 (Septiembre de 2026), coincidiendo con el próximo pico de apertura universitaria.
	• Simulación de Riesgo Logístico (Hora Punta): Modelando 10.000 escenarios diarios con volatilidad climática y retrasos de reparto mediante Montecarlo, se concluye que existe un 4.36% de probabilidad diaria de desabastecimiento (stockout) en estaciones nodo. Para mitigar el riesgo a un nivel de confianza del 95%, se establece un Punto de Reposición Óptimo en el cual AUVASA debe intervenir en cuanto el inventario de una estación de 26 anclajes alcance las 27 unidades teóricas (sumando un stock de seguridad de 9 unidades).
	• Simulación de Expansión Geográfica (Caso Zaratán - Ref. 1101): Ante una futura ampliación de la red hacia la Plaza de la Ronda de Zaratán, el modelo de Montecarlo determina que una dotación inicial estándar de 30 anclajes sufriría saturación o desabastecimiento el 10.84% de los días debido a la alta volatilidad del alfoz y las pendientes. Se recomienda un objetivo logístico real de 34 unidades de capacidad para absorber de forma segura la demanda de su población potencial (edad media de 38.8 años).

🛠️ Tecnologías y Librerías Utilizadas

El análisis ha sido desarrollado utilizando el ecosistema de ciencia de datos de Python 3.12:
• Pandas & NumPy: Procesamiento, limpieza y manipulación avanzada de estructuras de datos.
• Matplotlib & Seaborn: Generación de gráficos estáticos de series temporales y distribución de frecuencias.
• Plotly Express: Creación de cuadros de mando y gráficos de dispersión interactivos (matrices de esfuerzo).
• Scikit-Learn: Implementación de modelos de clustering (KMeans) y escalado de variables (StandardScaler).
• NetworkX: Construcción y análisis de métricas de centralidad en grafos de transporte.
• IO (StringIO / BytesIO): Gestión eficiente de flujos de datos en memoria para la consolidación de dataframes.

🚀 Cómo Ejecutar el Proyecto

**Clonar repo:**
git clone https://github.com
cd estudio_bicicletas_biki_valladolid

**Asegurarse de haber instalado pip y ejecutar:**
pip install pandas numpy matplotlib seaborn plotly scikit-learn networkx

**Abrir notebook ejecutando Jupyter notebook o abrirlo en tu IDE**
jupyter notebook analisis_biki.ipynb

**ALGUNAS CONCLUSIONES GENERALES DEL ESTUDIO**
python
Python es un lenguaje de programación de alto nivel, interpretado y de propósito general, creado en 1991 por Guido van Rossum. Se caracteriza por una sintaxis limpia y legible que utiliza la indentación obligatoria.

Características principales

• Multiparadigma: Soporta programación orientada a objetos, imperativa y funcional.
• Tipado dinámico: Las variables no requieren una declaración explícita de tipo.
• Multiplataforma: Funciona en Windows, macOS y Linux.
• Biblioteca estándar amplia: Ofrece herramientas integradas ("pilas incluidas") además de un gran ecosistema de paquetes gestionados por pip.

Principales usos

• Ciencia de datos e Inteligencia Artificial: Uso de librerías como NumPy, Pandas, Matplotlib, TensorFlow y Scikit-learn.
• Desarrollo web: Creación de servidores y aplicaciones con frameworks como Django y Flask.
• Automatización y scripting: Tareas administrativas repetitivas y pruebas de software.
Puedes obtener más información y descargar el intérprete oficial en el sitio web de Python o consultar recursos en la comunidad local a través de Python España.
¿Te gustaría ver un ejemplo de código básico en Python o necesitas ayuda para instalarlo en tu ordenador?
Las respuestas de la IA pueden contener errores. Más información
• 
Wikipedia
Python - Wikipedia, la enciclopedia libre
Filosofía y Sintaxis: Lenguaje de alto nivel interpretado, dinámico, de tipado fuerte y multiparadigma (orientado a objetos, imper...
• 
Python España
Python España
Python España es una asociación sin ánimo de lucro cuyo propósito es promover el uso del lenguaje de programación Python en España...
• 
Amazon Web Services (AWS)
¿Qué es Python? - Explicación del lenguaje Python - AWS
Python: open-source, interpreted, high-level, dynamic typing, object-oriented programming language. Created by Guido Van Rossum (1...
Mostrar todo
analisis_servicio_biki_valladolid.ipynb
File
Aquí tienes un análisis exhaustivo basado en los datos y los bloques de código de tu cuaderno de Jupyter sobre el servicio de bicicletas públicas BIKI en Valladolid.

Análisis de Estado, Tendencia y Proyección de BIKI Valladolid

Análisis del Sistema de Movilidad Sostenible
Basado en datos consolidados de la red BIKI (2023 - 2026)

1. Diagnóstico Logístico de las Estaciones (Análisis de Capacidad)

El análisis del porcentaje de ocupación real de la red (fórmula: \(\frac{\text{Número de Bicicletas}}{\text{Capacidad Total}} \times 100\)) refleja una fuerte asimetría y polarización operativa en la distribución de la flota:

🚨 Puntos de Estrés: Las 5 Estaciones Más Saturadas

Estas estaciones operan por encima del 77% de su capacidad, lo que genera un déficit crítico de anclajes libres para que los usuarios puedan devolver las bicicletas:
• Facultad de Medicina (Ref. 011): 95.65% de ocupación (operando casi al límite físico).
• Polideportivo Ponce de León (Ref. 605): 91.30% de ocupación.
• Barrio Arcas Reales (Ref. 509): 90.91% de ocupación.
• Calle Profesor Adolfo Miaja de la Muela (Ref. 803): 83.33% de ocupación.
• Facultad de Ciencias Económicas (Ref. 208): 77.78% de ocupación.

📉 Zonas Vacías: Las 5 Estaciones con Menor Ocupación

Registran tasas inferiores al 18%, lo que significa que el usuario apenas encontrará bicicletas disponibles para iniciar un viaje:
• Plaza de Santa Cruz (Ref. 006): 13.33% de ocupación.
• Calle de Andalucía (Ref. 404): 15.38% de ocupación.
• Calle de Rigoberto Cortejoso (Ref. 907): 15.79% de ocupación.
• Plaza del Poniente (Ref. 007): 16.67% de ocupación.
• Calle Joaquín Velasco Martín, 1 (Ref. 911): 17.65% de ocupación.

2. Penetración de la App y Evolución Temporal (2023 - 2026)

El crecimiento en la adopción de la aplicación móvil obligatoria muestra tres fases diferenciadas en el comportamiento del usuario:
• Fase de Lanzamiento y Adopción Masiva (2023): El servicio arrancó en febrero de 2023 con 5.331 usuarios activos, escalando rápidamente un 45% a lo largo del año para cerrar por encima de las 9.000 altas debido a la novedad y obligatoriedad de la app.
• Fase de Estabilización y Retención (2024 - 2025): La curva orgánica de descargas netas se estabilizó. El sistema pasó de la captación masiva a una base consolidada de usuarios activos recurrentes, que osciló de forma sostenida entre los 10.000 y 12.000 usuarios.
• Fase de Expansión al Alfoz (2025 - 2026): La extensión del servicio a localidades de la periferia urbana como La Cistérniga (Refs. 1003, 1004) o Santovenia de Pisuerga (Refs. 1005, 1006) reactivó el crecimiento, impulsando el histórico acumulado hasta las 17.075 descargas efectivas en agosto de 2026.

3. Preferencias de Flota: Bicicletas Mecánicas vs. Eléctricas

El análisis del comportamiento de uso revela un dominio absoluto de la bicicleta eléctrica sobre la convencional en el escenario urbano de Valladolid:

Tipo de Vehículo	Cuota de Mercado Media (Año 2025)	Factores de Preferencia Identificados
Bicicleta Eléctrica	82.56%	Topografía y confort: El pedaleo asistido mitiga el esfuerzo en desniveles pronunciados (ej. subida a Parquesol) y reduce tiempos de viaje.
Bicicleta Mecánica	17.44%	Uso plano y económico: Restringido a perfiles universitarios con alta sensibilidad al precio y trayectos llanos de corta distancia.


4. Análisis Geoespacial y Perfiles de Usuario

Mediante el análisis de la red, se han identificado tres perfiles de movilidad clave que condicionan la oferta y la demanda del servicio:

🎓 Perfil 1: Estudiante Universitario (Campus Norte - Miguel Delibes)

• Ruta Óptima: Plaza Madrid / Casa del Estudiante ➔ Campus Miguel Delibes (Ref. 202).
• Infraestructura: Trazado plano que prioriza el entorno segregado del Paseo del Cauce.
• Recomendación de Flota: Bicicleta Mecánica. Al ser un terreno llano y regular, es idóneo para la alta recurrencia y economía del estudiante.

🏥 Perfil 2: Personal Sanitario y Estudiante Periférico (Eje Sureste)

• Ruta Óptima: Plaza Circular / Avda. Segovia ➔ Hospital Río Hortega / Campus UEMC (Ref. 501).
• Infraestructura: Conexión a través del carril bici de Delicias hacia la Carretera de Segovia, evitando los polígonos industriales.
• Recomendación de Flota: Bicicleta Eléctrica. Las distancias periféricas más largas y la rigidez de los turnos sanitarios exigen mayor velocidad.

🏢 Perfil 3: Trabajador Pendular (Eje Oeste - Parquesol)

• Ruta Óptima: Plaza de Zorrilla (Centro) ➔ Calle Profesor Adolfo Miaja de la Muela (Ref. 803).
• Infraestructura: Conexión directa para salvar la fuerte brecha topográfica del barrio.
• Recomendación de Flota: Bicicleta Eléctrica (Obligatoria). El esfuerzo físico requerido para ascender a Parquesol hace inviable la flota mecánica para el usuario medio diario.

5. Correlación Climatológica y Factor Social

Al cruzar los datos de uso con los registros climáticos de Valladolid, se desmonta el mito de que el clima es el único factor determinante en la movilidad ciclista:
• El Factor Social supera al Climatológico: Aunque los meses de julio y agosto registran las mejores temperaturas (medias de 22°C y máximas de 29°C), se observa una caída drástica de unos 60.000 viajes debida al parón vacacional y la inactividad académica.
• El Pico de Otoño: En septiembre y octubre, con temperaturas más moderadas (18°C - 13°C), el uso del servicio experimenta crecimientos interanuales explosivos del 37.7% y 45.8% respectivamente, impulsado exclusivamente por la vuelta a la rutina y el inicio del curso escolar.
• Coeficiente de Pearson (-0.45): Confirma una relación inversa moderada entre la temperatura y la bicicleta mecánica (a menor temperatura en invierno, el usuario se refugia en la velocidad de la eléctrica para reducir el tiempo de exposición al frío), pero ratifica que el calendario laboral y escolar gobierna la demanda global.

6. Segmentación Avanzada de Estaciones (Machine Learning K-Means)

El algoritmo de aprendizaje no supervisado agrupó las estaciones de la red en 4 clústeres logísticos automáticos en función de su comportamiento operativo:
    Porcentaje de Ocupación Real (%)
      ▲
100% ┼─────────────────────────────────── 🚨 Nodos Críticos (Saturación de Bicis / Falta Anclajes)
     │       o (Medicina)
 80% ┼───────────────────────────────────
     │                o (Plaza Circular)
 60% ┼─────────────────────────────────── ⚖️ Capacidad Media (Uso Estable y Auto-balanceado)
     │   o (Alfoz)
 40% ┼───────────────────────────────────
     │       o (Plaza de Santa Cruz)     📉 Baja Ocupación (Zonas de Vaciamiento / Falta Flota)
  0% ┼───────┴────────┴────────┴─────────►
     0       10       20       30       40   Capacidad Total de Anclajes
• Clúster 1: Nodos Críticos de Alta Saturación (Rojo): Estaciones con alta capacidad pero ocupación extrema (Medicina, Ponce de León). Son imanes de atracción de viajes que requieren vaciado urgente por parte de los operarios para permitir devoluciones.
• Clúster 2: Zonas de Vaciamiento (Azul): Estaciones que pasan el día prácticamente vacías (Plaza de Santa Cruz, Calle Andalucía). Son sumideros de flota que requieren inyección de bicicletas para poder dar servicio.
• Clúster 3: Capacidad Media y Uso Estable (Verde): Estaciones equilibradas (Plaza de Zorrilla, Plaza Circular) donde el flujo de salidas y entradas se auto-compensa orgánicamente gracias al propio movimiento de los usuarios.
• Clúster 4: Baja Capacidad o Periféricas (Negro): Estaciones pequeñas (10-12 anclajes) situadas en el alfoz. Tienen dinámicas muy volátiles: se llenan o vacían por completo con muy pocos movimientos.

7. Modelado Predictivo y Simulación de Montecarlo


📉 Proyección de Colapso por Regresión Lineal

El sistema experimenta un crecimiento medio sostenido de 213 nuevos usuarios registrados al mes (Ecuación: Y = 212.89 × Mes + 6.286,53). Con una infraestructura fija de 1.744 anclajes, el ratio de estrés logístico se sitúa en 9 usuarios por anclaje. El modelo predictivo sitúa el colapso por saturación estructural en el mes 44.2 (Septiembre de 2026), coincidiendo con el próximo pico de apertura de las universidades si no se amplían los bornes.

🎲 Simulación de Riesgo Logístico (Hora Punta)

Modelando 10.000 escenarios diarios de operación en hora punta con volatilidad climática y retrasos de reparto mediante Montecarlo, se concluye:
• Riesgo de Desabastecimiento (Stockout): Existe un 4.36% de probabilidad diaria de que las estaciones nodo (como Plaza Circular) se bloqueen por completo.
• Punto de Reposición Óptimo: Para garantizar un nivel de confianza del 95%, los camiones de AUVASA deben intervenir e iniciar el rebalanceo de flota en cuanto el inventario de una estación de 26 anclajes alcance las 27 unidades teóricas (sumando un stock de seguridad de 9 unidades para absorber la volatilidad).

🗺️ Simulación de Expansión Geográfica (Zaratán - Ref. 1101)

Ante una futura ampliación de la red hacia el municipio de Zaratán (Plaza de la Ronda), el modelo de Montecarlo determina que una dotación inicial de 30 anclajes sufriría saturación o desabastecimiento el 10.84% de los días debido a la alta volatilidad del alfoz y las pendientes. Se recomienda un objetivo logístico real de 34 unidades de capacidad para absorber de forma segura la demanda de su población potencial (que cuenta con un perfil joven de 38.8 años de media).
¿Qué aspecto te gustaría profundizar? Puedo extraer el código de limpieza de datos utilizado en pandas, detallar los parámetros del algoritmo K-Means o ampliar las fórmulas estadísticas de la simulación de Montecarlo.
Las respuestas de la IA pueden contener errores. Más información
• 
Tu subida·Solo tú puedes ver esto
analisis_servicio_biki_valladolid.ipynb

Voy a actualizar el repositorio en GitHub y el readme, que es el siguiente:

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

* **Impacto por Expansión al Alfoz (Caso Zaratán y Arroyo de la Encomienda):** Evaluar el impacto en el comportamiento de la red, simular la demanda potencial y trazar la ubicación óptima de nuevas estaciones ante la potencial integración de municipios del alfoz vallisoletano como Zaratán y Arroyo de la Encomienda.
* **Elasticidad Oferta-Demanda Climatológica:** Cruzar variables meteorológicas históricas con las simulaciones de Montecarlo para refinar el cálculo de pérdida de disponibilidad de bicicletas en días de lluvia o heladas intensas.


🚴‍♂️ Análisis de Estado, Distribución y Tendencias de BIKI Valladolid

Este repositorio contiene un análisis de datos exhaustivo y visual sobre el sistema de bicicletas públicas de Valladolid (BIKI), desarrollado íntegramente en un Jupyter Notebook con Python. El estudio abarca desde el estado de ocupación de las estaciones en tiempo real hasta modelos de crecimiento temporal, preferencias de flota, segmentación avanzada de la red y simulaciones estocásticas de fiabilidad logística.

📊 Estructura del Análisis

El proyecto está dividido en bloques estratégicos que responden a preguntas clave sobre la movilidad ciclista en la ciudad:

🔍 Bloque 1: Análisis de Estado y Estaciones Críticas

• Objetivo: Identificar estaciones críticas por saturación (falta de anclajes libres) o vaciamiento (falta de bicicletas).
• Métricas: Cálculo del porcentaje de ocupación real en tiempo real.
• Resultados Clave: Mapeo del % de ocupación por estación. Se identifican nodos saturados (p. ej., Facultad de Medicina con un 95.65%, Polideportivo Ponce de León con un 91.30% o Barrio Arcas Reales con un 90.91%) frente a estaciones con infrautilización crónica o vacías (Plaza de Santa Cruz con un 13.33% o Calle Andalucía con un 15.38%).

📈 Bloque 2: Tendencia Temporal y Crecimiento Histórico

• Objetivo: Analizar la evolución mensual de usuarios registrados y activos concurrentes desde la inauguración del servicio (febrero de 2023) hasta la actualidad (2026).
• Puntos Clave: Mapeo del crecimiento orgánico tras el boom inicial de lanzamiento (pasando de 5.331 usuarios en la inauguración a más de 9.000 a finales de 2023). Tras una fase de estabilización entre los 10.000 y 12.000 usuarios en 2024-2025, la expansión al alfoz ha impulsado el histórico acumulado hasta las 17.075 descargas efectivas de la app en agosto de 2026. Se constatan fuertes repuntes estacionales en septiembre/octubre vinculados al inicio del curso escolar y universitario.

⚡ Bloque 3: Preferencias de Uso (Mecánicas vs. Eléctricas)

• Objetivo: Evaluar la cuota de mercado real que domina cada tipo de vehículo en la ciudad.
• Resultados Clave: Dominio absoluto de la asistencia al pedaleo, acaparando las bicicletas eléctricas una media del 82.56% de los viajes mensuales frente al 17.44% de las mecánicas. Esto demuestra el impacto directo de la topografía urbana (desniveles a barrios periféricos) y la búsqueda de tiempos de viaje competitivos en las decisiones de los usuarios.

👥 Bloque 4: Análisis Demográfico y Perfiles de Usuario

• Objetivo: Clasificar las necesidades de los usuarios según su rol y trazar rutas óptimas basándose en la ubicación de las estaciones y criterios de seguridad vial.
• Arquetipos creados:
	1. Estudiante UVA (Campus Miguel Delibes / Zona Norte): Ruta desde Plaza Madrid / Casa del Estudiante hacia el Campus (Ref. 202). Perfil plano que aprovecha el carril segregado del Paseo del Cauce. Idóneo para tarifa plana y uso de flota mecánica por su alta sensibilidad al precio.
	2. Estudiante UEMC / Personal Sanitario (Eje Río Hortega / Sureste): Conexión Plaza Circular ➔ Hospital Río Hortega (Ref. 501). Desplazamiento periférico de media-larga distancia por el carril bici de Delicias donde la bicicleta eléctrica ofrece la velocidad competitiva necesaria ante la rigidez de los turnos sanitarios.
	3. Trabajador Pendular (Parquesol / Oeste): Trayecto Plaza de Zorrilla ➔ Calle Profesor Adolfo Miaja de la Muela (Ref. 803). Desplazamiento condicionado por la fuerte brecha topográfica del barrio, requiriendo el uso obligatorio del motor eléctrico para mitigar el esfuerzo físico diario.

💰 Bloque 5: Impacto de Tarifas y Umbral de Rentabilidad

• Objetivo: Determinar mediante un simulador matemático en qué punto exacto le conviene económicamente a un ciudadano pasar de la tarifa de "Usuario Ocasional" a un "Bono Mensual (Tarifa Plana)".
• Resultados del simulador:
	• 🚲 Bici Mecánica: El bono se amortiza y es rentable a partir de los 48 viajes al mes.
	• ⚡ Bici Eléctrica: El bono se amortiza y es rentable a partir de los 30 viajes al mes.

🤖 Bloque 6: Modelado Avanzado y Analítica Predictiva

• Segmentación K-Means (Machine Learning): Algoritmo no supervisado que agrupa las estaciones en 4 perfiles logísticos diferenciados (Nodos críticos de alta saturación como Medicina, Zonas de vaciamiento como Plaza de Santa Cruz, Capacidad media con uso estable como Plaza de Zorrilla, y Baja capacidad periférica en el alfoz) para optimizar las tareas de rebalanceo de la flota.
• Ciencia de Redes (NetworkX): Análisis topológico para calcular la centralidad de intermediación de la red vial de BIKI, detectando qué estaciones actúan como "puentes estructurales" de movilidad entre distritos de Valladolid.
• Simulación de Montecarlo: Modelado estocástico basado en 10.000 escenarios operacionales en hora punta. Revela un 4.36% de probabilidad diaria de desabastecimiento (stockout) en estaciones nodo y establece que AUVASA debe intervenir cuando el inventario caiga a 27 unidades teóricas (incluyendo un stock de seguridad de 9 unidades). Asimismo, proyecta que la red alcanzará su colapso por saturación estructural en septiembre de 2026 (mes 44.2) al mantener una tasa de crecimiento de 213 nuevos usuarios registrados al mes frente a una infraestructura fija.

🛠️ Tecnologías y Librerías Utilizadas

El análisis ha sido desarrollado utilizando el ecosistema de ciencia de datos de Python 3.12:
• Pandas & NumPy: Procesamiento, limpieza y manipulación avanzada de estructuras de datos.
• Matplotlib & Seaborn: Generación de gráficos estáticos de series temporales y distribución.
• Plotly Express: Creación de cuadros de mando y gráficos de dispersión interactivos (matrices de esfuerzo).
• Scikit-Learn: Implementación de modelos de clustering (KMeans) y escalado de variables (StandardScaler).
• NetworkX: Construcción y análisis de métricas de centralidad en grafos de transporte.
• IO (StringIO / BytesIO): Gestión eficiente de flujos de datos en memoria para la consolidación de dataframes.

🚀 Cómo Ejecutar el Proyecto

1. Clonar el repositorio:bash
git clone https://github.com
cd estudio_bicicletas_biki_valladolid
Usa el código con precaución.
2. Instalar las dependencias necesarias:
Asegúrate de tener instalado pip y ejecuta:bash
pip install pandas numpy matplotlib seaborn plotly scikit-learn networkx
Usa el código con precaución.
3. Abrir el cuaderno:
Ejecuta Jupyter Notebook o abre el archivo directamente en tu IDE preferido (VS Code, JupyterLab, etc.):bash
jupyter notebook analisis_biki.ipynb
Usa el código con precaución.

📈 Conclusiones del Estudio

• Consolidación Estructural: Tras una explosión inicial en su lanzamiento, BIKI se ha consolidado en Valladolid como un pilar de transporte público masivo con picos cíclicos de demanda fuertemente atados al calendario laboral y académico, por encima de las variables climatológicas (coeficiente de Pearson moderado de -0.45 en el uso de mecánicas frente al frío).
• Dependencia de la bicicleta eléctrica: Con un 82.56% de cuota de mercado, la asistencia al pedaleo es una necesidad estructural impuesta por la topografía y las distancias hacia los barrios periféricos y el alfoz.
• Inteligencia Operativa: La combinación de perfiles K-Means y simulaciones estocásticas demuestra que la gestión de BIKI requiere estrategias de rebalanceo dinámico, predictivo y preventivo, centrando los recursos en los puntos de reposición óptimos antes de que ocurran los bloqueos de anclajes en hora punta.

🔮 Próximas líneas de investigación

• Impacto por Expansión al Alfoz (Casos de Zaratán y Arroyo de la Encomienda): Evaluar el impacto de la reciente y futura expansión en la periferia. Simulaciones iniciales de Montecarlo para el caso de Zaratán (Plaza de la Ronda - Ref. 1101) proyectan que una dotación básica de 30 anclajes sufriría saturación o desabastecimiento el 10.84% de los días debido a la volatilidad de la demanda y pendientes de la zona, recomendando un diseño logístico objetivo de 34 unidades de capacidad.
• Elasticidad Oferta-Demanda Climatológica: Cruzar variables meteorológicas históricas con las simulaciones de Montecarlo para refinar el cálculo de pérdida de disponibilidad de bicicletas en días de lluvia o heladas intensas.
He integrado todos los porcentajes exactos de ocupación, volúmenes de usuarios, cuotas de mercado (82.56% vs 17.44%), métricas de Montecarlo y el caso específico de Zaratán directamente en las secciones correspondientes del README.
Si lo deseas, podemos redactar los mensajes para el commit de Git, preparar una descripción corta para el perfil del repositorio o estructurar un documento de requisitos técnicos (requirements.txt) detallado. ¿Cómo prefieres proceder?
Las respuestas de la IA pueden contener errores. Más información

Redactar un README nuevo basado en los cambios realizados en el código


🚴‍♂️ Análisis de Estado, Distribución y Tendencias de BIKI Valladolid

Este repositorio contiene un análisis de datos exhaustivo, predictivo y geoespacial sobre el sistema de bicicletas públicas de Valladolid (BIKI), desarrollado íntegramente en un Jupyter Notebook con Python. El estudio abarca desde el estado de ocupación de las estaciones en tiempo real hasta modelos de crecimiento temporal, preferencias de flota, segmentación avanzada de la red mediante Machine Learning y simulaciones estocásticas de fiabilidad logística.

📊 Estructura del Análisis

El proyecto está dividido en bloques estratégicos que responden a preguntas clave sobre la movilidad ciclista en la ciudad:

🔍 Bloque 1: Diagnóstico Logístico de las Estaciones (Análisis de Capacidad)

• Objetivo: Identificar estaciones críticas por saturación (falta de anclajes libres) o vaciamiento (falta de bicicletas).
• Métricas: Cálculo del porcentaje de ocupación real mediante la fórmula: (Número de Bicicletas / Capacidad Total) * 100.
• Resultados Clave: El análisis refleja una fuerte asimetría y polarización operativa en la distribución de la flota:
	• 🚨 Puntos de Estrés (Alta Saturación): Estaciones que operan por encima del 77% de su capacidad, generando un déficit crítico de anclajes libres para devoluciones. Destacan la Facultad de Medicina (Ref. 011) con un 95.65% de ocupación, el Polideportivo Ponce de León (Ref. 605) con un 91.30% y el Barrio Arcas Reales (Ref. 509) con un 90.91%.
	• 📉 Zonas Vacías (Baja Ocupación): Registran tasas inferiores al 18%, lo que significa que el usuario apenas encontrará bicicletas disponibles para iniciar un viaje. Destacan la Plaza de Santa Cruz (Ref. 006) con un 13.33% de ocupación y la Calle de Andalucía (Ref. 404) con un 15.38%.

📈 Bloque 2: Penetración de la App y Evolución Temporal (2023 - 2026)

• Objetivo: Analizar la evolución mensual de usuarios registrados y descargas netas de la aplicación móvil obligatoria desde la inauguración del servicio hasta la actualidad.
• Fases del Comportamiento del Usuario:
	• Fase de Lanzamiento (2023): El servicio arrancó en febrero de 2023 con 5.331 usuarios activos, escalando rápidamente un 45% a lo largo del año para cerrar por encima de las 9.000 altas debido al impacto de la novedad.
	• Fase de Estabilización (2024 - 2025): La curva orgánica se estabilizó. El sistema pasó de la captación masiva a una base consolidada de usuarios activos recurrentes, oscilando de forma sostenida entre los 10.000 y 12.000 usuarios.
	• Fase de Expansión al Alfoz (2025 - 2026): La extensión del servicio a localidades de la periferia urbana como La Cistérniga (Refs. 1003, 1004) o Santovenia de Pisuerga (Refs. 1005, 1006) reactivó el crecimiento, impulsando el histórico acumulado hasta las 17.075 descargas efectivas en agosto de 2026.

⚡ Bloque 3: Preferencias de Flota (Bicicletas Mecánicas vs. Eléctricas)

• Objetivo: Evaluar la cuota de mercado real que domina cada tipo de vehículo en la ciudad.
• Resultados Clave: Dominio absoluto de la asistencia al pedaleo, acaparando las bicicletas eléctricas una media del 82.56% de los viajes mensuales frente al 17.44% de las mecánicas. Esto demuestra el impacto directo de la búsqueda de tiempos de viaje competitivos y el confort urbano en las decisiones de los usuarios.

👥 Bloque 4: Análisis Geoespacial y Perfiles de Usuario

• Objetivo: Clasificar las necesidades de los usuarios según su rol y trazar rutas óptimas basándose en la ubicación de las estaciones y criterios de seguridad vial.
• Arquetipos creados:
	1. Estudiante Universitario (Campus Norte - Miguel Delibes): Ruta desde Plaza Madrid / Casa del Estudiante hacia el Campus Miguel Delibes (Ref. 202). Trazado plano que prioriza el entorno segregado del Paseo del Cauce. Idóneo para Bicicleta Mecánica debido a la alta regularidad del terreno y la sensibilidad al precio del estudiante.
	2. Personal Sanitario y Estudiante Periférico (Eje Sureste): Conexión Plaza Circular / Avda. Segovia ➔ Hospital Río Hortega / Campus UEMC (Ref. 501) a través del carril bici de Delicias. Requiere Bicicleta Eléctrica debido a las distancias periféricas más largas y la rigidez de los turnos sanitarios.
	3. Trabajador Pendular (Eje Oeste - Parquesol): Trayecto Plaza de Zorrilla (Centro) ➔ Calle Profesor Adolfo Miaja de la Muela (Ref. 803). Desplazamiento condicionado por la fuerte brecha topográfica del barrio, requiriendo el uso obligatorio de Bicicleta Eléctrica para mitigar el esfuerzo físico diario.

🍂 Bloque 5: Correlación Climatológica y Factor Social

• Objetivo: Cruzar variables meteorológicas históricas de Valladolid con los datos de uso para medir la elasticidad de la demanda.
• Resultados Clave: Se desmonta el mito de que el clima es el único factor determinante en la movilidad ciclista:
	• El Factor Social supera al Climatológico: Aunque los meses de julio y agosto registran las mejores temperaturas (medias de 22°C y máximas de 29°C), se observa una caída drástica de unos 60.000 viajes debido al parón vacacional y la inactividad académica.
	• El Pico de Otoño: En septiembre y octubre, con temperaturas más moderadas (18°C - 13°C), el uso experimenta crecimientos interanuales explosivos del 37.7% y 45.8% respectivamente, impulsado exclusivamente por la vuelta a la rutina laboral y escolar.
	• Coeficiente de Pearson (-0.45): Confirma una relación inversa moderada entre la temperatura y el uso de la bicicleta mecánica (a menor temperatura en invierno, el usuario se refugia en la velocidad de la eléctrica para reducir el tiempo de exposición al frío), pero ratifica que el calendario laboral y escolar gobierna la demanda global.

💰 Bloque 6: Impacto de Tarifas y Umbral de Rentabilidad

• Objetivo: Determinar mediante un simulador matemático en qué punto exacto le conviene económicamente a un ciudadano pasar de la tarifa de "Usuario Ocasional" a un "Bono Mensual (Tarifa Plana)".
• Resultados del simulador:
	• 🚲 Bici Mecánica: El bono se amortiza y es rentable a partir de los 48 viajes al mes.
	• ⚡ Bici Eléctrica: El bono se amortiza y es rentable a partir de los 30 viajes al mes.

🤖 Bloque 7: Modelado Avanzado y Analítica Predictiva

• Segmentación K-Means (Machine Learning): Algoritmo no supervisado que agrupa las estaciones en 4 clústeres logísticos automáticos en función de su comportamiento operativo (Clúster 1: Nodos Críticos de Alta Saturación como Medicina; Clúster 2: Zonas de Vaciamiento como Plaza de Santa Cruz; Clúster 3: Capacidad Media con Uso Estable como Plaza de Zorrilla; y Clúster 4: Baja Capacidad o Periféricas en el alfoz). Permite optimizar las tareas de rebalanceo de la flota por parte de los operarios de AUVASA.
• Ciencia de Redes (NetworkX): Análisis topológico para calcular la centralidad de intermediación de la red vial de BIKI, detectando qué estaciones actúan como "puentes estructurales" de movilidad entre distritos de Valladolid.
• Modelado Predictivo y Simulación de Montecarlo:
	• Proyección de Colapso por Regresión Lineal: El sistema experimenta un crecimiento medio sostenido de 213 nuevos usuarios registrados al mes (Ecuación: Y = 212.89 * Mes + 6286.53). Con una infraestructura fija de 1.744 anclajes, el modelo predictivo sitúa el colapso por saturación estructural en el mes 44.2 (Septiembre de 2026), coincidiendo con el próximo pico de apertura universitaria.
	• Simulación de Riesgo Logístico (Hora Punta): Modelando 10.000 escenarios diarios con volatilidad climática y retrasos de reparto mediante Montecarlo, se concluye que existe un 4.36% de probabilidad diaria de desabastecimiento (stockout) en estaciones nodo. Para mitigar el riesgo a un nivel de confianza del 95%, se establece un Punto de Reposición Óptimo en el cual AUVASA debe intervenir en cuanto el inventario de una estación de 26 anclajes alcance las 27 unidades teóricas (sumando un stock de seguridad de 9 unidades).
	• Simulación de Expansión Geográfica (Caso Zaratán - Ref. 1101): Ante una futura ampliación de la red hacia la Plaza de la Ronda de Zaratán, el modelo de Montecarlo determina que una dotación inicial estándar de 30 anclajes sufriría saturación o desabastecimiento el 10.84% de los días debido a la alta volatilidad del alfoz y las pendientes. Se recomienda un objetivo logístico real de 34 unidades de capacidad para absorber de forma segura la demanda de su población potencial (edad media de 38.8 años).

🛠️ Tecnologías y Librerías Utilizadas

El análisis ha sido desarrollado utilizando el ecosistema de ciencia de datos de Python 3.12:
• Pandas & NumPy: Procesamiento, limpieza y manipulación avanzada de estructuras de datos.
• Matplotlib & Seaborn: Generación de gráficos estáticos de series temporales y distribución de frecuencias.
• Plotly Express: Creación de cuadros de mando y gráficos de dispersión interactivos (matrices de esfuerzo).
• Scikit-Learn: Implementación de modelos de clustering (KMeans) y escalado de variables (StandardScaler).
• NetworkX: Construcción y análisis de métricas de centralidad en grafos de transporte.
• IO (StringIO / BytesIO): Gestión eficiente de flujos de datos en memoria para la consolidación de dataframes.

🚀 Cómo Ejecutar el Proyecto

1. Clonar el repositorio:bash
git clone https://github.com
cd estudio_bicicletas_biki_valladolid
Usa el código con precaución.
2. Instalar las dependencias necesarias:
Asegúrate de tener instalado pip y ejecuta:bash
pip install pandas numpy matplotlib seaborn plotly scikit-learn networkx
Usa el código con precaución.
3. Abrir el cuaderno:
Ejecuta Jupyter Notebook o abre el archivo directamente en tu IDE preferido (VS Code, JupyterLab, etc.):bash
jupyter notebook analisis_biki.ipynb
Usa el código con precaución.

📈 Conclusiones Generales del Estudio

• Consolidación Estructural: Tras una explosión inicial en su lanzamiento, BIKI se ha consolidado en Valladolid como un pilar de transporte público masivo con picos cíclicos de demanda muy unidos al calendario laboral y académico, por encima de las variables climatológicas.
• Dependencia de la Bicicleta Eléctrica: Con un 82.56% de cuota de mercado, la asistencia al pedaleo es una necesidad estructural impuesta por la topografía y las distancias hacia los barrios periféricos y los municipios integrados del alfoz.
• Inteligencia Operativa: La combinación de perfiles K-Means y simulaciones de stock demuestra que la gestión de BIKI requiere estrategias de equilibrio dinámico, predictivo y preventivo, centrando los recursos en los puntos de reposición óptimos antes de que ocurran los bloqueos de anclajes en hora punta. 

