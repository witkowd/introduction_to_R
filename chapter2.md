--- 
courseTitle       : Introduction to R
chapterTitle      : Vectors
chapterTitleMeta  : Chapter 2
description       : We take you on a trip to Vegas, where you'll learn how to analyze your gambling results using vectors in R! After completing this chapter, you'll be able to create vectors in R, name them, select elements from them and compare different vectors. 
framework : datamind
mode: selfcontained
--- 

## Create a vector

Feeling lucky? 

You better, because this chapter takes you on a trip to the City of Sins, also known as "Statisticians Paradise" ;-).

Thanks to R and your new data-analytical skills, you will learn how to uplift your performance at the tables, and fire off your career as a professional gambler. This chapter will show you how to easily keep track of your betting progress and how to do some simple analysis on past actions. Next Stop, Vegas Baby...VEGAS!!!!

*** =instructions

1. Still remember what you learned in the first chapter? Assign to the variable `Vegas` the value `"Here we go!"`.

*** =hint
Type: `Vegas <- "Here we go!"`. Note that R is case sensitive. 

*** =sample_code




*** =solution


```r
Vegas <- "Here we go!"
```


*** =sct


```r
DM.result <- closed_test("Vegas", "c(\"Here we go!\")")
```


*** =pre_exercise_code



---

## Create a vector (2)

But hey, let's focus first! 

On your way from rags to riches, you will make extensive use of vectors. Vectors are one-dimension arrays that can hold numeric data, character data, or logical data. Stated otherwise, a vector is a  simple tool to store data. For example, your daily gains and losses in the casino's. 

In R, you create a vector with the combine function `c()`. Between the brackets you place the vector elements separated by a comma. For example:
- `numeric_vector <- c(1,2,3)`
- `character_vector <- c("a","b","c")`
- `boolean_vector <- c(TRUE,FALSE)`

Once you have created these vectors in R, you can use them to do calculations. 

*** =instructions 

1. Complete the code such that `boolean_vector` contains the three elements: `TRUE`, `FALSE` and `TRUE` (in that order). 

*** =hint 
Assign `c(TRUE,FALSE,TRUE)` to the variable `boolean_vector` with the `<-` operator. 

*** =sample_code


```r
numeric_vector <- c(1, 10, 49)
character_vector <- c("a", "b", "c")
boolean_vector <- 
# Print the vectors
numeric_vector
character_vector
boolean_vector
```


*** =solution


```r
numeric_vector <- c(1, 10, 49)
character_vector <- c("a", "b", "c")
boolean_vector <- c(TRUE, FALSE, TRUE)

# Print the vectors
numeric_vector
character_vector
boolean_vector
```


*** =sct

```r
DM.result <- closed_test(names = "boolean_vector", values = "c(TRUE,FALSE,TRUE)")
```


*** =pre_exercise_code




---

## Create a vector (3)

After one week in Las Vegas, and still zero Ferrari's in your garage, you decide it is time to start using your data analytical superpowers. 

Before doing a first analysis, you decide to first collect the winnings and losses for the last week: 
For `poker_vector`: 
- On Monday you won 140\$ 
- Tuesday you lost 50\$
- Wednesday you won 20\$ 
- Thursday you lost 120\$ 
- Friday you won 240\$

For `roulette_vector`: 
- On Monday you lost 24\$ 
- Tuesday you lost 50\$
- Wednesday you won 100\$ 
- Thursday you lost 350\$
- Friday you won 10\$

You only played Poker and Roulette, since there was a delegation of paragnosts that occupied the craps tables. To be able to use this data in R, you decide to create the variables `poker_vector` and `roulette_vector`.

*** =instructions

1. Assign to the variable `roulette_vector` the winnings/losses for roulette.

*** =hint
To help you with this step, the editor already contains the code for creating `poker_vector`. Assign the correct values to `roulette_vector` based on the numbers in the assignment. Don't forget that losses are negative numbers.

*** =sample_code


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140,-50,20,-120,240)

# Roulette winnings form Monday to Friday
roulette_vector <-  
```


*** =solution


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)

# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)
```


*** =sct


```r
names <- c("poker_vector", "roulette_vector")
values <- list("c(140,-50,20,-120,240)", "c(-24,-50,100,-350,10)")
DM.result <- closed_test(names, values)
```


--- 

## Naming a vector

As a data analyst, it is important to have a clear view on the data you are using. Understanding what each element refers to is thus key. 

In the previous exercise, we created a vector with your winnings over the week. Each vector element refers to a day of the week but it is hard to tell which element belongs to which day. It would be nice if you could show that in the vector itself. 

You can give a name to the elements of a vector with the `names()` function. For example: `names(some_vector)`.

*** =instructions

1. Go ahead and assign the days of the week as names to `poker_vector` and `roulette_vector`. In case you're not sure, the days of the week are: Monday, Tuesday, Wednesday, Thursday, Friday.

*** =hint
You can use `names( poker_vector )` to set the names of the variable `poker_vector`. Make sure not to forget the parentheses and the fact that weekdays are written with a capital letter! The vector with days of the week is thus given by: `c("Monday","Tuesday","Wednesday","Thursday","Friday")`.

*** =sample_code


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)

# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)

# Add your code here

# Print the named vectors to the console
poker_vector
roulette_vector
```


*** =solution


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)

# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)

# Add your code here
names(poker_vector) <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")

# Print the named vectors
poker_vector
roulette_vector
```


*** =sct

```r
names <- c("poker_vector", "roulette_vector", "names(poker_vector)", "names(roulette_vector)")
values <- list("poker_vector", "roulette_vector", "c(\"Monday\",\"Tuesday\",\"Wednesday\",\"Thursday\",\"Friday\")", 
    "c(\"Monday\",\"Tuesday\",\"Wednesday\",\"Thursday\",\"Friday\")")
DM.result <- closed_test(names, values, check.existence = c(TRUE, TRUE, FALSE, 
    FALSE))
```


*** =pre_exercise_code




---

## Naming a vector (2)

If you want to become a good statistician, you have to become lazy! (If you are already lazy, feel proud, chances are high you are one of those exceptional, natural-born statistical talents.) 

In the previous exercises you probably experienced it is boring and frustrating to type and retype information such as the days of the week. However, when looking at it from a higher perspective, there is a more efficient way to do this: assign the days of the week vector to a **variable**! 

Just like you did with your poker and roulette returns, you can also create a variable that contains the days of the week. This way you can use and re-use it.

*** =instructions

1. Create a variable `days_vector` that contains the days Monday until Friday.
2. Use that variable `days_vector` to set the names of `poker_vector` and `roulette_vector`.

*** =hint
You can use `names( poker_vector )` to set the names of the variable `poker_vector`. Make sure not to forget the parentheses around the days of the week.

*** =sample_code


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)

# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)

# Create the variable days_vector
days_vector <- 
# Assign the names of the day to the roulette and poker_vectors
names(poker_vector)
names(roulette_vector)

# Print the named vectors to the console
poker_vector
roulette_vector
```


*** =solution


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)

# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)

# Create the variable days_vector
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")

# Assign the names of the day to the roulette and poker_vectors
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Print the named vectors
poker_vector
roulette_vector
```


*** =sct


```r
names <- c("poker_vector", "roulette_vector", "names(poker_vector)", "names(roulette_vector)")
values <- list("poker_vector", "roulette_vector", "c(\"Monday\",\"Tuesday\",\"Wednesday\",\"Thursday\",\"Friday\")", 
    "c(\"Monday\",\"Tuesday\",\"Wednesday\",\"Thursday\",\"Friday\")")
DM.result <- closed_test(names, values, check.existence = c(TRUE, TRUE, FALSE, 
    FALSE))
```


---

## Calculating total winnings

Now that you have the poker and roulette winnings nicely as a named vector, you can start doing some data analytical magic. 

You want to find out the following type of information:
- How much has been your overall profit or loss per day of the week?
- Have you lost money over the week in total?
- Are you winning/losing money on poker or on roulette?

To get the answer to this, you have to do arithmetic calculations on vectors. 

Important to know is that if you sum two vectors in R, it takes the element-wise sum. For example: `c(1,2,3)+c(4,5,6)` is equal to `c(1+4,2+5,3+6)` or `c(5,7,9)`. Let's try this first!

*** =instructions

1. Take the sum of the variables `A_vector` and `B_vector` and assign to `total_vector`.

*** =hint
Use the `+` operator to sum `A_vector` and `B_vector`. Use `<-` to assign the result to `total_vector`.

*** =sample_code


```r
A_vector <- c(1, 2, 3)
B_vector <- c(4, 5, 6)

# Take the sum of A_vector and B_vector
total_vector <- 
# Show me:
total_vector
```


*** =solution


```r
A_vector <- c(1, 2, 3)
B_vector <- c(4, 5, 6)

# Take the sum of A_vector and B_vector
total_vector <- A_vector + B_vector

# Show me:
total_vector
```


*** =sct


```r
names <- c("A_vector", "B_vector", "total_vector")
values <- list("c(1,2,3)", "c(4,5,6)", "A_vector+B_vector")
DM.result <- closed_test(names, values)
```


*** =pre_exercise_code



---

## Calculating total winnings (2)

Understand how R does arithmetic calculations with vectors? 

Then it is time to get those Ferrari's in your garage! First, you need to understand what the overall profit or loss per day of the week was. The total daily profit, is the sum of the profit/loss you realized on poker per day, and the profit/loss you realized on roulette per day. 

In R, this is just the sum of the `roulette_vector` and `poker_vector`.

*** =instructions

1. Assign to the variable `total_daily` how much you won or lost on each day in total (poker & roulette combined).

*** =hint
Just click the Submit Answer button on the right.

*** =sample_code


```r
# Poker winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday:
roulette_vector <- c(-24, -50, 100, -350, 10)

# Name poker and roulette
days <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- days
names(poker_vector) <- days

# Up to you now:
total_daily <- 
# Show me:
total_daily
```


*** =solution


```r
# Poker winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday:
roulette_vector <- c(-24, -50, 100, -350, 10)

# Name poker and roulette
days <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- days
names(poker_vector) <- days

# Up to you now:
total_daily <- poker_vector + roulette_vector

# Show me:
total_daily
```


*** =sct


```r
names <- c("poker_vector", "roulette_vector", "total_daily")
values <- c("poker_vector", "roulette_vector", "poker_vector+roulette_vector")
DM.result <- closed_test(names, values)
```


*** =pre_exercise_code



---

## Calculating total winnings (3)

Based on the previous analysis, it looks like you had a mix of good and bad days. This is not what your ego expected, and you wonder if there may be a (very very very) tiny chance you've lost money over the week in total? 

A function that helps you to answer this question is `sum()`. It calculates the sum of all elements of a vector. For example, to calculate the total amount of money you've lost/won with poker you do: `total_poker <- sum(poker_vector)`.

*** =instructions

1. Calculate the total amount of money you've won/lost with roulette and assign to the variable `total_roulette`.
2. Now you have the totals for roulette and poker, you can easily calculate `total_week` (which is the sum of all gains and losses of the week).

*** =hint
Use the `sum` function to get the total of the `roulette_vector`. `total_week` is then the sum of `roulette_vector` and `poker_vector`.

*** =sample_code


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)

# Name poker and roulette
days <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- days
names(poker_vector) <- days

total_poker <- sum(poker_vector)

# Up to you now: assign the correct values to:
total_roulette
total_week

# Show me:
total_week
```


*** =solution


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)

# Name poker and roulette
days <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- days
names(poker_vector) <- days

total_poker <- sum(poker_vector)

# Up to you now:
total_roulette <- sum(roulette_vector)
total_week <- total_roulette + total_poker

# Show me:
total_week
```


*** =sct


```r
names <- c("poker_vector", "roulette_vector", "total_poker", "total_roulette", 
    "total_week")
values <- c("poker_vector", "roulette_vector", "sum(poker_vector)", "sum(roulette_vector)", 
    "total_poker+total_roulette")
DM.result <- closed_test(names, values, check.existence = c(TRUE, TRUE, FALSE, 
    FALSE, TRUE))
```


*** =pre_exercise_code




---

## Comparing total winnings

Ooops, it seems like you're losing money :-s. Time to rethink and adapt your strategy! This will require some deeper analysis... 

After a short brainstorm in your hotel's jacuzzi, you realize a possible explanation is that your skills in roulette are not as well developed as your skills in poker. So maybe your total gains in poker are higher (or `>` ) than in roulette.

*** =instructions

1. Calculate `total_poker` and `total_roulette`.
2. Check if your total gains in poker are higher than for roulette by using a comparison. Assign the result of this comparison to the variable `answer`.
(Tip: You partly calculated the answer to this question in the previous exercise). What do you conclude, should you focus on roulette or on poker?

*** =hint
To check if 6 is larger than 5, you type `6 > 5`. This returns a variable with data type Logical (`TRUE` or `FALSE`).

*** =sample_code


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)

# Name poker and roulette
days <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- days
names(poker_vector) <- days

# Calculate total gains for poker and roulette
total_poker
total_roulette

# Check if you realized higher total gains in poker then in roulette
answer <- 
# Show me the
answer
```


*** =solution


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)

# Name poker and roulette
days <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- days
names(poker_vector) <- days

# Calculate total gains for poker and roulette
total_poker <- sum(poker_vector)
total_roulette <- sum(roulette_vector)

# Check if you realized higher total gains in poker then in roulette
answer <- total_poker > total_roulette

# Show me the
answer
```


*** =sct


```r
names <- c("poker_vector", "roulette_vector", "total_poker", "total_roulette", 
    "answer")
values <- c("poker_vector", "roulette_vector", "sum(poker_vector)", "sum(roulette_vector)", 
    "total_poker > total_roulette")
DM.result <- closed_test(names, values, check.existence = c(TRUE, TRUE, FALSE, 
    FALSE, TRUE))
```


*** =pre_exercise_code




---

## Vector selection: the good times

Your hunch seemed to be right, it appears that the poker game is more your cup of tea than roulette. 

Another possible route for investigation is your performance at the beginning of the working week versus at the end of it? You did have a couple of Margarita cocktails at the end of the week... 

To answer that question, you only want to focus on a selection of the `total_vector`. In other words, our goal is to select specific elements of the vector. To select elements of a vector (and later matrices, data frames, ...) you can use square brackets. Between the square brackets, you indicate what elements to select: `[...elements to select..]`. For example, to select the first element of the vector, you type `poker_vector[1]`. To select the second element of the vector, you type `poker_vector[2]`, etc.

*** =instructions

1. Assign to the variable `poker_wednesday` the poker results of wednesday.

*** =hint
Wednesday is the third element of `poker_vector`, and can thus be selected with `poker_vector[3]`.

*** =sample_code


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)
# Name poker and roulette
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- names(poker_vector) <- days_vector

# Define new variable based on a selection
poker_wednesday
```


*** =solution


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)
# Name poker and roulette
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- names(poker_vector) <- days_vector

# Define new variable based on a selection
poker_wednesday <- poker_vector[3]
```


*** =sct

```r
names <- c("poker_vector", "poker_wednesday")
values <- c("poker_vector", "poker_vector[3]")
DM.result <- closed_test(names, values)
```


*** =pre_exercise_code



---

## Vector selection: the good times (2)

How about analyzing your midweek results? 

To select multiple elements from a vector, you can add square brackets at the end of it. Between the square brackets, you should indicate what element should be selected. For example: suppose you want to select the first and the fifth day of the week: use the vector `c(1,5)` between the square brackets:  `poker_vector[c(1,5)]`. Thus, you select here the first and the fifth element of `poker_vector`.

*** =instructions

1. Assign to the variable `poker_midweek` the poker results of Tuesday, Wednesday and Thursday.

*** =hint
Use the vector `c(2,3,4)` between square brackets to select the correct elements of `poker_vector`.

*** =sample_code


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)
# Name poker and roulette
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- names(poker_vector) <- days_vector

# Define new variable based on a selection
poker_midweek

# Show me the
poker_midweek
```


*** =solution


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)
# Name poker and roulette
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- names(poker_vector) <- days_vector

# Define new variable based on a selection
poker_midweek <- poker_vector[c(2, 3, 4)]

# Show me the
poker_midweek
```


*** =sct


```r
names <- c("poker_vector", "poker_midweek")
values <- c("poker_vector", "poker_vector[ c(2,3,4) ]")
DM.result <- closed_test(names, values)
```


*** =pre_exercise_code



---

## Vector selection: the good times (3)

Selecting multiple elements of `poker_vector` with `c(2,3,4)` is not very convenient. Many statisticians are lazy people by nature, so they created an easier way to do this: `c(2,3,4)` can be abbreviated to`2:4`, which generates a vector with all natural numbers from 2 up to 4.

Another way to find the mid-week results is thus `poker_vector[2:4]`. Notice how the vector `2:4` is placed between the square brackets to select element 2 up to 4.

*** =instructions

1. Assign to `roulette_selection_vector` the results from Tuesday up to Friday by making use of `:`.

*** =hint
Assign to `roulette_selection_vector` a selection of `roulette_vector` by placing `2:5` between square brackets.

*** =sample_code


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)
# Name poker and roulette
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- names(poker_vector) <- days_vector

# Define new variable based on a selection
roulette_selection_vector

# Show me the
roulette_selection_vector
```


*** =solution


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)
# Name poker and roulette
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- names(poker_vector) <- days_vector

# Define new variable based on a selection
roulette_selection_vector <- roulette_vector[2:5]

# Show me the
roulette_selection_vector
```


*** =sct

```r
DM.result <- code_test("roulette_vector[2:5]")
```


---

## Vector selection: the good times (4)

Another way to tackle the previous exercise, is by using the names of the vector elements (Monday, Tuesday, ...) instead of their numeric positions. For example, `poker_vector["Monday"]` will select the first element of `poker_vector` since `"Monday"` is the name of that first element. 

Just as you did in the previous exercise with numerics, you can also use the element names to select multiple elements, for example: `poker_vector[c("Monday","Tuesday")]`. 

*** =instructions

1. Calculate your average poker gains during the first three days of the week by selecting these elements with the help of the names. Assign this value to `average_midweek_gain`. To get the average of a vector, you can use `mean(vector_name)`.

*** =hint
To get the mean of the vector poker, you can use `mean(poker_vector)`. Now, you don't need the mean of all poker elements, but only of the first three days.

*** =sample_code


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)
# Name poker_vector and roulette_vector
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- names(poker_vector) <- days_vector

average_midweek_gain <- 
# Show me the
average_midweek_gain
```


*** =solution


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)
# Name poker and roulette
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- names(poker_vector) <- days_vector

average_midweek_gain <- mean(poker_vector[c("Monday", "Tuesday", "Wednesday")])

# Show me the
average_midweek_gain
```


*** =sct


```r
names <- c("poker_vector", "average_midweek_gain")
values <- c("poker_vector", "mean( poker_vector[c(\"Monday\",\"Tuesday\",\"Wednesday\")] )")
DM.result <- closed_test(names, values)
```


*** =pre_exercise_code




---

## Selection by comparison - Step 1

By making use of comparison operators, we can approach the previous question in a more pro-active way. 

The (logical) comparison operators known to R are:
- `<` for less than
- `>` for greater than
- `>=` for greater than or equal to
- `==` for equal to each other
- `!=` not equal to each other

As seen in the previous chapter, stating `6 > 5` returns `TRUE`. The nice thing about R is that you can use these comparison operators also on vectors. For example, the statement `c(4,5,6) > 5` returns: `FALSE FALSE TRUE`. In other words, you test for every element of the vector if the condition stated by the comparison operator is `TRUE` or `FALSE`. Don't take our word for it, try it in the console ;-).

*** =instructions

1. Check if your poker winnings are positive on the different days of the week (i.e. > 0), and assign this to `selection_vector`.

*** =hint
To check for which days your poker gains are positive, R should check for each element of `poker_vector` whether it is larger than zero. `some_vector > 0` is the way to tell R what you're after.

*** =sample_code


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)
# Name poker and roulette
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- names(poker_vector) <- days_vector

# What days of the week did you make money on poker
selection_vector <- 
# Show me
selection_vector
```


*** =solution


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)
# Name poker and roulette
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- names(poker_vector) <- days_vector

# What days of the week did you make money on poker
selection_vector <- poker_vector > 0

# Show me
selection_vector
```


*** =sct


```r
names <- c("poker_vector", "selection_vector")
values <- c("poker_vector", "poker_vector > 0")
DM.result <- closed_test(names, values)
```


*** =pre_exercise_code




---

## Selection by comparison - Step 2

Working with comparisons will make your data analytical life easier. Instead of selecting a subset of days to investigate yourself (like before), you can simply ask R to return only those days where you realized a positive return for poker. 

In the previous exercises you used: `selection_vector <- poker_vector > 0` to find the days on which you had a positive poker return. Now, you would like to know not only the days on which you won, but also how much you won on those days. 

You can select the desired elements, by putting `selection_vector` between square brackets when selecting from `poker_vector`. This works, because by default R only selects those elements where `selection_vector` is `TRUE`. For `selection_vector` this means where `poker_vector > 0`.

*** =instructions

1. Assign to variable `poker_winning_days`, the amounts you won on the profitable days.

*** =hint
Use `selection_vector` to select the desired elements from `poker_vector`, and assign the result to `poker_winning_days`.

*** =sample_code


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)
# Name poker and roulette
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- names(poker_vector) <- days_vector

# What days of the week did you make money on poker
selection_vector <- poker_vector > 0
# Select from poker_vector these days
poker_winning_days <- 
# Show me
poker_winning_days
```


*** =solution


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)
# Name poker and roulette
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- names(poker_vector) <- days_vector

# What days of the week did you make money on poker
selection_vector <- poker_vector > 0
# Select from poker_vector these days
poker_winning_days <- poker_vector[selection_vector]

# Show me
poker_winning_days
```


*** =sct


```r
names <- c("poker_vector", "poker_winning_days")
values <- c("poker_vector", "poker_vector[ selection_vector ]")
DM.result <- closed_test(names, values)
```


*** =pre_exercise_code





---

## Advanced selection

Just like you did for poker, you also want those days where you realized a positive return for roulette.

*** =instructions

1. Assign to variable `roulette_winning_days` the amount you made on the days you ended positively for roulette.

*** =hint
Have a look at the previous exercise, and do the similar analysis but now for `roulette_vector`.

*** =sample_code


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)
# Name poker and roulette
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- names(poker_vector) <- days_vector

# What days of the week did you make money on roulette

# Select from roulette_vector these days

# Show me
roulette_winning_days
```


*** =solution


```r
# Poker winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
# Roulette winnings form Monday to Friday
roulette_vector <- c(-24, -50, 100, -350, 10)
# Name poker and roulette
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(roulette_vector) <- names(poker_vector) <- days_vector

# What days of the week did you make money on roulette
selection_vector <- roulette_vector > 0
# Select from roulette_vector these days
roulette_winning_days <- roulette_vector[selection_vector]

# Show me
roulette_winning_days
```


*** =sct


```r
names <- c("roulette_winning_days")
values <- c("roulette_vector[ roulette_vector > 0 ]")
DM.result <- closed_test(names, values)
```
