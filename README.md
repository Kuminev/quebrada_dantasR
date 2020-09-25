# Proyecto final Hidrología: Quebrada Dantas

## Curso FP-0963-001

### Estudiantes: Fernando Bermúdez-Kuminev, Priscilla Obando


#### La micro-cuenca de Quebrada Dantas

En el presente trabajo se hará una recopilación y análisis de información sobre el comportamiento de la Quebrada Dantas, la cual entre otras presenta las siguientes características

PONER IMAGEN DE UN MAPA


**Análisis estadístico del caudal**

Para el desarrollo del presente análisis se utilizó el programa RStudio, ejecutando los siguientes pasos:

Cargar datos:
´´´{r}

install.packages("readxl")
install.packages("gapminder")
install.packages("dplyr")

library(readxl)
library(gapminder)
library(dplyr)
library(ggplot2)
´´´
Seguidamente se procedió a cargar los datos del análisis de caudal, mediante el import data set y el establecimiento
de un nuevo Data Frame:

´´´{r}
Datos_stream <- Datos_Quebrada_Dantas_fbk
´´´

Se analizó la composición de los datos y se construye un gráfico general de puntos Caudal vrs Fecha en diferentes módulos:

´´´{r}
str(Datos_stream)

plot(Datos_stream$`Q (L/s)`, Datos_stream$`Date`)

#puntos
plot(
  Datos_stream$`Date`, 
  Datos_stream$`Q (L/s)`,
  main='Caudal',
  xlab='Año',
  ylab='Caudal Q (L/s)'
)

#lineal
plot(
  Datos_stream$`Date`, 
  Datos_stream$`Q (L/s)`,
  main='Caudal',
  xlab='Año',
  ylab='Caudal Q (L/s)',
  type="l"
)

#lineal ggplot
ggplot(Datos_stream, aes(x = `Date`, y = `Q (L/s)`)) +
  geom_point(alpha = 0.6) +
  coord_fixed() +
  breaks = trans_breaks("log10", function(x) 10^x)

#histograma

ggplot(Datos_stream, aes(x= `Q (L/s)`)) +
  geom_histogram( binwidth=5, fill="#669933", color="#669933", alpha=0.9) +
  ggtitle("Histograma de caudal")+
  theme_classic()

#Frecuencia acumulada##

**Inicialmente se debe de realizar el cálculo de mínimos y máximos**

ggplot(Datos_stream, aes(x= `Q (L/s)`)) +
  geom_freqpoly(binwidth=60, size=2) 


#Jitter 
ggplot(Datos_stream, mapping = aes(x=`Q (L/s)`, y=`Date`)) + 
  geom_point( alpha=0.6, size=2)+
  labs(title = "Jitter")
