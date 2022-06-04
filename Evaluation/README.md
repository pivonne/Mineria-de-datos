<p align="center"> 
  <img src="/Images/Title.png" />
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
> Practica evaluatoria U2
>
> **Alumnos**<br>
> Anahi Del Carmen Hernandez Pablo *18210486* <br>
> Pérez Mora Ana Ivonne  	    18212074


# Content

```js
Instructions
Develop the following problem with R and RStudio for knowledge extraction
that the problem requires.
The directors of the movie review website are very happy with your
previous delivery and now they have a new requirement for you.
```

 

```js

# We import the packages to be able to carry out the evaluation   
install.packages ("caret")  
install.packages ("caTools")  
install.packages ("ElemStatLearn")  
install.packages("e1071")  
install.packages("lattice")  
library(e1071)  
library (caret)  
library(lattice)  
library(ggplot2)  
library(caTools)  
library(ElemStatLearn) 
```
<p align="center"> 
  <img src="/Imagen/im1.png" />
</p>

```js
# Importing the dataset  
#data <- read.csv('Social_Network_Ads.csv')  
data<- (file.choose())    
dataset=data  
dataset = data[3:5]  
dataset$Purchased=factor(dataset$Purchased, levels = c(0,1)) 
```

```js
# Split the dataset into the training set and the test set  
set.seed(123)    
split <- sample.split(dataset$Purchased, SplitRatio = 0.75)  
training_set <- subset(dataset, split == TRUE)  
test_set <- subset(dataset, split == FALSE)  
training_set[-3]=scale(training_set[-3])  
test_set[-3] = scale(test_set[-3])  
```


```js
# We use a classifier which will enter the results that we shows NaiveBayes  
classifier = naiveBayes(formula = Purchased ~ .,    
                        data=training_set,  
                        type='c-classification',  
                        kernel = 'linear')  
naiveBayes  

```


```js
# Prediction of results  
y_pred=predict(classifier, newdata = test_set[-3])  
y_pred  
```

```js
# Create the confusion matrix  
cm = table(test_set[, 3], y_pred)  
cm  

```

```js
# Visualizing the training set results  
set=training_set  
x1=seq(min(set[, 1]) - 1, max(set[, 1]) +1, by =0.01)  
x2=seq(min(set[, 2]) - 1, max(set[, 2]) +1, by =0.01)  
grid_set=expand.grid(x1,x2)  
colnames(grid_set)=c('Age', 'Estimated salary')  
y_grid=predict(classifier,newdata=grid_set)  
plot(set[, -3],  
     main='Native Bayes (Training set)',  
     xlab = 'Age', ylab = 'Estimated salary',  
     xlim = range(x1), ylim=range(x2))  
contour(x1, x2, matrix(as.numeric(y_grid), length(x1), length(x2)), add=TRUE)  
points(grid_set, pch = '.', col = ifelse(y_grid == 1, 'springgreen3', 'tomato'))  
points(set, pch = 21, bg = ifelse(set[, 3] == 1, 'green4', 'red3'))  


```

 

```js
# Visualising the Test set results  
set = test_set  
X1 = seq(min(set[, 1]) - 1, max(set[, 1]) + 1, by = 0.01)  
X2 = seq(min(set[, 2]) - 1, max(set[, 2]) + 1, by = 0.01)  
grid_set = expand.grid(X1, X2)  
colnames(grid_set) = c('Age', 'EstimatedSalary')  
y_grid = predict(classifier,newdata = grid_set)  
plot(set[, -3], main = 'Naive Bayes (Test set)',  
     xlab = 'Age', ylab = 'Estimated Salary',  
     xlim = range(X1), ylim = range(X2))  
contour(X1, X2, matrix(as.numeric(y_grid), length(X1), length(X2)), add = TRUE)  
points(grid_set, pch = '.', col = ifelse(y_grid == 1, 'springgreen3', 'tomato'))  
points(set, pch = 21, bg = ifelse(set[, 3] == 1, 'green4', 'red3'))  

```





