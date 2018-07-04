## Advanced R Test ##

1. NewFunction <- function(String) {  
print(String)  
}  
NewFunction("Hello World")

1.  NewFunction <- function(DataSet) {  
Setosa <- iris[which(DataSet[,"Species"]=="setosa"),]  
Virginica <- iris[which(DataSet[,"Species"]=="virginica"),]  
Versicolor <- iris[which(DataSet[,"Species"]=="versicolor"),]   
return(list(Setosa, Virginica, Versicolor))  
}

2.  NewVector <- array(data=NA,dim=dim(iris)[1]) 
IndexVector <- 1:dim(iris)[1]   
NewFunction <- function(DataSet) {  
for(Index in IndexVector) {  
if (DataSet[Index,"Sepal.Width"]>3.1) {  
NewVector[Index] <- DataSet[Index,"Sepal.Length"] + DataSet[Index,"Petal.Length"]  
}
else if (DataSet[Index,"Sepal.Width"]<3.1) {  
NewVector[Index] <- DataSet[Index,"Sepal.Length"] - DataSet[Index,"Petal.Length"]  
}  
}  
return(NewVector)
}  

3. mpgVector <- vector(mode="numeric", length=nrows(mtcars)
avgMPG <- function(numCylinder)  {  
mpgVector <- mtcars$mpg[which(mtcars[,"cyl"]==numCylinder)]
return(mean(mpgVector)  
}  

4. drawings <- function(numDrawings) {  
powerball <- matrix(data=NA, nrow=numDrawings, ncol=6)
for (draw in 1:numDrawings){  
powerball[draw,1:5] <- sample(c(1:69), 5, replace=FALSE)
powerball[draw,6] <- sample(c(1:26),1,replace=TRUE)  
}  
return(powerball)  
}  

5. drawings <- function(lotteryNumbers) {  
powerball <- matrix(data=NA, nrow=numDrawings, ncol=6)  
for (draw in 1:1000000) {    
powerball[draw,1:5] <- sample(c(1:69), 5, replace=FALSE)  
powerball[draw,6] <- sample(c(1:26),1,replace=TRUE)  
}     
Test <- vector(data="logical",nrow=1000000)  
for (i in 1:1000000) {  
Test[i] <- all(powerball[i,]==lotteryNumbers)    
}  
return(any(Test))  
}  


