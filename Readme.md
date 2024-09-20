# R tutorial
* Download R in the following link - https://cran.r-project.org/bin/windows/base/
* Downloadd R extension in Vscode
* To run in Vscode - ctrl+shift+s

## Objects
* R has five basic or atomic class of objects
    * Charater
    * Numberic
    * Integer
    * Complex
    * Logical (True/False)
* The most basic object is `vector`
* empty vectore is created with vector() function

## Number
* Treated as numberic Object(double precision real number)
* If we explicitely want an integer the made `L` as suffix `1L`
* There is a Special number `inf` which represent infinity (1/0)
* The is also a number NaN (Not a Number) which will come when there is a missing value
    ```R
    print(0/0)
    ```
## Attributes
* R object can have Attributes
* names,dimnames
* Atteribute of an object can be accessed using `attributes()` function
## Entering Input
* in R `<-` is an assignment operator
* And for single ine comment we use `#`
* s <- ## (this is incomplete expression)   
```r
x <- 5
print(x)
# This is comment
y <- ## This is incomplete expression 
2
# Now the value of y is 2
```
## Evaluation
* when a compelete expression is entered at the prompt ,It is evaluated and result of the evaluated expression is returned . The result may be auto printed
```r
x <- 5 # nothing printed
x # Auto printed
print(x) # Explicit printed
```
* op - [1] 5 , Here [1] indicated that x is a vector and 5 is the first element
* `ctrl+l` is used to clear the content in console

## printing
* The `:` operator is used to create integer sequences
```r
x <- 1:20
print(x)
[1]   1   2   3   4   5   6   7   8   9  10  11  12  13  14  15  16  17  18
[19]  19  20 
```

## Creating Vectors
* The c() function is used to create vector of objects
```r
x <- c(0.5,0.6) # Numeric
print(x)
x <- c(TRUE,FALSE) # Boolean
print(x)
x <- c(T,F) # boolean
print(x)
x <- c("a","b","c") # character
print(x)
x <- c("all","bec","coz") # String
print(x)
x <- 10:30 # Integer
print(x)
x <- c(1+0i,5+5i) # Complex
print(x)
[1] 0.5 0.6
[1]  TRUE FALSE
[1]  TRUE FALSE
[1] "a" "b" "c"
[1] "all" "bec" "coz"
[1] 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30
[1] 1+0i 5+5i
```
## Learn about Mixing object in R
## Explicit coercion
* Objects can be explicitly coerced from one class to another using `as.*` function 
```r
x <- 0:6
print(class(x)) # "integer"
y <- as.logical(x)  
print(y) # FALSE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE
z <- as.character(x)
print(z) # "0" "1" "2" "3" "4" "5" "6"
a <- as.complex(x)
print(a) # 0+0i 1+0i 2+0i 3+0i 4+0i 5+0i 6+0i
```
### nonsensical corecion results in NAs
```r
x <- c("a","b","c")
y <- as.numeric(x)
print(y) # NA NA NA
z <- as.logical(x)
print(z) # NA NA NA
In console
Warning message:
In eval(ei, envir) : NAs introduced by coercion
```
## Matrix
* It is a 2 dimensional Array
```r
mat <- matrix(nrow = 4,ncol = 4)
print(dim(mat)) # 4 4 
print(attributes(mat)) # $dim
```
* it is constructed in column Wise
```r
mat = matrix(1:9,nrow = 3,ncol = 3)
print(mat)
     [,1] [,2] [,3]
[1,]    1    4    7
[2,]    2    5    8
[3,]    3    6    9
```
* We cant convert the vector to the matrix
```r
mat = 1:9
print(mat) # 1 2 3 4 5 6 7 8 9
dim(mat) <- c(3,3)
print(mat) # Convert to matrix 
```
## cbinding and rbinding
* rbind means row bindinng and cbind means column binding
```r
x <- 1:3
y <- 5:10
print(cbind(x,y))
     x  y
[1,] 1  5
[2,] 2  6
[3,] 3  7
[4,] 1  8
[5,] 2  9
[6,] 3 10
print(rbind(x,y))
  [,1] [,2] [,3] [,4] [,5] [,6]
x    1    2    3    1    2    3
y    5    6    7    8    9   10
```
## Lists
* It is a special type of vector Where we can have elements with different class
* We cant create list using `list()` function
```r
c <- list (1,"s",3.5,4+0i)
print(c)
[[1]]
[1] 1

[[2]]
[1] "s"

[[3]]
[1] 3.5

[[4]]
[1] 4+0i
```