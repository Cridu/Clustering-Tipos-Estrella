# P2 - Clustering de Tipos de Estrella

Aprendizaje Automático — UC3M, curso 2025-26

## Descripción

Práctica de **aprendizaje no supervisado** cuyo objetivo es identificar los distintos tipos de estrella (enana roja, enana marrón, enana blanca, secuencia principal, súper gigante e hiper gigante) a partir de sus propiedades físicas, sin usar la etiqueta real de clase.

El flujo de trabajo seguido en el notebook es:

1. **Preprocesado** — codificación ordinal de las variables categóricas `Spectral_Class` y `Color`, ya que ambas están relacionadas con la temperatura y energía de la estrella.
2. **Reducción de dimensionalidad** — escalado de las variables numéricas y aplicación de **PCA** a 2 componentes principales para poder visualizar y agrupar los datos.
3. **Clustering** — comparación de tres algoritmos sobre el espacio PCA:
   - **K-Means** (selección de K mediante el método del codo, *silhouette score* y *Calinski-Harabasz score*)
   - **Clustering jerárquico** (dendrogramas con linkage `ward`, `complete` y `average`)
   - **DBSCAN**
4. **Interpretación** — se opta por 6 clusters, en línea con los tipos de estrella conocidos astronómicamente, y se analiza la correspondencia entre los clusters obtenidos y los tipos reales.

## Dataset

`stars_data.csv` — 240 estrellas con las variables:

| Variable | Descripción |
|---|---|
| `Temperature` | Temperatura superficial (K) |
| `L` | Luminosidad relativa al Sol |
| `R` | Radio relativo al Sol |
| `A_M` | Magnitud absoluta |
| `Color` | Color observado de la estrella |
| `Spectral_Class` | Clase espectral (O, B, A, F, G, K, M) |


## Estructura del repositorio

```
.
├── notebook.ipynb             # Preprocesado, PCA y comparación de algoritmos de clustering
├── stars_data.csv             # Dataset de estrellas
├── Practica2_enunciado_v2.pdf # Enunciado de la práctica
└── README.md
```

## Tecnologías

- Python 3
- pandas, numpy
- scikit-learn (`StandardScaler`, `PCA`, `KMeans`, `AgglomerativeClustering`, `DBSCAN`, métricas de clustering)
- matplotlib, seaborn, scipy (dendrogramas)

## Ejecución

```bash
pip install pandas numpy scikit-learn matplotlib seaborn scipy jupyter
jupyter notebook notebook.ipynb
```

## Autor
Cristian Dulugeac
