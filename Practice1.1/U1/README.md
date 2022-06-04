
## GRAPHS
We execute the libraries to be able to make the graphs  

install.packages("tidyverse")  
library(tidyverse)  

We export the cvs file and look at it  
base <- read.csv("base_ggplot.csv")  
base  

dim(base)  

#grafica  

install.packages("ggplot2")  
library(ggplot2)    
install.packages("dslabs")    
library(dslabs)     

Total motivation vs. total satisfaction will be compared  

grafico_base <- ggplot(data = base)+  
  aes(x  = motivacion_total, y = satisfaccion_total, color = sexo)+  
  geom_point()  

 grafico_base +   
  labs(title = "Grafica de Dispersion entre motivacion y satisfaccion",  
       subtitle = "En jovenes entre 18 y 37 años",  
       x= "Motivacion", y = "Satisfaccion",  
       caption = "Mineria de datos")  



#..................... 2da Grafica.................  

The two lines that are observed perform what are the facet graphs  

a <-ggplot(base,aes(x =motivacion_total))+ geom_bar(fill= "Red2")  
a + theme_classic()  

In this command the comparisons are indicated.  
ggplot (base,aes(x =edad ))+ geom_bar(aes(fill = sexo), position= "dodge")  


       
#..................... 3ero Grafica.................  

Here a dot plot was used to perform age and motivation statistics using theme  
ggplot(base, aes(x = edad, y =motivacion_total ))+ geom_point()+ geom_point(aes (color = sexo))+  
  theme_light()  