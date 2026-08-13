# Proyecto Final Sprint 7 - Análisis de Clientes ConnectaTel

## 📊 Descripción

Este proyecto tiene como objetivo analizar el comportamiento de los clientes de ConnectaTel, una empresa de telecomunicaciones con operaciones en México y Colombia.

El análisis busca identificar patrones de uso de llamadas y mensajes, segmentar clientes, detectar valores atípicos y generar recomendaciones comerciales que permitan mejorar la oferta de planes y la experiencia de los usuarios.

## 🎯 Objetivos

- Explorar y limpiar los datos de clientes, planes y uso.
- Identificar problemas de calidad de datos.
- Analizar el comportamiento de llamadas y mensajes.
- Detectar valores atípicos mediante boxplots y el método IQR.
- Segmentar clientes por edad y nivel de uso.
- Identificar oportunidades comerciales.
- Generar recomendaciones basadas en datos.

## 📂 Datasets

El proyecto utiliza tres archivos:

- `plans.csv`: información de los planes, precios y beneficios incluidos.
- `users_latam.csv`: información de los clientes, incluyendo edad, ciudad, fecha de registro y plan.
- `usage.csv`: información sobre el uso de llamadas y mensajes.

## 🛠️ Herramientas

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## 🔎 Etapas del análisis

1. **Carga y exploración de datos**
   - Revisión de filas, columnas y tipos de datos.

2. **Calidad de datos**
   - Identificación de valores nulos.
   - Detección de valores inválidos y sentinels.
   - Revisión de fechas.

3. **Limpieza**
   - Tratamiento de valores `-999` en edad.
   - Conversión de `?` a valores nulos en ciudad.
   - Corrección de fechas fuera de rango.

4. **Análisis estadístico**
   - Estadísticas descriptivas.
   - Agrupación del uso por cliente.

5. **Visualización**
   - Histogramas.
   - Boxplots.
   - Análisis de distribuciones.

6. **Detección de outliers**
   - Aplicación del método IQR.
   - Evaluación de comportamientos extremos.

7. **Segmentación**
   - Segmentación por edad.
   - Segmentación por nivel de uso.

8. **Insight ejecutivo**
   - Identificación de segmentos relevantes.
   - Recomendaciones comerciales.

## ▶️ Cómo ejecutar el proyecto

1. Descargar o clonar este repositorio.
2. Abrir el archivo `.ipynb` utilizando Jupyter Notebook o JupyterLab.
3. Verificar que los datasets estén disponibles en la ruta `/datasets/`.
4. Ejecutar las celdas del notebook en orden.

## 📈 Principales hallazgos

El análisis permitió identificar diferentes perfiles de clientes según su edad y comportamiento de consumo.

Los usuarios fueron clasificados en grupos de bajo, medio y alto uso, permitiendo identificar clientes con mayor demanda de llamadas y mensajes.

También se identificaron valores atípicos en variables de consumo. Estos registros no fueron eliminados automáticamente, ya que pueden representar clientes reales con niveles de consumo elevados y potencial comercial.

## 💡 Recomendaciones

- Crear planes diferenciados según el nivel de consumo.
- Diseñar estrategias comerciales específicas para cada segmento.
- Fidelizar a los clientes de alto uso mediante beneficios personalizados.
- Analizar los consumos extremos para identificar clientes de alto valor.
- Utilizar el comportamiento real de los usuarios para ajustar los beneficios de los planes.

## 👤 Autor

**Jean Nicolás Florez**
