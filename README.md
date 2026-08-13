# 📞 ConnectaTel — Data Quality & Customer Segmentation Analysis

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-Data%20Visualization-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Plotting-11557c?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

> **Proyecto de Análisis Exploratorio (EDA) y Diagnóstico de Calidad de Datos (Data Quality)**  
> Diagnóstico, limpieza básica, comprobación de mecanismos MAR y segmentación estratégica sobre el parque de usuarios y patrones de consumo de **ConnectaTel**.

---

## 🎯 Objetivo del Proyecto

El propósito central de este proyecto es realizar un diagnóstico y auditoría integral de calidad de datos (**Data Quality Audit**) sobre los registros de clientes y patrones de uso de la compañía de telecomunicaciones **ConnectaTel**. 

Mediante la identificación de anomalías, la imputación metodológicamente justificada de datos faltantes y el análisis de comportamientos de consumo por canal, el proyecto transforma datos crudos e inconsistentes en una **segmentación estratégica con recomendaciones comerciales accionables**.

---

## 📦 Datasets Utilizados

El análisis combina dos fuentes de información operativas:

| Dataset | Registros | Variables Clave | Descripción |
| :--- | :---: | :--- | :--- |
| **`users`** | 4,000 | `user_id`, `age`, `city`, `reg_date` | Información demográfica y de cuenta de los clientes. |
| **`usage`** | Transaccional | `user_id`, `type`, `duration`, `length`, `date` | Registros detallados de eventos de llamadas y mensajes. |

---

## 🛠️ Etapas del Análisis (Data Pipeline)

<img width="960" height="272" alt="image" src="https://github.com/user-attachments/assets/d761291b-87ff-47af-b8e1-6f39cd96c148" />

1. **Exploración Inicial de Datos (EDA):** Identificación de estructuras, tipos de datos, distribuciones estadísticas y hallazgo de anomalías.
2. **Limpieza Básica de Datos:**
   * **Inconsistencias en `age`:** Aislamiento y reemplazo del valor sentinel `-999` antes de calcular la **mediana real ($48.0$ años)** para la imputación de nulos.
   * **Estandarización Geográfica (`city`):** Estandarización de 96 caracteres sentinel `'?'` sumados a 469 nulos originales (**565 filas / 14.12% de la base**) a `pd.NA`.
   * **Depuración Temporal:** Reasignación a `pd.NaT` de fechas anómalas fuera del horizonte operativo (40 registros en `reg_date` y 50 en `usage['date']`).
3. **Mecanismo de Datos Faltantes (MAR):**
   * Comprobación empírica mediante agrupaciones por `type` de que la ausencia de datos en `duration` y `length` depende de la naturaleza del servicio (100% nulos en tipos de evento no aplicables). **Decisión:** Conservar los nulos sin imputación.
4. **Segmentación y Detección de Outliers:**
   * Clasificación demográfica por grupos de edad, hábitos de uso e identificación de consumos atípicos en llamadas y datos.
5. **Insight Ejecutivo:** Elaboración de conclusiones estratégicas y recomendaciones respaldadas por evidencia cuantitativa.

---

## 📊 Síntesis de Hallazgos y Resultados

           DISTRIBUCIÓN DEMOGRÁFICA DE USUARIOS

<img width="1037" height="236" alt="image" src="https://github.com/user-attachments/assets/d4af3c24-8a70-4123-9786-70dbb20772e0" />

* **Grupo Demográfico Predominante:** La base está centrada en la mediana de **48.0 años**, siendo el segmento **Adulto (30–59 años)** el mayoritario con un **50% del total de usuarios**.
* **Segmentación por Consumo:** El segmento de **Uso Medio** representa el núcleo operativo más estable y con mayor *Lifetime Value* (LTV) para ConnectaTel.
* **Patrones Extremos (Outliers):** Se detectaron llamadas atípicas de larga duración (>120–180 minutos) y volúmenes extremos de mensajería/datos, lo que señala riesgos de congestión de red o uso comercial no regulado sobre líneas residenciales.

---

## 💡 Recomendaciones Estratégicas de Negocio

1. **Portfolio Ajustado a Perfiles:**
   * **Plan Intermedio (Target Principal):** Paquete equilibrado de voz y datos adaptado al grupo adulto (30–59 años).
   * **Plan Data-Only:** Oferta digital intensiva en navegación para usuarios jóvenes (<30 años).
   * **Plan Senior Voice:** Enfocado en minutos ilimitados para adultos mayores ($\ge 60$ años).
2. **Mitigación de Riesgos por Consumo Extremo:**
   * Implementación de una **Política de Uso Justo (Fair Usage Policy - FUP)** sobre las variables `duration` y `length` para regular los consumos atípicos sin degradar la calidad del servicio para el $95\%$ de los usuarios convencionales.

---

## 🚀 Instrucciones para Ejecutar el Notebook

1. **Clonar el repositorio:**
   ```bash
   git clone [https://github.com/JeanNicolas-Conecta/Proyecto-final-del-sprint-7.git](https://github.com/JeanNicolas-Conecta/Proyecto-final-del-sprint-7.git)
   cd Proyecto-final-del-sprint-7
   
1. Crear entorno virtual e instalar dependencias:

python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
pip install pandas numpy jupyter

2. Ejecutar el Notebook:

jupyter notebook


👤 Autor
Jean Nicolas Florez Rodriguez

Data Analyst



