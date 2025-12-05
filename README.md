# Meta-análisis de Estudios de Metilación en la Enfermedad de Alzheimer
Este repositorio alberga los datos, el código de procesamiento y los resultados del metaanálisis de metilación  para la Enfermedad de Alzheimer (EA). 
El objetivo es identificar genes diferencialmente metilados consistentes a través de múltiples conjuntos de datos de GEO (Gene Expression Omnibus).

## Estructura del Repositorio
El directorio principal contiene toda la información esencial para replicar el análisis:
* **`raw_data/`**: Contiene los objetos `ExpressionSet` de R (`.rds`) para cada conjunto de datos de GEO (GSE) utilizados en el metaanálisis. Estos archivos binarios grandes son gestionados a través de Git LFS.
* **Archivos CSV y Metatablas**: Contienen la información de tablas análisis diferencial.
* **Resultados y Visualizaciones**: Archivos `.png` de *Boxplots*, *Volcano Plots* y gráficos de genes identificados.
* **`Metanalisis.Rmd`**: El script principal de R Markdown que contiene todo el código fuente para la importación, normalización, análisis estadístico y generación de resultados.

## Metodología

### Conjuntos de Datos Incluidos

Se incluyeron los siguientes estudios de GEO que comparan datos de pacientes con *Enfermedad de Alzheimer* vs. *controles sanos*:
GSE109887, GSE76105, GSE97760, GSE57360, GSE66351. Todos pertenecen a estudios realizados mediante la tecnología de microarrays y metilación : Illumina y Agilent.

### Flujo de Análisis

1.  **Descarga y Normalización**: Los datos se cargaron en R y se realizó la normalización necesaria de los datasets dependiendo de la exploración de datos.
2.  **Análisis de Expresión Diferencial (DEA)**: Se aplicó el modelo lineal de `limma` a cada dataset
3.  **Metaanálisis**: Se utilizó el paquete `metafor` 
4.  **Visualización**: Generación de *Volcano Plots* y *Boxplots* para los genes más significativos.
5.  **Análisis de resultados**: Análisis biológico y funcional de genes consistentes entre estudios.

## Cómo Replicar el Análisis

Este proyecto fue desarrollado en R. Para replicar los resultados, necesitarás:

1.  **Clonar el repositorio:**
    ```bash
    git clone [https://github.com/granizokaren1-a11y/Metaanalisis_Alzheimer_2025.git](https://github.com/granizokaren1-a11y/Metaanalisis_Alzheimer_2025.git)
    ```
3.  **Abrir `Metanalisis.Rmd`** en RStudio.
4.  **Instalar las librerías necesarias** (ej. `limma`, `GEOquery`, `metafor`, `Biobase`).
5.  **Ejecutar el script** paso a paso.

## Contacto

**Karen Granizo**
* **Correo Electrónico:** kareng2199@hotmail.com
* **Perfil de GitHub:** https://github.com/granizokaren1-a11y
