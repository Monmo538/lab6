# lab6
<!-- badges: start -->
[![R-CMD-check](https://github.com/Monmo538/lab6/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/Monmo538/lab6/actions/workflows/R-CMD-check.yaml)
<!-- badges: end -->

### How the Functions work

This package includes three functions to solve the knapsack problem. All the functions have 2 inputs: 1. "x" (A data frame with 2 columns which include w (weight)and v (value)) and "W" (the total capacity of the knapsack).
All the functions return a list including the maximum value (A list which includes the total value of all the items and all the elements that are in the knapsack).

#### Brute Force Algorithm
This first function solves the knapsack problem by evaluating every possible combination of elements in the knapsack and calculating their weight. 

```{r}
starttime <- Sys.time()
brute_force_knapsack(x = knapsack_objects[1:8,], W = 3500)
endtime <- Sys.time()
print(endtime-starttime)
```

#### Dynamic Programming
The second function solves the problem by iterating over all possible values of w. 

```{r}
starttime <- Sys.time()
dynamic_programming_knapsack (x = knapsack_objects[1:8,], W = 3500)
endtime <- Sys.time()
print(endtime-starttime)
```


#### Greedy Algorithm
The third function does not always find the optimal solution to the problem but reduces the computational complexity considerably.

```{r}
starttime <- Sys.time()
greedy_knapsack (x = knapsack_objects[1:800,], W = 3500, fast = TRUE)
endtime <- Sys.time()
print(endtime-starttime)
```

By running the C++ Code for Greedy algorithm, the run time will be optimized. As you see in the code, if the fast is FALSE, the C++ code will run, and if it is TRUE, the R code will run.

```{r}
starttime <- Sys.time()
greedy_knapsack (x = knapsack_objects[1:800,], W = 3500, fast = FALSE)
endtime <- Sys.time()
print(endtime-starttime)
```
