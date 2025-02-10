# Unexpected NA Result in Mean Calculation Function

This repository demonstrates a subtle bug in an R function designed to calculate the mean of a numeric vector. The function attempts to handle empty vectors and NA values but produces an unexpected result when NA values are present.

## Bug Description

The `calculate_mean` function correctly handles empty vectors by returning `NA`. However, when the input vector contains `NA` values, the function unexpectedly returns `NA` even though the `na.rm = TRUE` argument is used in the `sum()` function. This behavior is incorrect; the function should calculate the mean of the non-`NA` values. 

## Bug Solution

The solution involves correctly handling `NA` values. Instead of relying on `sum()` with `na.rm = TRUE` alone, the code should first remove the `NA` values before computing the mean.

## How to Reproduce

1. Clone this repository.
2. Open `bug.R` in RStudio or your preferred R environment.
3. Run the script. Observe the unexpected output.
4. Examine the corrected code in `bugSolution.R` to understand the fix.