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
