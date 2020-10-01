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
Table 1: Physical and chemical soil characteristics along a representative hillslope transect in Quebrada Grande catchment. 

Variable	CDA	CDM	CDB
Texture	Sandy 
Loam	Sandy 
Loam	Sandy 
Loam
Volumetric water content (%)	82.6	78.9	78.1
Hydraulic Conductivity (cm h-1)	0.21	1.68	2.06
Acidity (cmol L-1)	3.70	2.68	2.26
pH	4.1	4.7	4.8
Total Carbon content (%)	28.9	19.1	15.8
Total Nitrogen content (%)	1.93	1.24	0.97
C/N ratio	15.0	15.4	16.3
Organic matter content (%)	41.3	27.3	22.6
Trace elements (mg L-1)			
Fe	520	283	498
P	9.0	2.0	2.0
Zn	2.7	1.0	1.2
Cu	2.0	7.0	6.0
Mn 	4.0	5.0	2.0
Major cations (cmol L-1)			
Ca 	2.1	1.7	0.98
Mg 	0.94	0.37	0.38
K 	0.29	0.12	0.12
CEC (cmol  L-1)	7.0	4.9	3.7
Al (g/kg)	2.41	2.71	18.72
















