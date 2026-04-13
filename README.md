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


## Module 8 Assignment – Input/Output, String Manipulation, and plyr

This repository contains the R code for Module #8, which focuses on importing a dataset, using the plyr package to calculate grouped averages, filtering names with a string condition, and writing results to files.

Blog Link: https://rayhankhanlis4370.blogspot.com/2026/03/module-8-inputoutput-string.html

R Code:
> # Step 1: Import dataset

> x <- read.table(file.choose(), header = TRUE, sep = ",")

> 

> # View dataset

> x

        Name Age    Sex Grade

1       Raul  25   Male    80

2     Booker  18   Male    83

3      Lauri  21 Female    90

4     Leonie  21 Female    91

5    Sherlyn  22 Female    85

6    Mikaela  20 Female    69

7    Raphael  23   Male    91

8       Aiko  24 Female    97

9   Tiffaney  21 Female    78

10    Corina  23 Female    81

11 Petronila  23 Female    98

12    Alecia  20 Female    87

13   Shemika  23 Female    97

14    Fallon  22 Female    90

15   Deloris  21 Female    67

16    Randee  23 Female    91

17     Eboni  20 Female    84

18   Delfina  19 Female    93

19 Ernestina  19 Female    93

20      Milo  19   Male    67

> 

> # Step 2: Install/load plyr and calculate mean Grade by Sex

> install.packages("plyr")

trying URL 'https://cran.rstudio.com/bin/macosx/big-sur-arm64/contrib/4.5/plyr_1.8.9.tgz'

Content type 'application/x-gzip' length 984753 bytes (961 KB)

==================================================

downloaded 961 KB





The downloaded binary packages are in

	/var/folders/3k/3m0n90_x4pj426bkxvf2p01h0000gn/T//RtmpFal0Bh/downloaded_packages

> library(plyr)

> 

> y <- ddply(x, "Sex", transform, Grade.Average = mean(Grade))

> 

> # View result

> y

        Name Age    Sex Grade Grade.Average

1      Lauri  21 Female    90       86.9375

2     Leonie  21 Female    91       86.9375

3    Sherlyn  22 Female    85       86.9375

4    Mikaela  20 Female    69       86.9375

5       Aiko  24 Female    97       86.9375

6   Tiffaney  21 Female    78       86.9375

7     Corina  23 Female    81       86.9375

8  Petronila  23 Female    98       86.9375

9     Alecia  20 Female    87       86.9375

10   Shemika  23 Female    97       86.9375

11    Fallon  22 Female    90       86.9375

12   Deloris  21 Female    67       86.9375

13    Randee  23 Female    91       86.9375

14     Eboni  20 Female    84       86.9375

15   Delfina  19 Female    93       86.9375

16 Ernestina  19 Female    93       86.9375

17      Raul  25   Male    80       80.2500

18    Booker  18   Male    83       80.2500

19   Raphael  23   Male    91       80.2500

20      Milo  19   Male    67       80.2500

> 

> # Step 3: Write the mean result to a CSV-style file

> write.table(y, "Sorted_Average", sep = ",", row.names = FALSE)

> 

> # Step 4: Filter names containing the letter i or I

> newx <- subset(x, grepl("[iI]", x$Name))

> 

> # View filtered dataset

> newx

        Name Age    Sex Grade

3      Lauri  21 Female    90

4     Leonie  21 Female    91

6    Mikaela  20 Female    69

8       Aiko  24 Female    97

9   Tiffaney  21 Female    78

10    Corina  23 Female    81

11 Petronila  23 Female    98

12    Alecia  20 Female    87

13   Shemika  23 Female    97

15   Deloris  21 Female    67

17     Eboni  20 Female    84

18   Delfina  19 Female    93

19 Ernestina  19 Female    93

20      Milo  19   Male    67

> 

> # Step 5: Write the filtered subset to a CSV-style file

> write.table(newx, "DataSubset", sep = ",", row.names = FALSE)

> 



Sorted_Average:

"Name","Age","Sex","Grade","Grade.Average"

"Lauri",21,"Female",90,86.9375

"Leonie",21,"Female",91,86.9375

"Sherlyn",22,"Female",85,86.9375

"Mikaela",20,"Female",69,86.9375

"Aiko",24,"Female",97,86.9375

"Tiffaney",21,"Female",78,86.9375

"Corina",23,"Female",81,86.9375

"Petronila",23,"Female",98,86.9375

"Alecia",20,"Female",87,86.9375

"Shemika",23,"Female",97,86.9375

"Fallon",22,"Female",90,86.9375

"Deloris",21,"Female",67,86.9375

"Randee",23,"Female",91,86.9375

"Eboni",20,"Female",84,86.9375

"Delfina",19,"Female",93,86.9375

"Ernestina",19,"Female",93,86.9375

"Raul",25,"Male",80,80.25

"Booker",18,"Male",83,80.25

"Raphael",23,"Male",91,80.25

"Milo",19,"Male",67,80.25



DataSubset:

"Name","Age","Sex","Grade"

"Lauri",21,"Female",90

"Leonie",21,"Female",91

"Mikaela",20,"Female",69

"Aiko",24,"Female",97

"Tiffaney",21,"Female",78

"Corina",23,"Female",81

"Petronila",23,"Female",98

"Alecia",20,"Female",87

"Shemika",23,"Female",97

"Deloris",21,"Female",67

"Eboni",20,"Female",84

"Delfina",19,"Female",93

"Ernestina",19,"Female",93

"Milo",19,"Male",67

Explanation: 
In order to get the mean grade for Module #8, I imported the Assignment 6 dataset into R and used the plyr tool using Sex as the category. After dividing the data by sex using the ddply() function, I created a new variable named Grade. I used the Grade column's mean to calculate the average. The average grade for female students was 86.9375, while the average grade for male students was 80.25, according to the data. I then used write.table() with comma separation to write this output to a file. I then created a new subset of the original dataset by filtering it so that only names with the letter i (including uppercase I) were included. To get those names, I used subset() in conjunction with grepl ("[iI]", x$Name). Students like Lauri, Leonie, Mikaela, Aiko, Corina, Petronila, Alecia, Shemika, Deloris, Eboni, Delfina, Ernestina, and Milo were included in the smaller dataset that resulted from this. Lastly, I created a second CSV-style file with this filtered subset. This assignment helped me practice importing data, using plyr to summarize grouped information, working with string matching, and exporting results to files.


## Module 9 Assignment – Visualization in R

This repository contains the R code for Module #9, which compares base graphics, lattice, and ggplot2 using the BankWages dataset.

Blog Post: https://rayhankhanlis4370.blogspot.com/2026/03/assignment-9-visualization-in-r-base.html

R Code:

> data <- read.csv(file.choose(), stringsAsFactors = FALSE)
> 
> head(data)
  rownames    job education gender minority
1        1 manage        15   male       no
2        2  admin        16   male       no
3        3  admin        12 female       no
4        4  admin         8 female       no
5        5  admin        15   male       no
6        6  admin        15   male       no
> str(data)
'data.frame':	474 obs. of  5 variables:
 $ rownames : int  1 2 3 4 5 6 7 8 9 10 ...
 $ job      : chr  "manage" "admin" "admin" "admin" ...
 $ education: int  15 16 12 8 15 15 15 12 15 12 ...
 $ gender   : chr  "male" "male" "female" "female" ...
 $ minority : chr  "no" "no" "no" "no" ...
> 
> data$rownames <- as.numeric(data$rownames)
> data$education <- as.numeric(data$education)
> 
> plot(data$rownames, data$education,
+      main = "Base: Education by Observation",
+      xlab = "Observation",
+      ylab = "Education",
+      col = "blue")
> 
> hist(data$education,
+      main = "Base: Distribution of Education",
+      xlab = "Education",
+      col = "lightgreen")
> 
> library(lattice)
> 
> xyplot(education ~ rownames | gender,
+        data = data,
+        main = "Lattice: Education by Observation and Gender")
> 
> bwplot(education ~ job,
+        data = data,
+        main = "Lattice: Education by Job Type")
> 
> library(ggplot2)
> 
> ggplot(data, aes(x = rownames, y = education, color = gender)) +
+   geom_point() +
+   geom_smooth(method = "lm") +
+   labs(title = "ggplot2: Education by Observation with Trend")
`geom_smooth()` using formula = 'y ~ x'
> 
> ggplot(data, aes(x = education)) +
+   geom_histogram(binwidth = 1, fill = "blue") +
+   facet_wrap(~ job) +
+   labs(title = "ggplot2: Education Distribution by Job Type")
> 

Explanation:

For Module #9, I compared three R visualization systems, base graphics, lattice, and ggplot2, using the BankWages dataset. I chose education as the primary numerical variable for visualization because the dataset includes variables such as rownames, jobs, education, and gender. I produced a scatter plot of education by observation number and a histogram illustrating the distribution of education using base R graphics. Although base visuals were simple and easy to use, each plot element had to be manually specified. Despite being straightforward, after the plot is established, they become less adaptable. I used bwplot() to compare education across job categories and xyplot() to show education by observation conditioned on gender using lattice graphics. Lattice improves cross-category comparison by making it simpler to work with grouped data and producing multi-panel charts automatically. Lastly, I made a scatter plot using ggplot2 that included a faceted histogram per job type and a regression line. Plot customization and extension are made easier by ggplot2's tiered architecture. In comparison to the other systems, it also generated graphics that were the clearest and most aesthetically pleasing. Lattice worked well for grouped and panel data, Base R was the most straightforward, and ggplot2 offered the greatest flexibility and high-quality visuals. The primary difficulty was adjusting to the various syntactic styles that each system employed.


## Module 11 Assignment – Debugging and Defensive Programming in R

This repository contains the corrected R code for Module #11, which focuses on debugging a logical error in a function that identifies Tukey outliers across matrix columns.

Blog Post: https://rayhankhanlis4370.blogspot.com/2026/04/assignment-11-debugging-and-defensive.html

R Code:

> tukey.outlier <- function(x, k = 1.5) {
+   q1 <- quantile(x, 0.25, na.rm = TRUE)
+   q3 <- quantile(x, 0.75, na.rm = TRUE)
+   iqr <- q3 - q1
+   x < (q1 - k * iqr) | x > (q3 + k * iqr)
+ }
> 
> tukey_multiple <- function(x) {
+   outliers <- array(TRUE, dim = dim(x))
+   for (j in 1:ncol(x)) {
+     outliers[, j] <- outliers[, j] & tukey.outlier(x[, j])
+   }
+   outlier.vec <- vector("logical", length = nrow(x))
+   for (i in 1:nrow(x)) {
+     outlier.vec[i] <- all(outliers[i, ])
+   }
+   return(outlier.vec)
+ }
> 
> set.seed(123)
> test_mat <- matrix(rnorm(50), nrow = 10)
> 
> tukey_multiple(test_mat)
 [1] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
[10] FALSE
> 
> corrected_tukey <- function(x) {
+   if (!is.matrix(x)) {
+     stop("x must be a matrix.")
+   }
+   if (!is.numeric(x)) {
+     stop("x must be a numeric matrix.")
+   }
+   
+   outliers <- array(TRUE, dim = dim(x))
+   for (j in seq_len(ncol(x))) {
+     outliers[, j] <- outliers[, j] & tukey.outlier(x[, j])
+   }
+   
+   outlier.vec <- logical(nrow(x))
+   for (i in seq_len(nrow(x))) {
+     outlier.vec[i] <- all(outliers[i, ])
+   }
+   
+   outlier.vec
+ }
> 
> corrected_tukey(test_mat)
 [1] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
[10] FALSE
> 

Explanation:

I used the test matrix included in the assignment to replicate the error in the tukey_multiple() function for Module #11. A warning notice stating that a logical vector of length higher than 1 was being forced to logical(1) appeared when I executed the original function. This showed that the code was utilizing the incorrect kind of logical operator within the loop. The line that updates the outliers matrix contained a problem since it used && rather than &. This function requires an element-wise comparison over all rows in a column, whereas the operator && just evaluates the first element of a logical vector. because Tukey's full logical vectors were being used by the function.The use of && in outlier() was wrong and resulted in warnings. I fixed the code by substituting &, which applies the logical operation element by element, for &&. This modification resulted in an error-free logical vector of length 10 being returned by the repaired function. To ensure that the input x is both a matrix and a number, I additionally included defensive checks at the top of the function. This assignment demonstrated how defensive programming can stop abuse and how minor logical operator errors can disrupt vectorized programs in R.


## Module 12 Assignment – R Markdown Primer

Blog Post:https://rayhankhanlis4370.blogspot.com/2026/04/assignment-12-introduction-to-r-markdown.html

This assignment demonstrates how to use R Markdown to combine text, code, and output into a single document.

Files:
- module12_rmarkdown.Rmd
- module12_rmarkdown.html

Explanation:

In this assignment, I created an R Markdown document that includes formatted text, LaTeX math, and executable R code. I used the mtcars dataset to generate summary statistics and a histogram. This assignment helped me understand how R Markdown supports reproducible analysis by integrating code and explanation in a single file.
