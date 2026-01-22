# Análisis y segmentación de gamas de teléfonos móviles.

## Resumen del proyecto
Este proyecto analiza una base de datos de dispositivos móviles con el objetivo de identificar patrones y segmentar los teléfonos por **gama** mediante aprendizaje no supervisado.

El flujo de análisis consistió en:  
1. Carga y limpieza de datos, verificando el formato de las características.
2. Clustering inicial para separar tablets de teléfonos móviles. (se consideró que la variable de pantalla tenía mucho peso en los algoritmos y no era relevante, por lo que las tablets requerian un tratamiento por separado)
3. Selección de características relevantes para análisis de teléfonos, seleccionando sólo las numéricas de interés.  
4. Segundo clustering para clasificar los teléfonos en **gama baja, media y alta**.  
5. Interpretación de los resultados y extracción de patrones que pueden aplicarse en marketing o decisiones de negocio.

---

## Dataset
El conjunto de datos se obtuvo de Kaggle del siguiente enlace: https://www.kaggle.com/datasets/abdulmalik1518/mobiles-dataset-2025/code
- Contiene información de teléfonos y tablets de diferentes marcas y modelos.  
- Columnas relevantes:  
  - `Company Name` – Marca del dispositivo  
  - `Model Name` – Modelo  
  - `Processor` – Procesador  
  - `RAM` – Memoria RAM  
  - `Battery Capacity` – Capacidad de batería  
  - `Front Camera` – Cámara frontal (MP)  
  - `Back Camera` – Cámara trasera (MP)  
  - `Screen Size` – Tamaño de pantalla  
  - `Mobile Weight` – Peso  
  - `Launched Year` – Año de lanzamiento  
  - `Launched Price` – Precio de lanzamiento (solo para análisis descriptivo final, no usado en clustering)

---

## Selección de variables y clustering.
- Se realizó un **clustering inicial** para separar tablets de teléfonos móviles, utilizando el algoritmo de Agglomerative Hierarchical.

<img width="581" height="492" alt="image" src="https://github.com/user-attachments/assets/e57a4d0f-b326-4c26-b12e-6013fa1bab16" />

- Se seleccionaron características relevantes para teléfonos y se realizó un **segundo clustering** que permitió segmentarlos en tres gamas: baja, media y alta.
- Variables principales para clustering: `RAM`, `ProcessorBench`, `Battery Capacity`, `Front Camera`, `Back Camera`, `Mobile Weight`.  
- Se utilizaron tres algoritmos diferentes de clustering: K-Means, Agglomerative Hierarchical y Gaussian Mixture Models. Asimismo, se realizó como preprocesamiento el escalamiento de variables con MinMax y con estandarización. Se evaluó el clustering con métricas como DBI y Silhouette para determinar el clustering más adecuado.

<img width="604" height="492" alt="image" src="https://github.com/user-attachments/assets/4be9bdcf-7e32-4cdc-adf3-dc63ef780e4b" />

---

## Análisis de los clusters y dashboard.
Para identificar los clusters, se utilizaron estadísticas descriptivas y se presentaron en un dashboard hecho con Tableau.

<img width="1282" height="780" alt="image" src="https://github.com/user-attachments/assets/a5565a6f-ba55-4237-bf9f-8798d5ba8ad7" />

Puede consultarse públicamente desde: https://public.tableau.com/views/Dashboard_Smartphones/Dashboard1?:language=es-ES&:sid=&:redirect=auth&publish=yes&showOnboarding=true&:display_count=n&:origin=viz_share_link

---

## Conclusiones
Tras analizar las características por grupo, se identificaron los siguientes patrones:  

1. La mayor concentración de dispositivos móviles se encuentra en la **gama baja**.  
2. Los teléfonos de **gama media y baja** presentan características de hardware similares a los de **gama alta**, pero a precios significativamente menores.  
3. La capacidad de batería es similar entre las tres gamas, ofreciendo un rendimiento comparable.  
4. El tamaño de pantalla se mantiene casi constante, indicando que no es un factor relevante para clasificar teléfonos.  
5. Los teléfonos de gama media superan a los de gama alta en megapíxeles, aunque esto no necesariamente significa mejor cámara, ya que los de gama alta suelen tener sensores superiores; esto puede ser más un tema de marketing.  
6. La principal diferencia de los teléfonos de **gama alta** respecto a las otras gamas es su **mayor capacidad de procesamiento**.  

---

## Herramientas y tecnologías
- **Python**: pandas, numpy, scikit-learn, matplotlib, seaborn  
- **Tableau Public**: dashboard interactivo.

---

## Autor
**Fernando Arvizu Vargas**  

---
