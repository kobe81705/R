# R
R language
#switch
x <- 1
switch(x, 5, sum(1:10), rnorm(5))

y <-1
switch(y, juice="Apple", meat="Pork")

y<- "juice"
switch(y, juice="Apple", meat="Pork")

#for
x <- 0
for (i in 1:5) x <- x + i
x

x <- 0
y <- 0
for(i in 1:5) {x <- x+ i; y <- i^2}
x
y

#while
sum <- 0
i <- 1
while (i <=10) {sum <- sum +i; i <- i + 1}
sum

#repeat
sum <- 0
i <- 1
repeat{
  sum <- sum + i
  i <- i +1
  if(i > 10)break
}
sum

# %% 餘數 %/% 商
sum <- 0
for(i in 1:50){
  if(i %% 2 ==0)next
  sum <- sum +i
}
sum

#自訂函數

myfun <- function(x) {y <- x +2; return(y)}
myfun(1)
myfun(100)

# <<- 改變函數外面的值
x <- 1
myfun <- function(x) {x <- 2; print(x)}
myfun(x)
x
x<-1
myfun <- function(x) {x <<- 2; print(x)}
myfun(x)
x

#factorial 階層
factorial <- function(x=1){
  y <- 1
  for(i in 1:x) y <- y *i
  return(y)
}
factorial(5)
factorial(10)


#apply
x <- array(1:24, dim =c(4,6))
x
apply(x, 1, sum)
apply(x, 2, sum)


id <- c(1,2,3,4)
age <- c(20,30,40,50)
sex <- c("male",'male','female','female')
pay <- c(3000,4000,5000,6000)

x_dataframe <- data.frame(id,age,sex,pay)

x_dataframe[3,2]
x_dataframe[4,]
x_dataframe[2]
x_dataframe$age
edit(x_dataframe)

#list
id <- c(1,2,3)
sex <- c("male","male","male")
pay <- c(30000,40000,50000)
y_dataframe <- data.frame(id,sex,pay)
gender <- factor(c("男","男","女"))
Paul.Family <- list(name="paul",wife="Iris",
no.kids=3, kids.age=c(25,27,30), gender,
y_dataframe)
Paul.Family

Paul.Family$kids.age
Paul.Family[4]
Paul.Family[[4]]

Paul.Family$kids.age[2]
Paul.Family[[4]][2]
#錯誤Paul.Family[4][2]

#ch2 資料的讀取與寫入
getwd()
setwd("c:/")
getwd()

x <- read.table("x.csv", sep=",",geader=TRUE)
x
