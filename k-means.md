# Implementacion de K-means en R.

K-medias es un método que tiene como objetivo generar una partición de un conjunto de n observaciones en k grupos. Cada grupo está representado por el promedio de los puntos que lo componen. El representante de cada grupo se denomina centroide. La cantidad de grupos a descubrir, k, es un parámetro que se debe fijar a priori. El método de clustering comienza con k centroides ubicados de forma aleatoria, y asigna cada observación al centroide más cercano. Después de asignarlos, los centroides se mueven a la ubicación promedio de todos los datos asignados a él, y se vuelven a reasignar los puntos de acuerdo a las nuevas posiciones de los centroides. 

## A continuacion se presentara la implementacion de dicho metodo en el lenguaje R con el dataframe Iris. 

Install the dependencies and devDependencies and start the server.

```sh
ipak <- function(pkg){
  new.pkg <- pkg[!(pkg %in% installed.packages()[, "Package"])]
  if (length(new.pkg)) 
    install.packages(new.pkg, dependencies = TRUE)
  sapply(pkg, require, character.only = TRUE)
}
```
```sh
packages <- c("stats","dplyr", "ggplot2","ggfortify","tidyr","tidyverse","cluster","factoextra","NbClust","tidyr")
ipak(packages)
```
```sh
view(iris)

df = select(iris,c(1,2,3,4))
df
```

Con esta función se pueden calcular varios metodos que deterinan cuantos clusters son los adecuados
```sh
resnumclust<-NbClust(df, distance = "euclidean", min.nc=2, max.nc=10, method = "kmeans", index = "alllong")
fviz_nbclust(resnumclust)
```
```sh
k2 <- kmeans(df, centers = 2, nstart = 25)
k2
str(k2)
```
```sh
#plotear los cluster
fviz_cluster(k2, data = df)
fviz_cluster(k2, data = df, ellipse.type = "euclid",repel = TRUE,star.plot = TRUE) #ellipse.type= "t", "norm", "euclid"
fviz_cluster(k2, data = df, ellipse.type = "norm")
fviz_cluster(k2, data = df, ellipse.type = "norm",palette = "Set2", ggtheme = theme_minimal())
```
