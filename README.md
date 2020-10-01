---
title: "Proyecto final Hidrología: Quebrada Dantas"
author: "Fernando Bermúdez y Priscilla Obando"
date: "24/9/2020"
output: html_document
---

```{r}
```

## Curso FP-0963-001

### La micro-cuenca de Quebrada Dantas.

En el presente trabajo se hará una recopilación y análisis de información sobre el comportamiento de la Quebrada Dantas, la cual entre otras presenta las siguientes características

PONER IMAGEN DE UN MAPA_sick

Inicialmente se procedió a la elaboración de un análisis estadístico y para el desarrollo del presente análisis se utilizó el programa RStudio, ejecutando los siguientes pasos:
  
1) Importar los datos Import dataset, establecer el nuevo data frame de trabajo de los datos de caudal y generar una visualización de los datos:

```{r}
Datos_Quebrada_Dantas_fbk <- read_excel("E:/DCS/MAESTRIA GIRHS/HIDROLOGIA/Proyecto final/Datos_Quebrada_Dantas_fbk.xlsx", 
                                        +     sheet = "Stream")
str(Datos_Quebrada_Dantas_fbk)

Datos_stream <- Datos_Quebrada_Dantas_fbk

plot(Datos_stream$`Q (L/s)`, Datos_stream$`Date`)

```


