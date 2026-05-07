---
title: Análisis del Desarrollo Educativo y la Finalización Escolar Femenina
subtitle: Indicador SE.PRM.CMPT.FE.ZS · World Development Indicators (WDI) · 2000–2022
authors:
  - name: Samuel David Chamorro
  - name: Juan David Marín
date: 2026-05-06
---

```{note}
Este análisis examina la evolución de la tasa de finalización de educación primaria femenina
a nivel global durante el período **2000–2022**, usando datos del Banco Mundial (WDI).
Se aplican técnicas de análisis exploratorio, series de tiempo y modelado **ARIMA(0,2,2)**
para proyectar tendencias hasta 2032.
```

## ¿Qué encontrarás aquí?

```{grid} 2
:gutter: 3

:::{grid-item-card} 🌍 Contexto Global
:link: test.ipynb
:link-type: doc
192 países · 23 años de datos · Panel desbalanceado.
Explora cómo ha evolucionado el acceso a la educación primaria femenina en el mundo.
:::

:::{grid-item-card} 📊 Análisis Exploratorio
:link: test.ipynb
:link-type: doc
Distribuciones, mapas coropléticos, boxplots por año y ritmo de mejora anual por país.
:::

:::{grid-item-card} 📈 Series de Tiempo
:link: test.ipynb
:link-type: doc
Prueba ADF de estacionariedad, correlogramas ACF/PACF y diagnóstico de estructura temporal.
:::

:::{grid-item-card} 🤖 Predicción ARIMA(0,2,2)
:link: test.ipynb
:link-type: doc
Selección automática de orden, validación 80/20 con MAPE < 1% y pronóstico 2023–2032.
:::
```

## Indicador analizado

:::{list-table}
:header-rows: 1
:widths: 30 70

* - Campo
  - Valor
* - **Indicador**
  - `SE.PRM.CMPT.FE.ZS` — Primary completion rate, female (% of relevant age group)
* - **Fuente**
  - World Development Indicators (WDI), Banco Mundial
* - **Período**
  - 2000 – 2022
* - **Cobertura**
  - 192 países (panel desbalanceado — 15.6% con serie completa)
* - **Variable clave**
  - `tasa_fin_cap` ∈ [0, 100] (acotada para visualización)
* - **Herramientas**
  - Python · Pandas · Matplotlib · Plotly · Statsmodels
:::

## Hipótesis del estudio

```{admonition} H₁ · Tendencia positiva global
:class: tip
La tasa de finalización de la educación primaria femenina ha mostrado una tendencia positiva
y estadísticamente significativa a nivel global durante el período 2000–2022.
```

```{admonition} H₂ · Convergencia internacional
:class: tip
Los países con tasas iniciales más bajas en el año 2000 han registrado incrementos relativos
mayores, evidenciando un proceso de convergencia hacia los niveles más altos observados en el panel.
```

```{admonition} H₃ · No estacionariedad temporal
:class: warning
La serie anual de la mediana global no es estrictamente estacionaria: existe una tendencia
temporal persistente que debe considerarse en el análisis estadístico (ADF p ≈ 0.055).
```

## Resultado principal

```{important}
El modelo **ARIMA(0,2,2)** —seleccionado por criterios AIC, BIC y HQIC entre 48 combinaciones—
proyecta que la mediana global de niñas que completan primaria se mantendrá cerca del **96–97%**
en los próximos años, con una mejora muy lenta dado el **efecto techo** del indicador.

La validación 80/20 arrojó un **MAPE < 1%**, indicando una réplica casi exacta de la tendencia histórica.
```

## Estructura del análisis

```{list-table}
:header-rows: 1
:widths: 10 30 60

* - Sección
  - Título
  - Contenido
* - 1
  - Introducción
  - Justificación, marco teórico, hipótesis y metodología
* - 2
  - Obtención y Procesamiento de Datos
  - Extracción vía API WDI, limpieza y preparación del dataset
* - 3
  - Análisis Univariado
  - ADF, ACF/PACF, histograma, boxplot y estadísticos descriptivos
* - 4
  - Análisis Bivariado y Multivariado
  - Mapa coroplético, tendencia anual, boxplots por año
* - 5
  - Predicción ARIMA(0,2,2)
  - Grid search, ajuste, diagnóstico, validación 80/20, pronóstico 2023–2032
* - 6
  - Conclusión
  - Síntesis de hallazgos e implicaciones para política educativa
* - 7
  - Referencias
  - Fuentes bibliográficas y de datos
```

---

*Fuente de datos: [World Bank Open Data](https://data.worldbank.org/indicator/SE.PRM.CMPT.FE.ZS) ·
Indicador SE.PRM.CMPT.FE.ZS · Accedido 2026.*
