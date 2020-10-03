## Curso FP-0963-001

### La micro-cuenca de Quebrada Grande.

En el presente trabajo se hará una recopilación y análisis de información sobre el comportamiento de la Quebrada Grande, la cual entre otras presenta las siguientes características.

![](/Imagen/Mapa 1.PNG)  
**Mapa 1**. Ubicación geográfica de la micro-cuenca Quebrada Grande. Fuente: Sanchez, 2020.

<table>
  <tr><th>Área (km2)</th><th>Perímetro (m)</td><th>Provincia</th><th>Distrito</td>
  <tr><td>3.90</td><td>11900</td><td>Heredia</td><td>Vara Blanca</td>
</table>

*Se procedió a la elaboración de un análisis estadístico y para el desarrollo del presente análisis se utilizó el programa RStudio, ejecutando los siguientes pasos:
  
1) Importar los datos, establecer el data frame de trabajo de los datos de caudal y generar una visualización de los datos en escala temporal:

```{r}
str(Datos_Quebrada_Dantas_fbk)

Datos_stream <- Datos_Quebrada_Dantas_fbk

str(Datos_stream)

plot(Datos_stream$`Q (L/s)`, Datos_stream$`Date`)

_Puntos
plot(
  Datos_stream$`Date`, 
  Datos_stream$`Q (L/s)`,
  main='Caudal',
  xlab='Año',
  ylab='Caudal Q (L/s)'
)
```

![](/Imagen/Imagen/Rplot.png)  
**Grafico 1**. Caudal por año (puntos). Fuente: Sanchez, 2020.

```{r}
#lineal ggplot
ggplot(Datos_stream, aes(x = `Date`, y = `Q (L/s)`)) +
  geom_point(alpha = 0.6) +
  coord_fixed() +
  breaks = trans_breaks("log10", function(x) 10^x)
```

**Grafico 2**. Caudal por año (lineas). Fuente: Sanchez, 2020.

Seguidamente se procedió a la visualización de los datos en una escala logarítimica, con el obejtivo de poder visualizar de mejor manera el comportamiento del caudal durante el periodo de análisis.

```{r}
ggplot(Datos_stream, aes(x = Date, y = `Level (cm)`))+
  geom_line()+
  scale_y_log10()
```

**Grafico 2**. Caudal por año caudal (log10). Fuente: Sanchez, 2020.

Posteriorme se construyó el histograma del cadudal.

```{r}
ggplot(Datos_stream, aes(x= `Q (L/s)`)) +
  geom_histogram( binwidth=5, fill="#669933", color="#669933", alpha=0.9) +
  ggtitle("Histograma de caudal")+
  theme_classic()
 ```






