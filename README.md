# r-programming-assignments
Repository for R Programming Assignments
Rayhan Khan
LIS4370

## Module 2 Assignment – myMean Function

This repository contains the corrected myMean function for Module #2.
Corrected R Code:

> assignment2 <- c(16, 18, 14, 22, 27, 17, 19, 17, 17, 22, 20, 22)
> myMean <- function(assignment2) {
+   return(sum(assignment2) / length(assignment2))
+ }
> 
> myMean(assignment2)
[1] 19.25
> 

Blog Post:
A detailed explanation of the error in the original function, why it failed, and the corrected version is available at the following link:
https://rayhankhanlis4730.blogspot.com/2026/01/module-2-assignment.html

## Module 3 Assignment – Data Frame Analysis

This repository contains the R code for Module #3, which focuses on creating and working with data frames using fictional 2016 presidential polling data from two sources (ABC and CBS).

R Code:

# Create vectors

Name <- c("Jeb", "Donald", "Ted", "Marco", "Carly", "Hillary", "Bernie")

ABC <- c(4, 62, 51, 21, 2, 14, 15)

CBS <- c(12, 75, 43, 19, 1, 21, 19)



# Create data frame

poll_results <- data.frame(Name, ABC, CBS)



# View data frame

poll_results



# Compare polls

poll_results$Difference <- poll_results$CBS - poll_results$ABC

poll_results


Output: 

> # Compare polls
> poll_results$Difference <- poll_results$CBS - poll_results$ABC
> poll_results
     Name ABC CBS Difference
1     Jeb   4  12          8
2  Donald  62  75         13
3     Ted  51  43         -8
4   Marco  21  19         -2
5   Carly   2   1         -1
6 Hillary  14  21          7
7  Bernie  15  19          4
> 

Blog Post:

A discussion of the results, including a comparison of polling data and a reflection on the use of data frames in R, is available at the following link:

https://rayhankhanlis4730.blogspot.com/2026/02/module-3-assignment.html

## Module 4 Assignment – Hospital Patient Data Analysis

This repository contains the R code for Module #4, which involves analyzing hospital patient data using boxplots and histograms.

R Code:

> # Create the data vectors
> Frequency <- c(0.6, 0.3, 0.4, 0.4, 0.2, 0.6, 0.3, 0.4, 0.9, 0.2)
> 
> BloodPressure <- c(103, 87, 32, 42, 59, 109, 78, 205, 135, 176)
> 
> First <- c("bad", "bad", "bad", "bad", "good", "good", "good", "good", NA, "bad")
> 
> Second <- c("low", "low", "high", "high", "low", "low", "high", "high", "high", "high")
> 
> FinalDecision <- c("low", "high", "low", "high", "low", "high", "low", "high", "high", "high")
> 
> # Create data frame
> hospital_data <- data.frame(Frequency, BloodPressure, First, Second, FinalDecision)
> 
> hospital_data
   Frequency BloodPressure First Second FinalDecision
1        0.6           103   bad    low           low
2        0.3            87   bad    low          high
3        0.4            32   bad   high           low
4        0.4            42   bad   high          high
5        0.2            59  good    low           low
6        0.6           109  good    low          high
7        0.3            78  good   high           low
8        0.4           205  good   high          high
9        0.9           135  <NA>   high          high
10       0.2           176   bad   high          high
> 
> 
> # Create boxplot of Blood Pressure
> boxplot(BloodPressure,
+         main="Boxplot of Patient Blood Pressure",
+         ylab="Blood Pressure",
+         col="lightblue")
> 
> 
> # Create histogram of Blood Pressure
> hist(BloodPressure,
+      main="Histogram of Patient Blood Pressure",
+      xlab="Blood Pressure",
+      col="lightgreen")
> 
Blog Post:

https://rayhankhanlis4730.blogspot.com/2026/02/module-4-programming-structure.html

## Module 5 Assignment – Doing Math

This repository contains the R code for Module #5, which focuses on working with matrices, determinants, and matrix inverses in R.

Blog link:
https://rayhankhanlis4730.blogspot.com/2026/02/module-5-doing-math.html

R Code:

> # Create matrices
> A <- matrix(1:100, nrow=10)
> B <- matrix(1:1000, nrow=10)
> 
> # Check dimensions
> dim(A)
[1] 10 10
> dim(B)
[1]  10 100
> 
> # Determinants
> detA <- det(A)
> detA
[1] 0
> 
> # Inverses
> invA <- tryCatch(solve(A), error=function(e) e)
> invB <- tryCatch(solve(B), error=function(e) e)
> 
> invA
<simpleError in solve.default(A): Lapack routine dgesv: system is exactly singular: U[3,3] = 0>
> invB
<simpleError in solve.default(B): 'a' (10 x 100) must be square>
> 
> # Determinant of B
> detB <- tryCatch(det(B), error=function(e) e)
> detB
<simpleError in determinant.matrix(x, logarithm = TRUE, ...): 'x' must be a square matrix>

Explanation:

I made two matrices in R for Module #5:
A <- matrix(1:100, nrow=10) and B <- matrix(1:1000, nrow=10).
I verified that A and B are 10x10 square and 10x100 non-square matrices, respectively, using dim(). I then used det(A) to determine the determinant of A. The outcome was zero, indicating that A is a singular matrix without an inverse. R gave me an error stating that the matrix is singular (not invertible) when I tried to compute the inverse using solve(A). Since determinants and inverses are only defined for square matrices, det(B) and solve(B) failed for matrix B since B is not square.

## Module 6 Assignment – Doing Math in R (Part 2)

This repository contains the R code for Module #6, which focuses on matrix operations, use of the diag() function, and structured matrix construction in R.

Blog link:
https://rayhankhanlis4730.blogspot.com/2026/02/module-6-doing-math-in-r-part-2.html

R Code:

> # 1) Matrices A and B
> A <- matrix(c(2,0,1,3), ncol=2)
> B <- matrix(c(5,2,4,-1), ncol=2)
> 
> A
     [,1] [,2]
[1,]    2    1
[2,]    0    3
> B
     [,1] [,2]
[1,]    5    4
[2,]    2   -1
> 
> # a) A + B
> A_plus_B <- A + B
> A_plus_B
     [,1] [,2]
[1,]    7    5
[2,]    2    2
> 
> # b) A - B
> A_minus_B <- A - B
> A_minus_B
     [,1] [,2]
[1,]   -3   -3
[2,]   -2    4
> 
> 
> # 2) diag() matrix size 4 with diagonal values 4,1,2,3
> D <- diag(c(4,1,2,3))
> D
     [,1] [,2] [,3] [,4]
[1,]    4    0    0    0
[2,]    0    1    0    0
[3,]    0    0    2    0
[4,]    0    0    0    3
> 
> 
> # 3) Generate the 5x5 matrix using diag()
> M <- diag(3, 5)      # start with 3s on the diagonal
> M[1, 2:5] <- 1       # first row (cols 2-5) become 1
> M[2:5, 1] <- 2       # first column (rows 2-5) become 2
> M
     [,1] [,2] [,3] [,4] [,5]
[1,]    3    1    1    1    1
[2,]    2    3    0    0    0
[3,]    2    0    3    0    0
[4,]    2    0    0    3    0
[5,]    2    0    0    0    3

Explanation:

I made two 2x2 matrices, A and B, in R for Module #6, and then used fundamental matrix operations to get A + B and A - B. As long as the dimensions of the matrices are the same, R can add and remove them element by element. My A + B and A - B outputs were in line with the anticipated element-wise computations. I then created a 4x4 matrix with diagonal values of 4, 1, 2, and 3 using the diag() method. Lastly, I used diag() to create the necessary 5x5 matrix by first creating a diagonal matrix of 3s and then changing the first row and first column to fit the assignment's pattern. This demonstrated how diag() may be used to quickly create organized matrices and then modify particular rows and columns.


## Module 7 Assignment – R Objects: S3 vs S4

This repository contains the R code for Module #7, which uses the mtcars dataset to explore generic functions and compares S3 vs S4 object systems in R.

Blog Link: https://rayhankhanlis4730.blogspot.com/2026/03/module-7-r-object-s3-vs-s4-assignment.html

R Code:
> # Step 1: Load a dataset
> data(mtcars)
> head(mtcars, 6)
                   mpg cyl disp  hp drat    wt  qsec vs am
Mazda RX4         21.0   6  160 110 3.90 2.620 16.46  0  1
Mazda RX4 Wag     21.0   6  160 110 3.90 2.875 17.02  0  1
Datsun 710        22.8   4  108  93 3.85 2.320 18.61  1  1
Hornet 4 Drive    21.4   6  258 110 3.08 3.215 19.44  1  0
Hornet Sportabout 18.7   8  360 175 3.15 3.440 17.02  0  0
Valiant           18.1   6  225 105 2.76 3.460 20.22  1  0
                  gear carb
Mazda RX4            4    4
Mazda RX4 Wag        4    4
Datsun 710           4    1
Hornet 4 Drive       3    1
Hornet Sportabout    3    2
Valiant              3    1
> 
> # Step 2: Check if generic functions can be used on this dataset
> class(mtcars)
[1] "data.frame"
> typeof(mtcars)
[1] "list"
> isS4(mtcars)
[1] FALSE
> 
> # Generic functions examples
> summary(mtcars)
      mpg             cyl             disp      
 Min.   :10.40   Min.   :4.000   Min.   : 71.1  
 1st Qu.:15.43   1st Qu.:4.000   1st Qu.:120.8  
 Median :19.20   Median :6.000   Median :196.3  
 Mean   :20.09   Mean   :6.188   Mean   :230.7  
 3rd Qu.:22.80   3rd Qu.:8.000   3rd Qu.:326.0  
 Max.   :33.90   Max.   :8.000   Max.   :472.0  
       hp             drat             wt       
 Min.   : 52.0   Min.   :2.760   Min.   :1.513  
 1st Qu.: 96.5   1st Qu.:3.080   1st Qu.:2.581  
 Median :123.0   Median :3.695   Median :3.325  
 Mean   :146.7   Mean   :3.597   Mean   :3.217  
 3rd Qu.:180.0   3rd Qu.:3.920   3rd Qu.:3.610  
 Max.   :335.0   Max.   :4.930   Max.   :5.424  
      qsec             vs               am        
 Min.   :14.50   Min.   :0.0000   Min.   :0.0000  
 1st Qu.:16.89   1st Qu.:0.0000   1st Qu.:0.0000  
 Median :17.71   Median :0.0000   Median :0.0000  
 Mean   :17.85   Mean   :0.4375   Mean   :0.4062  
 3rd Qu.:18.90   3rd Qu.:1.0000   3rd Qu.:1.0000  
 Max.   :22.90   Max.   :1.0000   Max.   :1.0000  
      gear            carb      
 Min.   :3.000   Min.   :1.000  
 1st Qu.:3.000   1st Qu.:2.000  
 Median :4.000   Median :2.000  
 Mean   :3.688   Mean   :2.812  
 3rd Qu.:4.000   3rd Qu.:4.000  
 Max.   :5.000   Max.   :8.000  
> plot(mtcars$mpg, mtcars$hp)
> 
> # What is a generic function?
> mean
function (x, ...) 
UseMethod("mean")
<bytecode: 0xa155718f8>
<environment: namespace:base>
> 
> # Step 3: Create an S3 example
> 
> s3 <- list(name = "Myself", age = 29, GPA = 3.5)
> class(s3) <- "student"
> 
> s3
$name
[1] "Myself"

$age
[1] 29

$GPA
[1] 3.5

attr(,"class")
[1] "student"
> class(s3)
[1] "student"
> typeof(s3)
[1] "list"
> isS4(s3)
[1] FALSE
> 
> # Step 4: Create an S4 example
> 
> setClass("student",
+          slots = list(
+            name = "character",
+            age  = "numeric",
+            GPA  = "numeric"
+          ))
> 
> s4 <- new("student", name = "Myself", age = 29, GPA = 3.5)
> 
> s4
An object of class "student"
Slot "name":
[1] "Myself"

Slot "age":
[1] 29

Slot "GPA":
[1] 3.5

> class(s4)
[1] "student"
attr(,"package")
[1] ".GlobalEnv"
> typeof(s4)
[1] "S4"
> isS4(s4)
[1] TRUE

Explanation: 
I utilized R's built-in mtcars dataset for Module #7. Since class(mtcars) returns "data.frame" and isS4(mtcars) returns FALSE, I was able to verify that mtcars is an S3 object. Additionally, I used typeof(mtcars) to verify its base type, and it returned "list". I next evaluated the dataset's suitability for generic functions. Because they employ method dispatch, generic methods like summary() and plot() are compatible with mtcars. For instance, the function summary.data.frame() is called by summary(mtcars). A generic function is one that, depending on the object's class, chooses the appropriate method; in R, many generics display UseMethod() when printed. Lastly, I produced S3 and S4 samples. In S3, I used a list to create a student object, and then I gave it a class attribute (class(s3) <- "student"). I used setClass() with slots to explicitly define a student class for S4, and I then used new() to construct an instance. The primary distinction is that S4 is formal, has predetermined slots, and enforces a more rigid structure, whereas S3 is informal and flexible.
