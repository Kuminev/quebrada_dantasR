## Curso FP-0963-001

### La micro-cuenca de Quebrada Grande.

En el presente trabajo se hará una recopilación y análisis de información sobre el comportamiento de la Quebrada Grande, la cual entre otras presenta las siguientes características

![](/Imagen/Mapa 1.PNG)

PONER IMAGEN DE UN MAPA_sick

Inicialmente se procedió a la elaboración de un análisis estadístico y para el desarrollo del presente análisis se utilizó el programa RStudio, ejecutando los siguientes pasos:
  
1) Importar los datos Import dataset, establecer el data frame de trabajo de los datos de caudal y generar una visualización de los datos:

```{r}
Datos_Quebrada_Dantas_fbk <- read_excel("E:/DCS/MAESTRIA GIRHS/HIDROLOGIA/Proyecto final/Datos_Quebrada_Dantas_fbk.xlsx", 
                                        +     sheet = "Stream")
str(Datos_Quebrada_Dantas_fbk)

Datos_stream <- Datos_Quebrada_Dantas_fbk

plot(Datos_stream$`Q (L/s)`, Datos_stream$`Date`)

```
Seguidamente se procedió a la visualización de los datos en una escala logarítimica, con el obejtivo de poder visualizar de mejor manera el comportamiento del caudal durante el periodo de análisis.


