## VERIFICATION OF THE LAW OF NUMBERS

Create an R script that will count how many of these numbers fall between -1 and 1 and divide
by the total quantity of N  

You know that E(X) = 68.2%
Check that Mean(Xn)->E(X) as you rerun your script while increasing N  

1. Initialize sample size  
x <- rnorm(10)
y <- dnorm(x, mean = 0, sd = 1)
plot(x,y)

2. Initialize counter  
count <- 0
res <- 0

3. loop for(i in rnorm(size))  

for(i in rnorm(10))
{
  count <- count + 1
  print(count)

  4. Check if the iterated variable falls  
  
  if(i <= 1 && i >= -1)
  {
    print(i)
    print("It is between -1 y 1")

 5. Increase counter if the condition is true  
    res <- res +1
  }
  else
  {
    print (i)
    print ("Out of range")
    
  }
}
6. return a result <- counter / N  
Res <- res / count
print(Res)

