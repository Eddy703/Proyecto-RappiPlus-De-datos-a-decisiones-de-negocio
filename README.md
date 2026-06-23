# 📊 Proyecto RappiPlus: De Datos a Decisiones de Negocio

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0+-150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Data Analytics](https://img.shields.io/badge/Bootcamp-TripleTen-orange.svg?style=for-the-badge)
![Status](https://img.shields.io/badge/Project%20Status-Completed%20/%20Reviewed-brightgreen.svg?style=for-the-badge)

## 📝 Introducción y Contexto del Negocio
**RappiPlus** es un servicio de suscripción premium dentro del ecosistema de Rappi, diseñado estratégicamente para incrementar la frecuencia de compra, optimizar el valor de vida del cliente (*Customer Lifetime Value*) y potenciar la retención de usuarios. 

A pesar del despliegue del programa, el equipo de operaciones y dirección estratégica carecía de visibilidad clara sobre el impacto real del servicio: ¿Los usuarios están comprando más? ¿El modelo unitario es saludable y rentable? ¿Dónde experimentamos fugas en el embudo de conversión?

Este proyecto resuelve estas incógnitas mediante una auditoría completa de los datos, modelado financiero de rentabilidad, análisis de comportamiento por cohortes y pruebas de hipótesis estadísticas ($Z-test$).

---

## 🎯 Objetivos Principales
1. **Calidad de Datos:** Validar, limpiar y transformar las fuentes de datos operacionales para garantizar la confianza en los reportes de negocio.
2. **Análisis de Rentabilidad:** Determinar los márgenes de ganancia bruta y neta cruzando pedidos, costos de catálogo y gasto de marketing.
3. **Optimización del Embudo:** Identificar cuellos de botella y pérdidas de conversión en el flujo transaccional.
4. **Análisis de Retención:** Evaluar la lealtad del usuario a lo largo del tiempo mediante el comportamiento de cohortes semanales.
5. **Validación de Experimentos:** Analizar estadísticamente si los cambios implementados en la plataforma generaron un impacto significativo.

---

## 💾 Estructura y Fuentes de Datos
El ecosistema analítico se compone de las siguientes fuentes de datos limpias y procesadas:
* `orders_clean.csv`: Registro transaccional de pedidos, dispositivos, canales de adquisición, montos y banderas de anomalías.
* `catalog_clean.csv`: Catálogo maestro de productos con costos unitarios e información de proveedores.
* `marketing_clean.csv` & `marketing_mes_clean.csv`: Inversión detallada en marketing digital desglosada por canal, país y periodo mensual.

---

## 🛠️ Metodología Aplicada y Proceso Analítico

### 1. Validación y Calidad de Datos (Data Wrangling)
* Corrección y normalización de formatos temporales a `datetime64`.
* Auditoría de consistencia numérica: detección y tratamiento de valores negativos en columnas de precios y cantidades a través de funciones customizadas utilizando `.abs()`.
* Tratamiento exhaustivo de valores nulos y registros duplicados para asegurar métricas libres de sesgo.

### 2. Rentabilidad Financiera y KPIs Maestros
Se calculó la rentabilidad integrando ingresos operativos contra el costo total de los productos vendidos y las inversiones publicitarias:
* **Profit Bruto:** **$8,858,479.27 USD** *(Ingresos - Costo de Productos)*
* **Profit Neto:** **$5,986,635.74 USD** *(Incluyendo deducción de costos operativos totales y gasto de marketing)*

### 3. Retención por Cohortes Semanales
Se implementó un análisis de cohortes basado en el mes de registro de los usuarios, monitoreando su actividad transaccional semana a semana:
* **Hallazgo Clave:** Se identificó una retención sumamente sólida y estable que oscila entre el **40% y 43% de usuarios activos por semana**. Las cohortes mostraron un comportamiento homogéneo, validando la estabilidad a largo plazo de la propuesta de valor de RappiPlus.

### 4. Experimentación A/B (Pruebas de Hipótesis)
Para evaluar si una nueva variante en la plataforma incrementaba el ratio de conversión frente al flujo actual, se aplicó un **Z-test de proporciones**:
* **Métrica de Conversión Control:** 15.69%
* **Métrica de Conversión Tratamiento:** 16.29%
* **Resultado Estadístico:** Valor $p = 0.416$
* **Interpretación de Negocio:** Dado que el p-valor es significativamente mayor que el nivel de significancia estándar ($\alpha = 0.05$), **no se rechaza la hipótesis nula ($H_0$)**. No existe evidencia estadística suficiente para afirmar que los cambios implementados impacten el comportamiento de conversión; se recomienda iterar sobre el diseño del experimento antes de un despliegue masivo.

---

## 📈 Conclusiones y Recomendaciones Estratégicas
1. **Viabilidad del Modelo:** RappiPlus es financieramente saludable y rentable, generando más de **$5.9M USD** en beneficio neto durante el periodo evaluado.
2. **Engagement Consistente:** La retención semanal en torno al 40% es un indicador potente de lealtad, lo que justifica mantener incentivos basados en la recurrencia.
3. **Enfoque en Producto:** La prueba A/B demostró que pequeños cambios en el embudo no movieron la aguja de conversión de forma significativa. Se sugiere priorizar investigaciones cualitativas (UX/UI) para atacar cuellos de botella críticos detectados en el embudo antes de lanzar nuevos desarrollos técnicos.

---

## 💻 Tecnologías Utilizadas
* **Lenguaje de Programación:** Python 3.x
* **Librerías Clave:** `pandas`, `numpy`, `scipy.stats` (para pruebas Z/análisis estadístico).
* **Entorno de Trabajo:** Jupyter Notebook (.ipynb)

---

## 👤 Autor
* **Eduardo Emmanuel Gutiérrez García** - *Ingeniero en Sistemas Computacionales / Data Analyst*
* Proyecto desarrollado y evaluado con éxito bajo los estándares profesionales de **TripleTen**.
