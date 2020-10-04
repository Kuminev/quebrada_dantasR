## Curso FP-0963-001

### La micro-cuenca de Quebrada Grande.

En el presente trabajo se hará una recopilación y análisis de información sobre el comportamiento de la Quebrada Grande, la cual entre otras presenta las siguientes características.

![](/Imagen/Mapa 1.PNG)  
**Mapa 1**. Ubicación geográfica de la micro-cuenca Quebrada Grande. Fuente: Sanchez, 2020.

|Área (km2) | Perímetro (m) | Provincia | Distrito |
| ------ | -------- | -------- | -------- |
| 3.90 | 11900 | Heredia | Vara Blanca |

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

![](/Imagen/Rplot.png)  
**Grafico 1**. Caudal por año (puntos). Fuente: Sanchez, 2020.

```{r}
plot(
  Datos_stream$`Date`, 
  Datos_stream$`Q (L/s)`,
  main='Caudal',
  xlab='Año',
  ylab='Caudal Q (L/s)',
  type="l"
)
```
![](/Imagen/Rplot01.png)
**Grafico 2**. Caudal por año (lineas). Fuente: Sanchez, 2020.

Seguidamente se procedió a la visualización de los datos en una escala logarítimica, con el obejtivo de poder visualizar de mejor manera el comportamiento del caudal durante el periodo de análisis.

```{r}
ggplot(Datos_stream, aes(x = Date, y = `Level (cm)`))+
  geom_line()+
  scale_y_log10()
```
![](/Imagen/caudal log10.png)

**Grafico 2**. Caudal por año caudal (escala log10). Fuente: Sanchez, 2020.

Análisis estacional:







