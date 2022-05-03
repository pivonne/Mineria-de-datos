#..................... graph 1................. 
#these libraries were used to generate the graphs 
install.packages("tidyverse") 
library(tidyverse) 
#the csv document was loaded 
base <- read.csv("base_ggplot.csv") 
base 

dim(base) 

#graph  
#the ggplot2 library was used  
install.packages("ggplot2") 
library(ggplot2) 

#here the first graph was generated 
grafico_base <- ggplot(data = base)+ 
  aes(x  = motivacion_total, y = satisfaccion_total, color = sexo)+ 
  geom_point() 

install.packages("dslabs") 

library(dslabs) 

 grafico_base + 
  labs(title = "Grafica de Dispersion entre motivacion y satisfaccion", 
       subtitle = "En jovenes entre 18 y 37 años", 
       x= "Motivacion", y = "Satisfaccion", 
       caption = "Mineria de datos") 


#here the second graph was generated using ggplot2
#..................... 2da Grafica................. 


a <-ggplot(base,aes(x =motivacion_total))+ geom_bar(fill= "Red2") 
a + theme_classic() 

ggplot (base,aes(x =edad ))+ geom_bar(aes(fill = sexo), position= "dodge") 


       
#..................... 3ero Grafica................. 
#Here the third graph was generated using ggplot2  

ggplot(base, aes(x = edad, y =motivacion_total ))+ geom_point()+ geom_point(aes  (color = sexo))+ 
  theme_light() 
       
       
       
       