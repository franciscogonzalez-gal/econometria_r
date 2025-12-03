# Econometría con R

Este repositorio contiene una colección de laboratorios y proyectos de econometría desarrollados en R, enfocados en técnicas de análisis de datos, modelado predictivo y series temporales.

## 📋 Descripción del Proyecto

Este proyecto forma parte de un curso de econometría y contiene implementaciones prácticas de diversos conceptos y técnicas estadísticas y de machine learning aplicadas a problemas económicos reales. Los laboratorios cubren desde regresión lineal básica hasta modelos avanzados de predicción con XGBoost y análisis de series temporales.

## 📁 Estructura del Repositorio

```
econometria_r/
├── Lab 2.Rmd              # Laboratorio 2: Modelos de Regresión
├── Lab 3.Rmd              # Laboratorio 3: Predicción de Ventas Walmart
├── Lab 3 Ejercicio 2 v2.qmd  # Variante del Lab 3
├── Lab 4.Rmd              # Laboratorio 4: Series Temporales (CPI)
├── proyecto.Rmd           # Proyecto Final: Competencia Kaggle
├── resultados_modelos_walmart.csv  # Resultados del análisis Walmart
└── LICENSE.txt            # Licencia CC0 1.0 Universal
```

## 🔧 Requisitos

### Software
- **R** (versión 4.0 o superior recomendada)
- **RStudio** (opcional pero recomendado)

### Paquetes de R

Los siguientes paquetes son necesarios para ejecutar los laboratorios:

```r
# Manipulación de datos
install.packages("tidyverse")
install.packages("dplyr")
install.packages("tidyr")
install.packages("readr")

# Visualización
install.packages("ggplot2")
install.packages("GGally")
install.packages("corrplot")
install.packages("ggmap")  # Para visualizaciones geográficas

# Modelado
install.packages("caret")
install.packages("tidymodels")
install.packages("recipes")

# Modelos específicos
install.packages("randomForest")
install.packages("ranger")
install.packages("rpart")
install.packages("xgboost")
install.packages("glmnet")
install.packages("kernlab")
install.packages("kknn")

# Series temporales
install.packages("forecast")
install.packages("tseries")
install.packages("lubridate")
install.packages("nnfor")

# Otros
install.packages("readxl")
install.packages("Metrics")
install.packages("MASS")
```

## 📚 Descripción de Laboratorios

### Laboratorio 2: Modelos de Regresión en R

**Autor:** Francisco González  
**Objetivos:**
- Implementar una función de regresión lineal desde cero sin usar `lm()`
- Comparar resultados con la función nativa de R
- Realizar análisis exploratorio de datos (EDA)
- Entrenar y validar múltiples modelos de regresión
- Implementar validación cruzada con `caret`

**Conceptos clave:**
- Regresión lineal simple
- Coeficiente de determinación (R²)
- Validación cruzada repetida
- Partición de datos (train/validation)
- Comparación de modelos (Champion vs Challenger)

### Laboratorio 3: Predicción de Ventas Walmart

**Autor:** Francisco González  
**Carnet:** 24002914  
**Objetivos:**
- Análisis exploratorio de datos de ventas de Walmart
- Predicción de ventas semanales
- Manejo de variables temporales
- Comparación de múltiples algoritmos de machine learning

**Técnicas aplicadas:**
- EDA con visualizaciones de densidad
- Análisis de correlaciones
- Ingeniería de características
- Modelos de regresión múltiple

### Laboratorio 4: Series Temporales (CPI)

**Autor:** Francisco González  
**Carnet:** 24002914  
**Objetivos:**
- Análisis de series temporales del Índice de Precios al Consumidor (CPI)
- Manejo de datos temporales con `lubridate`
- Implementación de modelos de pronóstico
- Tratamiento de valores faltantes en series temporales

**Técnicas aplicadas:**
- Creación de objetos `ts` (time series)
- Forward fill para imputación
- Análisis de tendencias
- Modelos de pronóstico con `forecast`

### Proyecto Final: Competencia Kaggle

**Autor:** Francisco González  
**Carnet:** 24002914  
**Dataset:** California Housing Prices  
**Objetivos:**
- Participar en una competencia de predicción de precios de viviendas
- Aplicar técnicas avanzadas de machine learning
- Optimización de hiperparámetros
- Generación de predicciones para submission

**Pipeline del proyecto:**

1. **EDA Completo:**
   - Análisis de distribuciones
   - Matrices de correlación
   - Visualizaciones geográficas con Google Maps
   - Análisis de proximidad al océano

2. **Modelos implementados:**
   - Regresión Lineal
   - Árbol de Decisión
   - Random Forest
   - XGBoost
   - Elastic Net (Lasso/Ridge)
   - Support Vector Machine (SVM)
   - K-Nearest Neighbors (KNN)

3. **Optimización:**
   - Tuning de hiperparámetros con `tune_grid`
   - Validación cruzada estratificada
   - Búsqueda en grilla de parámetros

4. **Variables clave:**
   - `median_income`: ingreso medio del área
   - `ocean_proximity`: proximidad al océano (categórica)
   - `latitude`, `longitude`: coordenadas geográficas
   - `median_house_value`: variable objetivo

**Mejores prácticas implementadas:**
- Preprocesamiento con `recipes`
- Imputación de valores faltantes
- Variables dummy para categóricas
- Eliminación de predictores con varianza cero
- Workflow reproducible con `tidymodels`

## 🚀 Instrucciones de Uso

### 1. Clonar el repositorio

```bash
git clone https://github.com/franciscogonzalez-gal/econometria_r.git
cd econometria_r
```

### 2. Instalar dependencias

Abrir R o RStudio y ejecutar:

```r
# Instalar todos los paquetes necesarios
source("install_packages.R")  # Si existe
# O instalar manualmente según la sección de Requisitos
```

### 3. Ejecutar los laboratorios

Cada laboratorio está en formato R Markdown (`.Rmd`) o Quarto (`.qmd`):

**Opción 1: Desde RStudio**
1. Abrir el archivo `.Rmd` deseado
2. Click en "Knit" o presionar `Ctrl+Shift+K`
3. Se generará un archivo HTML con los resultados

**Opción 2: Desde R console**

```r
rmarkdown::render("Lab 2.Rmd")
rmarkdown::render("Lab 3.Rmd")
rmarkdown::render("Lab 4.Rmd")
rmarkdown::render("proyecto.Rmd")
```

### 4. Para el Proyecto Final (Kaggle)

**Requisitos adicionales:**
- Descargar los datasets de la competencia:
  - `train.csv`
  - `test.csv`
- Colocarlos en el directorio raíz del proyecto
- (Opcional) Configurar Google Maps API key para visualizaciones geográficas:

```r
Sys.setenv(GOOGLE_API_KEY = "tu_api_key_aqui")
```

**Ejecutar el proyecto:**

```r
rmarkdown::render("proyecto.Rmd")
```

El archivo generará:
- Análisis exploratorio completo
- Entrenamiento de múltiples modelos
- Optimización de hiperparámetros
- Archivo `submission.csv` para Kaggle

## 📊 Resultados Destacados

### Proyecto Kaggle - California Housing

**Conclusiones del EDA:**
- El **ingreso medio** es el predictor más fuerte del valor de vivienda
- La **proximidad al océano** impacta significativamente los precios
- Existe un tope artificial en `$500,000` en el dataset
- Las zonas costeras urbanas (San Francisco, Los Ángeles) tienen los precios más altos

**Rendimiento de modelos:**
- Mejor modelo: **XGBoost optimizado**
- Métrica: RMSE (Root Mean Squared Error)
- Técnica de validación: 5-fold cross-validation

## 🤝 Contribuciones

Este es un proyecto académico individual desarrollado por Francisco González (Carnet: 24002914) como parte del curso de Econometría.

## 📄 Licencia

Este proyecto está bajo licencia **CC0 1.0 Universal** (Creative Commons Zero v1.0 Universal).

Esto significa que el autor ha dedicado el trabajo al dominio público, renunciando a todos sus derechos de autor y derechos conexos en la medida permitida por la ley. Puedes copiar, modificar, distribuir y realizar el trabajo, incluso con fines comerciales, sin pedir permiso.

Ver el archivo [LICENSE.txt](LICENSE.txt) para más detalles.

## 📧 Contacto

**Autor:** Francisco González  
**Carnet:** 24002914

---

## 🔍 Notas Técnicas

### Reproducibilidad

Todos los análisis utilizan semillas aleatorias para garantizar reproducibilidad:

```r
set.seed(42)  # Usado en la mayoría de laboratorios
```

### Estructura de Workflows

Los laboratorios siguen buenas prácticas de ciencia de datos:

1. **Carga de datos** → 2. **EDA** → 3. **Preprocesamiento** → 4. **Modelado** → 5. **Evaluación** → 6. **Predicción**

### Manejo de Datos Faltantes

- **Numéricos:** Imputación por mediana (`step_impute_median`)
- **Categóricos:** Imputación por moda (`step_impute_mode`)
- **Series temporales:** Forward fill (`fill(.direction = "down")`)

---

**Última actualización:** Diciembre 2024
