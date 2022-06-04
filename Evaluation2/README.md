<p align="center"> 
  <img src="/Imagen/Title.png" />
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
> Mineria de Datos
>
> **Docente**<br>
> JOSE CHRISTIAN ROMERO HERNANDEZ
>
> **Unidad:** 2
>
> **Titulo**
> Practica 5
>
> **Alumnos**<br>
> Anahi Del Carmen Hernandez Pablo *18210486* <br>
>  Pérez Mora Ana Ivonne  	  18212074

# Content

```js
//We export the document that contains the data in csv format, once the  
document we execute the ggplot2 library to be able to make the graph.    

DataBase <- leer.csv(file.choose())      
library (ggplot2)    
DataBase    

```

<p align="center"> 
  <img src="/Imagen/im1.png" />
</p>


```js
/We filter all movie genres shown in the data.    
filtracion <- (DataBase$Genre == "action") | (DataBase$Genre == "adventure") |(DataBase$Genre   ==  "animation")   |  
  (DataBase$Genre   ==  "comedy") |(DataBase$Genre == "drama")2   
```
<p align="center"> 
  <img src="/Imagen/im2.png" />
</p>

```js
//In this other leak, only the name of the company that carried out the leak will be shown film.    

filtracion2   <-   DataBase$Studio   %in%   c("Buena   Vista   Studios",  "WB",  "Fox","Universal",  "Sony",  "Paramount   Studios")  

filtracion  
filtracion2  
```

<p align="center"> 
  <img src="/Imagen/im3.png" />
</p>
```js
//It was necessary to carry out a second data frame since reference is made to the two filters created earlier.   
<br> DataBase2 <- mydata[filtro & filtracion2,]  
DataBase2   
```

<p align="center"> 
  <img src="/Imagen/im4.png" />
</p>

```js
//For the realization of the graph we will only use the variable of DataBase 2, already in es that's where all the leaked data is.  

Grafica <- ggplot(data=DataBase2, aes(x=Genre, y=Gross...US))+  geom_jitter(aes(size=Budget...mill., colour=Studio))+  
geom_boxplot(alpha = 0.8, outlier.color = NA)+  scale_size_continuous(range = c(1, 3))+    
xlab("Genre")+  ylab("Gross % US")+    
ggtitle("Domestic Gross % by Genre")+    
theme(    axis.title.x = element_text(colour = "Blue", size=15),    
axis.title.y = element_text(colour = "Blue", size=15),   
 axis.text.x = element_text(size=10),      
 axis.text.y = element_text(size=10),     
plot.title = element_text(size=20),     
legend.title = element_text(size=10),  
text = element_text(family = "sans")  
  )  

```
<p align="center"> 
  <img src="/Imagen/im5.png" />
</p>


```js
Grafica 
```

<p align="center"> 
  <img src="/Imagen/im6.png" />
</p>





 



 
