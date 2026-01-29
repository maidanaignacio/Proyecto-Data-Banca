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



## 📈 Aplicación de Negocio: IA para Retención Preventiva

El modelo desarrollado no es solo un experimento técnico; es un **activo estratégico** para la entidad financiera. Con una precisión del **87%**, permite pasar de una estrategia reactiva a una proactiva mediante los siguientes casos de uso:

### 1. Sistema de Alerta Temprana (Early Warning System)
* **Funcionamiento:** Mensualmente, el modelo califica a la base de clientes activos con un **"Score de Riesgo"** (Probabilidad de Fuga).
* **Aplicación:** Los clientes con un score superior al **80%** son derivados automáticamente al equipo de fidelización para una intervención inmediata antes de que soliciten el cierre de cuenta.

### 2. Micro-segmentación para Campañas de Marketing
* **Hallazgo:** El análisis de importancia identifica que la **Edad** y el **Salario Estimado** son los principales motores de la fuga.
* **Aplicación:** El banco dirige ofertas de retención exclusivamente al segmento crítico (ej. clientes de 40-50 años con alto patrimonio), optimizando el **ROI en marketing** al evitar campañas masivas ineficientes.

### 3. Estrategia de Vinculación por Producto
* **Hallazgo:** El modelo indica que el **Número de Productos** influye directamente en la permanencia del cliente.
* **Aplicación:** Diseño de estrategias de *Cross-selling* para clientes con un solo producto. Al aumentar la vinculación, la probabilidad de abandono disminuye, incrementando el **LTV (Lifetime Value)** del cliente.

---

## 🛠️ Metodología Técnica (El "Cómo lo hice")

Para lograr estos resultados, implementé un pipeline basado en tres pilares:

1. **Ingeniería de Características:** Transformación de variables crudas en categorías de negocio (ej. `Nivel_Saldo`) para mejorar la interpretabilidad del perfil financiero.
2. **Entrenamiento:** Implementación de un algoritmo **Random Forest** por su alta precisión y capacidad para explicar qué variables pesan más en la decisión del cliente.
3. **Validación:** Evaluación del modelo con datos de prueba (test set) no vistos durante el entrenamiento, asegurando que el **87% de precisión** sea robusto y aplicable a nuevos clientes.

# Dashboard de Seguimiento - Scoring de Riesgo de Clientes

## Objetivo
Visualizar en tiempo real los clientes con mayor riesgo de fuga para priorizar acciones de retención.

## Estructura del Dashboard

### 1. Panel de Métricas Clave
- **Clientes en riesgo alto** (>70% prob. fuga)
- **Clientes en observación** (20%-70% prob. fuga)  
- **Clientes leales** (<20% prob. fuga)
- **Tasa de éxito de intervenciones**

### 2. Filtros de Segmentación
- [ ] Por probabilidad de fuga
- [ ] Por saldo promedio
- [ ] Por antigüedad del cliente
- [ ] Por tipo de producto

### 3. Lista de Clientes Prioritarios
| Cliente ID | Prob. Fuga | Saldo Promedio | Antigüedad | Productos | Acción Recomendada |
|------------|------------|----------------|------------|-----------|-------------------|
| C-001      | 85%        | $45,000        | 3 años     | 2         | Contacto urgente |
| C-002      | 65%        | $120,000       | 8 años     | 5         | Oferta producto premium |

### 4. Histórico de Intervenciones
- Gráfico de tendencia de riesgo por segmento
- Efectividad de campañas anteriores

## Requerimientos Técnicos

```python
# Ejemplo de estructura de datos para el dashboard
class CustomerRiskDashboard:
    def __init__(self):
        self.high_risk_threshold = 0.70
        self.medium_risk_threshold = 0.20
        
    def get_priority_customers(self):
        """Retorna clientes con probabilidad > 0.50"""
        return self.customers_df[self.customers_df['churn_prob'] > 0.50]
        
    def calculate_intervention_roi(self):
        """Calcula ROI de acciones de retención"""
        pass
