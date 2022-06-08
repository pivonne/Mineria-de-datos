<p align="center"> 
  <img src="/ImagesU4/TitleU4.jpg" />
</p>

> # Tecnológico Nacional de México Instituto Tecnológico de Tijuana
>
>
> **Departamento de Sistemas y Computación Ingeniería en Sistemas Computacionales**
>
> **Semestre**<br>
> Enero-Junio 2022
>
> **Materia**<br>
>Mining Data
>
> **Docente**<br>
> JOSE CHRISTIAN ROMERO HERNANDEZ
>
> **Unidad:** 4
>
> **Titulo**
> Practica 5
>
> **Alumnos**<br>
> Anahi Del Carmen Hernandez Pablo *18210486* <br>
> Pérez Mora Ana Ivonne		18212074

# Content



```js
Instrucciones
Desarrolle el siguiente problema con R y RStudio para la extracción de conocimiento
que el problema require.
Implementar el modelo de agrupación K-Means con el conjunto de datos Iris.csv que
se encuentra en https://github.com/jcromerohdz/iris utilizando el método
kmeans() en R. Una vez que se obtenga el modelo de agrupamiento hacer el analisis
de visualización de datos correspondiente.
Al finalizar el desarrollo explicar detalladamente en consiste el modelo de
agrupación K-Means y cuales fuerón sus observacines en el analisis de visualización
de datos.
```


```js
# Install the cluster package and run its library  
install.packages("cluster")  
library(cluster)  

```

<p align="center"> 
  <img src="/ImagesU4/imw1.jpg" />
</p>

```js
# First I look for the path of our folder to get the csv we are looking for in an easier way.   
getwd()  
setwd("C:/Users/Ivonne/Desktop/iris")  
getwd()  
```

<p align="center"> 
  <img src="/ImagesU4/imw2.jpg" />
</p>


```js
# We import the dataset and tell it that we are only going to use the vectors from 1 to 4.  
dataset = read.csv("iris.csv")  
dataset = dataset[1:4]  

```
<p align="center"> 
  <img src="/ImagesU4/imw3.jpg" />
</p>


```js
# Let's run the model k means it's installed in the base R package. We put randomness, in the kmeans function, we  need to set the center, which is the number of groups we want and they are grouped. We know this value will be 3  and we are going to set that   
set.seed(101)  
ClusterIris <- kmeans(iris[,1:4], center=3, nstart = 20)  
ClusterIris  
```
<p align="center"> 
  <img src="/ImagesU4/imw4.jpg" />
</p>

```js
# Hacemos el plots de los clusters  
clusplot(iris, ClusterIris$cluster, color = T, shade = T, labels = 0, lines = 0)  

```
<p align="center"> 
  <img src="/ImagesU4/imw5.jpg" />
</p>

```js
# Aplicamos el método del codo para ver la implementación de los datos y dónde  se encuentra el punto de quiebre de la gráfica.  
tot.withinss <- vector(mode="character", length=10)  
for(i in 1:10)  
{
 ClusterIris <- kmeans (dataset[,1:4], center=i, nstart=20)  
  tot.withinss[i] <- ClusterIris$tot.withinss  
}  
```

<p align="center"> 
  <img src="/ImagesU4/imw6.jpg" />
</p>

<p align="center"> 
  <img src="/ImagesU4/imw7.jpg" />
</p>

<p align="center"> 
  <img src="/ImagesU4/imw8.jpg" />
</p>

```js
# Aquí podemos visualizar el método  

plot(1:10, tot.withinss, type="b", pch=19)  
```


<p align="center"> 
  <img src="/ImagesU4/imw9.jpg" />
</p>

<p align="center"> 
  <img src="/ImagesU4/imw10.jpg" />
</p>












