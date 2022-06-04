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

# Install the cluster package and run its library  
install.packages("cluster")  
library(cluster)  

# First I look for the path of our folder to get the csv we are looking for in an easier way.   
getwd()  
setwd("C:/Users/Ivonne/Desktop/iris")  
getwd()  

# We import the dataset and tell it that we are only going to use the vectors from 1 to 4.  
dataset = read.csv("iris.csv")  
dataset = dataset[1:4]  

# Let's run the model k means it's installed in the base R package. We put randomness, in the kmeans function, we  need to set the center, which is the number of groups we want and they are grouped. We know this value will be 3  and we are going to set that   
set.seed(101)  
ClusterIris <- kmeans(iris[,1:4], center=3, nstart = 20)  
ClusterIris  

# Hacemos el plots de los clusters  
clusplot(iris, ClusterIris$cluster, color = T, shade = T, labels = 0, lines = 0)  

# Aplicamos el método del codo para ver la implementación de los datos y dónde  se encuentra el punto de quiebre de la gráfica.  
tot.withinss <- vector(mode="character", length=10)  
for(i in 1:10)  
{
 ClusterIris <- kmeans (dataset[,1:4], center=i, nstart=20)  
  tot.withinss[i] <- ClusterIris$tot.withinss  
}  

# Aquí podemos visualizar el método  

plot(1:10, tot.withinss, type="b", pch=19)  