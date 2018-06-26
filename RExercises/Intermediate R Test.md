#Intermediate R Exercises#


##Section 1##
1. replace = TRUE; sample with replacement. replace = FALSE; sample without replacement
2. MyMatrix*1
3. all(MyMatrix)

##Section 2##
1. 16 times
2. apply(MyMatrix, 2, sum)
3. apply(MyMatrix, 2, prod)
4. MyMatrix[which(MyMatrix==10)]<-12
5. 33 numbers
6. MyDataFrame <- as.data.frame(MyMatrix)
* MyDataFrame[,12] <- as.character(MyMatrix[,12])
7. MyDataFrame <- as.data.frame(MyMatrix)
* RowSums <- apply(MyMatrix,1,sum)>70
* MyDataFrame <- as.data.frame(MyMatrix)
* MyDataFrame$V13 <- RowSums


