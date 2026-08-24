# Análisis final

## Selección del modelo

Para el pronóstico de los precios se seleccionó una red neuronal LSTM (*Long Short-Term Memory*), debido a que las series analizadas presentan fluctuaciones y variaciones importantes a lo largo del tiempo. Este tipo de red permite trabajar con información secuencial y conservar patrones relevantes de observaciones anteriores, por lo que resulta una alternativa adecuada para explorar la dinámica temporal de los precios.

La elección de LSTM debe entenderse como una decisión metodológica para este ejercicio y no como una afirmación de que sea el único modelo apropiado. Antes de utilizarlo en un entorno productivo sería conveniente compararlo con otros métodos de series de tiempo y validar su desempeño bajo diferentes configuraciones.

## Ventanas de entrenamiento

Se exploraron ventanas de entrenamiento de 2, 3 y 5 años de información histórica. Esta comparación permitió revisar cómo influye la cantidad de datos utilizada en la capacidad del modelo para representar el comportamiento de los precios.

De las alternativas evaluadas, la ventana de 5 años presentó el ajuste más consistente con los valores observados en el periodo de validación. Por esta razón, se tomó como referencia para generar los pronósticos finales del ejercicio. Sin embargo, esta selección debe seguir validándose con nuevos periodos, diferentes semillas aleatorias y una búsqueda más amplia de hiperparámetros.

## Horizonte de pronóstico

Se definió un horizonte operativo de 30 días. La finalidad es contar con una estimación de corto plazo que pueda apoyar la toma de decisiones cuando exista la necesidad de adquirir alguno de los dos equipos durante el mes siguiente.

Adicionalmente, se generó una proyección para todo el año. Esta proyección no se plantea como una predicción exacta de cada precio diario, sino como una referencia general para observar tendencias y localizar periodos potencialmente más convenientes para realizar una compra.

El uso de ambos horizontes permite separar dos necesidades distintas:

- El pronóstico de 30 días sirve como apoyo para decisiones inmediatas.
- El pronóstico anual ayuda a elaborar una planeación general de compras.

## Resultados observados

Las visualizaciones sugieren que el comportamiento de los precios de los equipos converge de manera aproximada entre junio y julio en los distintos años analizados. Este patrón puede considerarse una señal exploratoria de estabilidad relativa y, por lo tanto, representa una ventana que podría ser conveniente revisar para la planeación de compras.

Con base en este resultado, la recomendación inicial es planear, cuando las condiciones operativas lo permitan, la adquisición de la mayoría de los equipos entre junio y julio. Esta recomendación no debe aplicarse de manera automática, ya que también deben revisarse la disponibilidad, las condiciones de los proveedores, el presupuesto y cualquier cambio reciente en los precios.

## Evaluación del modelo

El modelo se evaluó mediante métricas como MSE y MAPE, tanto para los insumos como para los equipos estimados a partir de las ecuaciones de regresión. La evaluación por año y por día permite identificar que el desempeño no es uniforme en todo el periodo: los errores pueden aumentar durante etapas de mayor volatilidad o cambios bruscos.

Por este motivo, no es suficiente reportar una sola métrica global. Es recomendable observar la evolución temporal del error y revisar si el modelo mantiene un comportamiento aceptable en los periodos más recientes, que son los más importantes para la toma de decisiones.

## Limitaciones

- El análisis se realizó con las variables históricas disponibles.
- La cantidad y calidad de las observaciones pueden limitar la capacidad de generalización.
- El modelo LSTM utiliza principalmente el comportamiento pasado de las series y no incorpora todos los factores externos que pueden afectar los precios.
- La convergencia observada entre junio y julio es un hallazgo exploratorio, no una garantía de que los precios serán menores en todos los años.
- Los pronósticos deben interpretarse como apoyo para la planeación y no como valores definitivos de compra.
- La evaluación debe complementarse con nuevos datos conforme estén disponibles.

## Trabajo futuro

Como siguientes pasos se propone:

1. Continuar evaluando las métricas MSE, MAPE y otras métricas complementarias en periodos recientes.
2. Probar distintas arquitecturas LSTM y ajustar hiperparámetros como número de capas, unidades, épocas, tamaño de lote y longitud de la secuencia.
3. Comparar LSTM con modelos estadísticos y de aprendizaje automático, por ejemplo, modelos estacionales, regresión, Random Forest, XGBoost y otras arquitecturas recurrentes.
4. Incorporar variables adicionales, como indicadores económicos, tipo de cambio, inflación, costos logísticos, disponibilidad, estacionalidad y características de los proveedores.
5. Utilizar validación temporal o *walk-forward validation* para evitar evaluaciones que no respeten el orden cronológico.
6. Generar intervalos de predicción para comunicar también la incertidumbre de cada pronóstico.
7. Automatizar la actualización de datos, el reentrenamiento y la generación de reportes para su uso en Power BI o en una base de datos.
8. Definir criterios de decisión que combinen el precio pronosticado con presupuesto, inventario, urgencia y condiciones comerciales.

## Comentario metodológico

La implementación de LSTM también estuvo relacionada con la experiencia previa adquirida trabajando con este tipo de modelo. Esto permitió avanzar de forma más eficiente en el desarrollo del caso y concentrar el esfuerzo en la integración de datos, el pronóstico rodante y la evaluación de resultados.

No obstante, la experiencia previa fue un factor práctico para seleccionar el modelo, no una validación suficiente de su superioridad. Como parte de una versión posterior del proyecto, sería importante realizar una comparación sistemática contra otros enfoques y seleccionar el modelo final con base en una validación temporal y criterios de desempeño definidos previamente.

Alcance y experiencia adicional
No cuento con experiencia práctica previa en la implementación de agentes de inteligencia artificial. Sin embargo, conozco sus generalidades, sus componentes principales y el tipo de flujo que normalmente puede utilizarse para integrar modelos, herramientas, memoria y procesos de decisión.

Decidí no incorporar agentes de inteligencia artificial como un componente adicional del proyecto, ya que no los he utilizado directamente en un desarrollo anterior ni formaban parte del flujo que fue implementado y validado en este ejercicio. Preferí mantener el análisis enfocado en las actividades que sí fueron realizadas: integración y limpieza de datos, análisis exploratorio, modelado, pronóstico, evaluación de métricas y generación de resultados.

La misma consideración aplica para el diagrama de arquitectura o flujo. Tengo una idea general de cómo podría estructurarse una solución de este tipo; sin embargo, no quise presentar un diagrama como si representara una implementación ya realizada cuando únicamente se trata de una propuesta conceptual.

Considero importante distinguir entre los conocimientos generales y la experiencia práctica. Por esta razón, cualquier incorporación de agentes de IA o de una arquitectura más completa se plantea como una posible línea de trabajo futuro. En una siguiente etapa sería posible diseñar el flujo, seleccionar las herramientas, implementar un prototipo y evaluar su funcionamiento con un caso controlado.

Esta decisión busca mantener la trazabilidad y honestidad técnica del proyecto: los elementos presentados corresponden a procesos que fueron efectivamente desarrollados, ejecutados o evaluados, mientras que los componentes no implementados se señalan como oportunidades de mejora y no como resultados del trabajo actual.

## Conclusión

El análisis permitió integrar información histórica de insumos y equipos, explorar sus relaciones, generar pronósticos de corto y mediano plazo y establecer una primera referencia para la planeación de compras.

La ventana de entrenamiento de 5 años fue la que mostró el ajuste más adecuado dentro de las alternativas revisadas. El horizonte de 30 días resulta útil para atender necesidades inmediatas, mientras que la proyección anual permite observar tendencias generales. De acuerdo con las visualizaciones, junio y julio aparecen como un periodo relativamente estable para considerar la compra de equipos.

Como resultado final, se recomienda utilizar el modelo como una herramienta de apoyo y continuar validándolo con nuevos datos, más variables y comparaciones contra otros modelos de pronóstico.
