# Desafío 2 - Hackathon 2

Este archivo tiene como finalidad explicar el contenido de las carpetas y el procesamiento lógico seguido para abordar el Desafío 2 de la Hackathon 2.

## Antecedentes

El desarrollo de este proyecto no fue lineal, sino que siguió una metodología iterativa y circular. Esto significa que, en varias ocasiones, fue necesario volver a pasos anteriores debido a errores o requerimientos específicos que surgieron durante el proceso.

## 0. Archivos Originales

Esta carpeta contiene la información original proporcionada por Minera Centinela, sin modificaciones.

## 1. Ordenamiento de Bases de Datos

Inicialmente, se analizaron los archivos Excel de cada base de datos para comprender su estructura. Se concluyó que la estructura original no era adecuada para su procesamiento en DataFrames de pandas. Por lo tanto, se decidió transponer las matrices. En el caso de los costos, tras un análisis de variabilidad, se determinó que no había claridad en la clasificación de costos fijos o variables. Por esta razón, se eliminó esta clasificación y los costos se agruparon por subproceso. Esta es la data que se utilizó a lo largo del desafío.

## 2. Análisis de Costos

Se empleó el método del coeficiente de variación para analizar los costos, lo que resultó en la clasificación de los costos en tres categorías:
- **Costos Fijos:** 1982
- **Costos Variables:** 1266
- **Sin Registros:** 378

## 3. Análisis de Bases de Datos de Indicadores

Para analizar las bases de datos de indicadores, se presentaron dos opciones:
1. Analizar las bases por separado y predecir costos de un subproceso basado en una única base seleccionada arbitrariamente.
2. Realizar un análisis matemático para determinar, mediante correlaciones, qué indicadores son más apropiados para cada subproceso. Se eligió la segunda opción.

Se seleccionó el coeficiente de correlación de **Spearman**, considerando las características de los datos y la investigación realizada.

### 3.1 Pruebas de Machine Learning

Se realizaron pruebas con varios modelos de machine learning para determinar cuál sería el más adecuado. Sin embargo, los resultados iniciales no fueron concluyentes, por lo que se decidió seguir un enfoque por etapas. Se determinó que modelos computacionalmente más complejos, como los basados en PyTorch o Keras, no aportaban a la solución. Finalmente, se optó por una lista de modelos más simples (ver sección 3.2).

### 3.2 Entrenamiento de Modelos

Se procedió a entrenar los modelos seleccionados utilizando datos hasta diciembre de 2021, para luego predecir los costos de todo el año 2022 y comparar los resultados. Aunque se logró un avance respecto a los modelos previos, los resultados no fueron concluyentes. Posteriormente, se probó un ensamblado con un **Voting Regressor**, que arrojó mejores resultados. Por lo tanto, este es el modelo propuesto como solución final.

## 4. Modelo Final

El modelo final es un **Voting Regressor** entrenado con todos los datos desde 2016 hasta 2022, y se utilizó para estimar los costos de 2023 en base a los indicadores.

## 5. Entregable

El archivo final es una matriz traspuesta, derivada del modelo final. Debido a limitaciones de tiempo, se decidió realizar modificaciones manuales y hacer los cálculos en Excel para los procesos, basados en los resultados del modelo.

## Consideraciones

Esta es una explicación general, ya que se realizó mucho más trabajo y esto es solo un resumen de los hitos más importantes. También existen archivos que no están presentes en este repositorio, los cuales fueron trabajados pero, para mantener un orden y calidad en los mismos, se decidió dejarlos fuera.

---

Este enfoque permite presentar una solución basada en análisis rigurosos y una metodología iterativa, adaptada a los desafíos específicos del proyecto.

  
