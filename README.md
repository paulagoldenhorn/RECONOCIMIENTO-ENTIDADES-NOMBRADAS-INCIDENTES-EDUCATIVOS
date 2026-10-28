# Proyecto de Procesamiento de Lenguaje Natural

**Trabajo Práctico Final de la materia Procesamiento de Lenguaje Natural - Universidad de Palermo.**

## Integrantes

- Juan Cruz Rey
- Juan Ignacio Pintarelli
- Paula Goldenhorn

## Objetivos

El objetivo del trabajo es entrenar y evaluar modelos de Reconocimiento de Entidades Nombradas (NER) para extraer automáticamente información estructurada sobre incidentes en aulas y entornos educativos. A partir de ejemplos de mensajes de docentes en lenguaje natural, los modelos identifican las siguientes entidades:

- **OBJETO**: Elemento físico afectado.
- **PROBLEMA**: Falla o incidente reportado.
- **LUGAR**: Ubicación del incidente.

## Dataset

Se construyó un dataset sintético de ejemplos 570 anotados manualmente y aumentados con herramientas de IA. Se dividió en conjuntos de entrenamiento (80%), desarrollo (10%) y validación (10%).

## Modelado

Se entrenaron tres modelos para comparar dos enfoques: entrenamiento desde cero vs. aprendizaje por transferencia:
- **Fine-tuning spaCy (`es_core_news_lg`):** modelo neuronal de spaCy versión grande en español (con embeddings estáticos preentrenados).
- **Fine-tuning spaCy (`es_core_news_sm`):** modelo neuronal de spaCy versión pequeña en español (sin embeddings preentrenados).
- **Entrenamiento CRF**: modelo probabilístico de Campos Aleatorios Condicionales de scikit-learn.

## Resultados

**Métricas globales**

| Modelo | Precisión | Recall  | F1 |
| --- | --- | --- | --- |
| spaCy lg | 0.7365 | 0.7267 | 0.7315 |
| CRF | 0.7603 | 0.7400 | 0.7500 |
| spaCy sm | 0.7500 | 0.7400 | 0.7450 |

**Métricas por tipo de entidad**

[INSERTAR IMAGEN]

**Distribución de errores (falsos positivos y falsos negativos)**

[INSERTAR IMAGEN]

## Estructura del repositorio

```
├── NOTEBOOK.ipynb                  # Notebook principal (pipeline del proyecto)
├── INFORME.pdf                     # Informe del proyecto
├── dataset_limpio.jsonl            # Dataset anotado
├── comparacion_metricas.png        # Gráficos de comparación entre métricas
├── distribucion_errores.png        # Gráficos de distribución de errores
├── config/                         # Archivos de configuración de spaCy
└── data/                           # Datos en formato binario spaCy (.spacy)
```
