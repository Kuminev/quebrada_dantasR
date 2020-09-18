# Proyecto final Hidrología: Quebrada Dantas

## Curso FP-0963-001

### Estudiantes: Fernando Bermúdez-Kuminev, Priscilla Obando


#### La micro-cuenca de Quebrada Dantas

En el presente trabajo se hará una recopilación y análisis de información sobre el comportamiento de la Quebrada Dantas, la cual entre otras presenta las siguientes características

PONER IMAGEN DE UN MAPA


**Análisis estadístico del caudal**

Para el desarrollo del presente análisis se utilizó el programa RStudio, ejecutando los siguientes pasos:

Cargar datos:
```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)

install.packages("readxl")

library(readxl)

Datos_Quebrada_Dantas

Datos_caudal <- Datos_Quebrada_Dantas

summary(Datos_caudal)
```
Seguidamente se cargaron los elementos de los paquetes para graficación:

```{r setup, include=FALSE}
install.packages("ggplot")
```

Ahora se comienza a desarrollar el análisis a partir de diferentes elementos:

```{r setup, include=FALSE}
ggplot(Datos_caudal, aes(x = Date, y = `Level (cm)`, group = 1)) +
  geom_line()
plot(
  Datos_caudal$Date, 
  Datos_caudal$`Level (cm)`,
  main='Caudal Quebrada Dantas',
  xlab='Fecha',
  ylab='Luvia'
)
#ggplot(Datos_Quebrada_Dantas, aes(x = Date, y = Q(L/s))) +
  geom_line()
```
