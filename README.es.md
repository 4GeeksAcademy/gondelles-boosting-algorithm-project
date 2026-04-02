# Optimización de algoritmos con Boosting para predicción de diabetes

## Descripción del proyecto

Este proyecto analiza el uso de un modelo de boosting para predecir diabetes en un problema de clasificación supervisada. El trabajo continúa el recorrido realizado previamente con árbol de decisión y random forest, reutilizando el mismo dataset procesado para poder comparar resultados de forma consistente.

El objetivo no fue solo entrenar un nuevo algoritmo, sino comprobar si boosting aportaba una mejora real, analizar el efecto de sus hiperparámetros y decidir, con base en evidencia, qué modelo conviene conservar.

## Objetivo

Construir un modelo de boosting, optimizar sus hiperparámetros y compararlo con los modelos anteriores del recorrido para elegir la alternativa más adecuada en este problema de predicción de diabetes.

## Dataset

Se utiliza el conjunto de datos procesado en el proyecto anterior, ya dividido en entrenamiento y prueba.

Archivos utilizados:

- `X_train_CON_outliers.csv`
- `X_test_CON_outliers.csv`
- `y_train.csv`
- `y_test.csv`

Variables predictoras empleadas:

- `Pregnancies`
- `Glucose`
- `BloodPressure`
- `SkinThickness`
- `Insulin`
- `BMI`
- `DiabetesPedigreeFunction`
- `Age`

## Metodología

El proyecto sigue este flujo de trabajo:

1. carga del dataset procesado;
2. entrenamiento de un modelo baseline de boosting;
3. exploración de hiperparámetros (`n_estimators`, `learning_rate`, `max_depth`);
4. evaluación del modelo optimizado con métricas de clasificación;
5. comparación final con árbol de decisión y random forest;
6. conclusión argumentada sobre el modelo más conveniente.

## Modelos comparados

- Árbol de decisión
- Random Forest
- Boosting (`XGBClassifier`)

## Principales resultados

### Boosting baseline
- Accuracy: **0.7468**

### Boosting optimizado
- Mejor configuración encontrada:
  - `n_estimators = 50`
  - `learning_rate = 0.2`
  - `max_depth = 3`
- Accuracy: **0.7662**

### Comparación final entre modelos
- **Random Forest**
  - Accuracy: **0.7727**
  - Precision clase 1: **0.8333**
  - Recall clase 1: **0.5085**
  - F1 clase 1: **0.6316**

- **Decision Tree**
  - Accuracy: **0.7662**
  - Precision clase 1: **0.6885**
  - Recall clase 1: **0.7119**
  - F1 clase 1: **0.7000**

- **Boosting**
  - Accuracy: **0.7662**
  - Precision clase 1: **0.7347**
  - Recall clase 1: **0.6102**
  - F1 clase 1: **0.6667**

## Interpretación general

Random Forest fue el modelo con mejor rendimiento global en términos de `accuracy` y también el que mostró mayor `precision` para la clase positiva. Esto lo convierte en la opción más sólida dentro del alcance del proyecto.

El árbol de decisión, sin embargo, obtuvo el mejor `recall` y el mejor `f1-score` para la clase `1`, lo que indica una mayor capacidad para detectar casos positivos de diabetes.

Boosting mejoró respecto a su baseline inicial, lo que confirma que el ajuste de hiperparámetros sí tuvo efecto. Aun así, en la comparación final no consiguió superar con claridad a Random Forest en rendimiento general ni al árbol de decisión en sensibilidad hacia la clase positiva.

## Conclusión

El modelo elegido para este proyecto es **Random Forest**, porque ofreció el mejor equilibrio general entre rendimiento global y precisión en la clase positiva.

Aunque el árbol de decisión detectó mejor los casos positivos y boosting mostró una mejora respecto a su versión inicial, Random Forest fue la alternativa más consistente dentro del conjunto de pruebas realizadas.

## Estructura del repositorio

```text
gondelles-boosting-algorithm-project/
├── data/
│   └── processed/
├── models/
├── src/
│   └── boosting_diabetes.ipynb
├── README.md
└── requirements.txt