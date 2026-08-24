# Dataknow_caso_tecnico
Análisis y pronóstico de precios
Proyecto de análisis de datos enfocado en estudiar el comportamiento histórico de los precios de tres insumos y dos equipos, así como en generar pronósticos para apoyar la toma de decisiones.

Descripción
El proyecto parte de la necesidad de analizar la variación de los precios de ciertos equipos y determinar si existe alguna relación con los precios de diferentes insumos o materias primas.

El análisis incluye exploración y limpieza de datos, integración de series históricas, análisis de correlaciones, construcción de pronósticos y comparación de precios entre proveedores.

Objetivos
Analizar el comportamiento histórico de los precios.

Identificar posibles relaciones entre los insumos y los equipos.

Generar pronósticos para periodos posteriores.

Evaluar el desempeño de los modelos utilizados.

Comparar los precios de distintos proveedores.

Presentar los resultados mediante tablas y visualizaciones.

Flujo de trabajo
Carga de los archivos de datos.

Revisión de estructura, tipos de datos y valores faltantes.

Limpieza y transformación de la información.

Conversión y homologación de fechas.

Integración de las diferentes series de precios.

Análisis estadístico y de correlaciones.

Generación de pronósticos.

Evaluación mediante métricas de error.

Comparación entre precios reales, pronosticados y de proveedores.

Variables principales
Date: fecha del registro.

Price_X: precio del insumo X.

Price_Y: precio del insumo Y.

Price_Z: precio del insumo Z.

Price_Equipo1: precio del equipo 1.

Price_Equipo2: precio del equipo 2.

También se utilizan variables relacionadas con precios de proveedores, desviaciones e intervalos de confianza.

Modelado y evaluación
Se generaron pronósticos para los precios de los insumos y equipos. Para revisar el desempeño de los modelos se compararon los valores estimados contra los valores observados.

Las principales métricas consideradas fueron:

MSE: error cuadrático medio.

MAPE: error porcentual absoluto medio.

Desviación absoluta y porcentual.

El desempeño puede cambiar según el periodo analizado, por lo que los resultados deben interpretarse considerando el contexto de los datos y la disponibilidad de información histórica.

Tecnologías
Python

Jupyter Notebook

pandas

NumPy

matplotlib

seaborn

scikit-learn

TensorFlow/Keras

Estructura del repositorio
text
.
├── DataKnow_caso_tecnico.ipynb
├── README.md
└── datos/
La carpeta de datos puede variar dependiendo de la configuración del entorno de ejecución.

Instalación
Se recomienda utilizar un entorno virtual. Las principales dependencias pueden instalarse con:

bash
pip install pandas numpy matplotlib seaborn scikit-learn tensorflow jupyter
Uso
Clonar el repositorio:

bash
git clone <URL_DEL_REPOSITORIO>
cd <NOMBRE_DEL_REPOSITORIO>
Verificar las rutas de los archivos de entrada.

Abrir el notebook:

bash
jupyter notebook DataKnow_caso_tecnico.ipynb
Ejecutar las celdas en orden.

Consideraciones
Los resultados dependen de la calidad, formato y disponibilidad de los datos.

Las correlaciones encontradas representan relaciones estadísticas y no necesariamente causalidad.

Los pronósticos deben utilizarse como apoyo para el análisis, no como una garantía del comportamiento futuro.

Antes de utilizar el proyecto con información nueva, se recomienda actualizar las fuentes y validar nuevamente los modelos.

Resultados
El notebook permite obtener una visión general de la evolución de los precios, revisar las relaciones entre las variables, evaluar los pronósticos y comparar las propuestas de distintos proveedores.
