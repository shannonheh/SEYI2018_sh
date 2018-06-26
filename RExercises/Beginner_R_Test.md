#Beginner R Test#
1. class = "data.frame"; function = class(mtcars)
2. I could use the "length()" function to retrieve the vector size, but got NULL when I tried to use "dim()" to retrieve the array size. OR is(precip,"vector) returns TRUE.
3. trees <- as(trees,"matrix")
4. Atlanta
5. list(mtcars,trees,precip)
6. Yes numeric, typeof(precip) returns "double"
7. (1) mtcars[2][7], (2) mtcars["Mazda RX4 Wag",7], (3) mtcars[2,"qsec"], (4) mtcars["Mazda RX4 Wag", "qsec"]
8. precip["Juneau"] <- 23,  precip["Phoenix"] <- 46,  precip["Sacramento"] <- 12
9. No, any(trees["Girth"] > trees["Volume"]) returns FALSE
10. 2356.628