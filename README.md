# Análisis de Churn en Servicios de Telecomunicaciones

## 🚀 Visión General del Proyecto

Este proyecto tiene como objetivo analizar el problema de la evasión de clientes (Churn) en una empresa de telecomunicaciones. La evasión de clientes es un desafío crítico que impacta directamente en los ingresos y la sostenibilidad de cualquier negocio. A través del análisis de datos de clientes, buscamos identificar patrones y características clave de aquellos clientes que deciden abandonar el servicio, con el fin de desarrollar estrategias efectivas de retención.

## ⚙️ Estructura del Repositorio

Este repositorio contiene el código y los resultados del análisis de Churn, incluyendo:

*   **`TelecomX_Data.json`**: El conjunto de datos original utilizado para el análisis.
*   **`notebook.ipynb`**: El Jupyter Notebook que contiene todo el proceso de extracción, transformación, carga, análisis exploratorio de datos y el informe final.

## 🧹 Limpieza y Tratamiento de Datos

El proceso de preparación de los datos fue fundamental para garantizar la calidad y consistencia del análisis. Los pasos clave incluyeron:

1.  **Carga de Datos**: El archivo `TelecomX_Data.json` fue cargado en un DataFrame de pandas.
2.  **Normalización de Estructuras Anidadas**: Las columnas con datos anidados ('customer', 'phone', 'internet', 'account') fueron normalizadas para expandir sus sub-atributos en el DataFrame principal (`df_norm`).
3.  **Manejo de Inconsistencias en 'Churn'**: Se identificaron y trataron valores inconsistentes (`''`) en la columna 'Churn', reemplazándolos por `NaN` y eliminando las filas correspondientes.
4.  **Creación de 'Cuentas_Diarias'**: Se añadió una nueva columna calculando los cargos diarios (`Charges.Monthly` / 30).
5.  **Conversión de Tipo de Datos**: La columna 'Charges.Total' fue convertida de `object` a `float64`, manejando posibles errores de conversión.

## 📊 Análisis Exploratorio de Datos (EDA)

Se realizó un extenso Análisis Exploratorio de Datos para comprender la distribución de las variables y su relación con el Churn. Las visualizaciones clave revelaron lo siguiente:

### Distribución General de Clientes por Churn

*   Aproximadamente el 26.5% de los clientes han abandonado el servicio, lo que subraya la importancia de este análisis de retención.

### Distribución de Churn por Género

*   No se observaron diferencias significativas en la tasa de Churn entre géneros, indicando que este no es un factor determinante.

### Distribución de Churn por Tipo de Contrato

*   Los clientes con contratos **mes a mes** (`Month-to-month`) muestran una tasa de Churn considerablemente más alta en comparación con aquellos que tienen contratos de uno o dos años. Esto sugiere una mayor lealtad entre los clientes con compromisos a largo plazo.

### Distribución de Churn por Método de Pago

*   Los clientes que utilizan **'Electronic check'** como método de pago presentan una tasa de Churn notablemente superior. Esto podría estar relacionado con la facilidad para cambiar de proveedor o la insatisfacción con el servicio que los lleva a tomar decisiones rápidas.

### Distribución de Churn por Total Gastado (Charges.Total)

*   Los clientes que finalmente churnean tienden a tener un **'Total Gastado'** menor en promedio, lo que podría indicar que aquellos con un bajo gasto total son más propensos a irse.

### Distribución de Churn por Tiempo de Contrato (Tenure)

*   Existe una clara relación inversa entre el tiempo de contrato (`tenure`) y el Churn. Los clientes con **menor tiempo de contrato** son significativamente más propensos a abandonar el servicio, mientras que aquellos con una larga permanencia muestran una tasa de Churn mucho más baja. Esto destaca la importancia de la fidelización en las etapas iniciales del ciclo de vida del cliente.

## 💡 Conclusiones e Insights Clave

*   **Contratos a Corto Plazo**: Los contratos flexibles (mes a mes) son un factor de riesgo significativo para el Churn.
*   **Método de Pago 'Electronic Check'**: Este método de pago está fuertemente asociado con una mayor propensión a la evasión.
*   **Importancia del 'Tenure'**: Los primeros meses de servicio son críticos para la retención, ya que los clientes nuevos son los más vulnerables.
*   **Gasto Total**: Un bajo gasto total podría ser un indicador de insatisfacción o menor compromiso con el servicio.
*   **Género Neutral**: El género no influye de manera relevante en la decisión de churn.

Estos hallazgos sugieren que las estrategias de retención deben ser focalizadas, prestando especial atención a los clientes en sus primeras etapas y a aquellos con métodos de pago menos vinculantes.

## 📈 Recomendaciones Estratégicas

Basado en el análisis realizado, se proponen las siguientes estrategias para mitigar el Churn:

1.  **Programas de Lealtad para Contratos Flexibles**: Ofrecer incentivos atractivos (descuentos, beneficios exclusivos) a clientes con contratos mes a mes para fomentar su migración a planes de mayor duración.
2.  **Monitoreo Proactivo de Clientes con 'Electronic Check'**: Implementar un seguimiento personalizado para este segmento, incluyendo encuestas de satisfacción o campañas de retención específicas.
3.  **Estrategias de Retención Temprana**: Desarrollar programas de bienvenida robustos y campañas de fidelización intensivas durante los primeros 6 a 12 meses de servicio, cuando el riesgo de Churn es más alto.
4.  **Optimización de Ofertas para Clientes de Bajo Gasto**: Investigar si los clientes con un bajo 'Charges.Total' perciben un menor valor del servicio y adaptar planes o promociones para satisfacer mejor sus necesidades.
5.  **Mejora Continua de la Experiencia del Cliente**: Mantener una excelente atención al cliente y garantizar la resolución eficiente de problemas para fomentar la satisfacción general, un pilar fundamental para la retención.

---
