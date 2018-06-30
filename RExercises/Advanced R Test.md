##Advanced R Test ##

1. Print Hello World

NewFunction <- function(String) {  
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


