# 📘 Impacto de la Adaptación Pedagógica COVID-19 en la Inserción Laboral de los Graduados Universitarios Andaluces

Este repositorio contiene el código fuente, la metodología de limpieza de datos (ETL) y el análisis estadístico reproducible del proyecto de investigación sobre la calidad de la inserción laboral de los egresados en Andalucía tras la pandemia.

---

## 👥 Autores

- **Carlos Pérez**
- **Daniel Limón**
- **Joaquín Vidal**

---

## 🎯 Objetivo del Estudio

Analizar si la adaptación pedagógica y metodológica derivada de la pandemia COVID-19 ha afectado la calidad de la inserción laboral en las cohortes de egresados universitarios (2019–2023) en comparación con la cohorte control (2018–2019).

- **Hipótesis:** El cambio metodológico ha incrementado la probabilidad de inserción precaria (jornada parcial).

---

## 📁 Estructura del Repositorio

```plaintext
.
├── microdatos/              # Carpeta contenedora de los CSVs originales (No incluidos)
├── analisis_insercion.qmd   # Script principal (Quarto) con todo el flujo: ETL, análisis, tablas y figuras
├── README.md                # Documentación del proyecto
└── .gitignore               # Archivos ignorados (datos crudos, temporales)
```

## 🛠️ Stack Tecnológico

El proyecto utiliza **R** y **Quarto** para garantizar un flujo de trabajo reproducible.

- **Lenguaje:** R (Tidyverse estricto)
- **Formato de salida:** PDF (vía LaTeX/TinyTeX)
- **Librerías clave:**
  - `tidyverse`: Manipulación y limpieza de datos.
  - `gtsummary`: Tablas descriptivas y de regresión listas para publicación.
  - `broom`, `lmtest`, `sandwich`: Modelado estadístico inferencial.

---

## 🚀 Instrucciones de Reproducción

### 1. Requisitos Previos

Asegúrate de tener instalados los siguientes paquetes en R:

```r
install.packages(c("tidyverse", "gtsummary", "broom", "kableExtra", "scales", "lmtest", "sandwich"))
tinytex::install_tinytex()  # Necesario para renderizar a PDF
```

### 2. Datos
Debido a su tamaño y naturaleza, los microdatos no se alojan en este repositorio.
1.	Descarga los ficheros MicrodatILEUPA[2018–2022].csv desde el portal del IECA.
2.	Crea una carpeta llamada microdatos/ en la raíz del proyecto.
3.	Coloca los 5 archivos CSV dentro.

### 3. Ejecución
Abre el archivo analisis_insercion.qmd en RStudio y pulsa el botón Render.
El script se encargará automáticamente de:
- Ingesta: Detectar separadores (; o ,) y unir los archivos (rbind_union).
- Limpieza: Filtrar Grados, tratar NAs y generar variables (periodo_covid, CalidadContrato).
- Análisis: Generar tablas y modelos.

## 📊 Metodología de Datos

El script incluye un algoritmo de armonización personalizado para tratar la heterogeneidad de los archivos anuales originales.
- Universo: Egresados de Grado.
- Variable Dependiente: Precariedad (Jornada Parcial vs Completa).
- Variable Independiente: Periodo (Pre-COVID vs Post-COVID).

*Última actualización: Diciembre 2025*