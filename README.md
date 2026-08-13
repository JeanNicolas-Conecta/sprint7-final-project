# 📞 Proyecto ConnectaTel: Análisis de Calidad de Datos y Segmentación de Clientes

## 🎯 Objetivo del Proyecto
Realizar un Diagnóstico y Limpieza de Calidad de Datos (Data Quality) sobre los registros de clientes y patrones de consumo de **ConnectaTel**, identificando segmentos de usuarios, patrones de uso y recomendaciones estratégicas de negocio respaldadas por evidencia cuantitativa.

---

## 📦 Datasets Utilizados
1. **`users` (4,000 registros):** Contiene `user_id`, `age` (edad), `city` (ciudad) y `reg_date` (fecha de registro).
2. **`usage` (Registros de actividad):** Contiene `user_id`, `type` (`call` o `text`), `duration` (duración), `length` (longitud/tamaño) y `date` (fecha del evento).

---

## 🛠️ Etapas del Análisis
1. **Exploración Inicial (EDA):** Identificación de estructura, tipos de datos y distribución estadística.
2. **Limpieza Básica de Datos:**
   * **`age`:** Exclusión previa del sentinel `-999` para imputar con la **mediana real (48.0 años)**.
   * **`city`:** Estandarización de 96 caracteres `'?'` sumados a 469 nulos (**565 filas / 14.12% de la base**) a `pd.NA`.
   * **Fechas fuera de rango:** Reasignación de fechas posteriores a 2024 (40 en `reg_date` y 50 en `date`) a `pd.NaT`.
3. **Mecanismo MAR:** Confirmación de que los nulos en `duration` y `length` se explican por la variable `type` (mantenidos sin imputar).
4. **Segmentación y Outliers:** Clasificación por grupos de edad, nivel de uso y detección de atípicos.
5. **Insight Ejecutivo:** Elaboración de conclusiones y recomendaciones comerciales.

---

## 📊 Síntesis de Hallazgos Clave
* **Edad Predominante:** Mediana de **48.0 años**, siendo el grupo de **30 a 59 años** el mayoritario (~50% de la base).
* **Patrones de Servicio:** Comportamiento de nulos simétrico clasificado como **MAR**.
* **Outliers:** Presencia de llamadas atípicas de larga duración (>120-180 min) y mensajes masivos.

---

## 🚀 Instrucciones para Ejecutar el Notebook
```bash
# 1. Clonar el repositorio
git clone [https://github.com/TuUsuarioDeGitHub/NombreDeTuRepositorio.git](https://github.com/TuUsuarioDeGitHub/NombreDeTuRepositorio.git)

# 2. Instalar dependencias
pip install pandas numpy

# 3. Ejecutar Jupyter
jupyter notebook

Jean Nicolas Florez Rodriguez — Data Analyst
