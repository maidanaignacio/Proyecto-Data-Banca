# 🏦 Proyecto: Optimización de Datos Bancarios

![Banner](banner.png)

## 📝 Resumen del Proyecto
En esta semana logré descargar 10,000 registros bancarios, los limpié con Python y los optimicé en formato Parquet.

### 🚀 Logros técnicos:
* **Limpieza:** Procesamiento con Pandas.
* **Optimización:** Conversión a Parquet para mayor velocidad.


# 📊 Proyecto: Sistema de Monitoreo de Salud Financiera y Retención de Clientes

## 1. Introducción y Objetivo
Este proyecto desarrolla un pipeline de datos integral para una entidad financiera, enfocado en la detección temprana de la fuga de clientes (**Churn**). El objetivo es transformar datos transaccionales crudos en hallazgos estratégicos para la toma de decisiones en el directorio.

## 2. Perfil Técnico del Proyecto
* **Lenguajes:** Python (Pandas/PySpark) para manipulación de volúmenes de datos.
* **Procesamiento:** Creación de pipelines de datos para limpieza y orquestación.
* **Modelado:** Ingeniería de datos para segmentación de carteras según comportamiento financiero.
* **Almacenamiento:** Gestión de datos optimizados en formato **Parquet** (Eficiencia en almacenamiento).

## 3. Análisis de Negocio (Storytelling)
A diferencia de un análisis académico, este informe se centra en **hallazgos estratégicos** para el negocio:

### A. Segmentación por Nivel de Saldo
Utilizamos lógica de programación para clasificar a los clientes según su patrimonio ($S$):

$$f(S) = \begin{cases} \text{Sin Saldo} & \text{si } S = 0 \\ \text{Saldo Bajo} & \text{si } 0 < S < 50,000 \\ \text{Saldo Medio} & \text{si } 50,000 \leq S < 150,000 \\ \text{Saldo Alto} & \text{si } S \geq 150,000 \end{cases}$$

**Hallazgo:** Los clientes de **Saldo Bajo** presentan la mayor tasa de abandono ($\approx 35\%$), lo que sugiere una falta de bancarización o productos de entrada atractivos.

### B. El Factor Demográfico (Edad)
El análisis visual revela un "pico" crítico de fuga entre los **40 y 50 años**.
* **Insight:** El banco está perdiendo a su segmento de clientes con mayor estabilidad laboral. Se recomienda revisar la oferta de productos de inversión o seguros de vida.

## 4. Métricas de Control (KPIs)
El éxito del pipeline se mide a través del **Churn Rate** calculado:

$$\text{Churn Rate} = \frac{\sum \text{Clientes Fugados}}{\text{Total Clientes}}$$

## 5. Próximos Pasos: Evolución hacia ML
---

##  Evolución hacia Inteligencia Artificial (Machine Learning)
En esta fase, el proyecto escala de un análisis descriptivo a un **sistema predictivo** capaz de anticipar la fuga de clientes antes de que ocurra.

### 🧠 Implementación del Modelo
Se seleccionó el algoritmo **Random Forest Classifier** debido a su robustez y capacidad para manejar relaciones no lineales en datos bancarios.
* **Precisión Alcanzada:** **87%** (Accuracy Score: 0.87).
* **Metodología:** División de datos en 80% entrenamiento y 20% testeo, con balanceo de variables categóricas.

### 🔍 Análisis de Importancia de Variables (Feature Importance)
A través de la interpretación del modelo, identificamos los tres pilares que disparan la fuga:
1. **Edad:** Factor crítico que confirma la necesidad de planes de fidelización para el segmento de 40-50 años.
2. **Salario Estimado:** Indica que la fuga no es solo por falta de fondos, sino por movilidad de clientes con alto poder adquisitivo.
3. **Puntaje de Crédito:** Los clientes con perfiles de riesgo específicos tienden a buscar otras opciones bancarias.

> **Valor Agregado:** Esta implementación permite al banco realizar **campañas de retención preventivas**, optimizando el presupuesto de marketing al dirigirlo solo a clientes con alta probabilidad de salida.
>
> ### 🔍 Análisis de Importancia de Variables (Feature Importance)
![Gráfico de Importancia de Variables](cap.png)
