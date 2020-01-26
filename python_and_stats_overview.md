# Python & Stats Overview
1. [Python](#Python)
  * [Data Structures](#Data-Structures)
  * [Built-in Functions](#Built-in-Functions)
  * [Python Math Module](#Python-Math-Module)
2. [Probability/Statistics](#ProbabilityStatistics)
3. [Other Notes](#Other-Notes)

[[Back to Main Menu]](/README.md)

## Python

### Data Structures

https://docs.python.org/3/tutorial/datastructures.html

  1. list 
  2. dictionary 
  3. set
  4. tuple

### Built-in Functions

https://docs.python.org/3/library/functions.html

1. abs()
2. bool()
3. chr()
4. dict()
5. enumerate()
6. float()
7. input()
8. int()
9. len()
10. list() 
11. max()
12. min()
13. ord()
14. print() 
15. range()
16. round()
17. set()
18. sorted()
19. str()
20. sum()
21. tuple()
22. type()

### Python Math Module
https://docs.python.org/3/library/math.html

## Probability/Statistics

1. measures of central tendency
  * **mean** - average
    * μ - **population** mean
    * x¯ ("x-bar") - **sample** mean
    * X¯ ("x-bar" _capitalized)_ - **sample** mean, _where X is a random variable_
    * population vs. sample
      * population - **all** of the possible data points or observations from a set of data
      * sample - does **not** represent every possible observation
    * advantages: **preferable in large datasets with few (or symmetric) outliers**
    * calculating with python:
      ```python
      # Option 1: Create simple function
      def mean(lst):
          return sum(lst) / len(lst)
      # Option 2: Use numpy function 
      import numpy as np
      np.mean(lst)
      ```
  * **median** - middle value
    * notations: **med(A)** or **lower-case x _with tilde over top_**
    * advantages: **more resistant to _extreme/non-symmetric_ outliers** _than mean_
    * calculating with python:
      ```python
      # Option 1: Simple function
      def median(lst):
          import numpy as np
          length = len(lst)
          lst.sort()
          # Odd number of items in list
          if length % 2 != 0:
              idx = (length / 2 + 0.5) - 1
              return lst[int(idx)]
          # Even number of items in list
          else:
              idx1 = int(length / 2 - 1)
              idx2 = idx1 + 1
              return np.mean([lst[idx1], lst[idx2]])
      # Option 2: Numpy function
      import numpy as np
      np.median(lst)
      ```    
  * **mode** - item with greatest frequency
    * notations: **mode(A)** or **Mo**
    * advantages: **preferred with _categorical data_**
    * calculating with python:
      ```python
      # Option 1: scipy function
      from scipy import stats
      # Will return the mode, and its frequency, each in a numpy array
      stats.mode(lst)
      ```
2. error metrics
3. least squares regression
4. combinations & permutations
  * combinations
  * permutations
5. conditional probability
  * law of total probability 
  * Bayes theorem
6. distributions
  * Binomial
  * Poisson
7. plots
  * histograms
    * each bin is left inclusive, and right exclusive
    * common function to calculate # of bins: k = sqrt(n), where n represents # of samples
    * **right-skewed**: mean > mode, longer tail to the right
    * **left-skewed**: mean < mode, longer tail to the left
  * boxplots
  * distribution visualizations
8. five number summary
  * The minumum
  * Q_1 - the first quartile
  * The median
  * Q_3 - the third quartile
  * The maximum
  * notation: _(min, Q_1, median, Q_3, max)_
  * steps to build 5 number summary:
    * sort data in ascending order
    * calculate min, max, median
    * Q_1 = median of lower subset (exclusively below median)
    * Q_3 = median of upper subset (exclusively above median)
    * calculating with python:
      ```python
      # Option 1: Use functions from scipy, numpy (percentile)
      from numpy import percentile
      def five_number_summary(lst):
          # Calculate quartiles (Q1, Median, Q3)
          q1, median_, q3 = percentile(lst, [25, 50, 75])
          # Calculate min/max
          min_, max_ = data.min(), data.max()
          return min_, q1, median_, q3, max_
9. variance and standard deviation 
  * variance
    * population: **σ^2** = 1/n * n∑i=1 (x_i−μ)^2
    * sample: **s^2** = 1/n−1 * n∑i=1 (x_i−x¯)^2
      * different from population variance due to Bessel's correction (https://en.wikipedia.org/wiki/Bessel%27s_correction)
      * bias partially corrected with factor n / n-1
  * standard deviation = sqaure root of variance
    * calculating with python:
      ```python
      import numpy as np
      # Will return the variance of the numeric dataset w/o Bessel's correction
      np.var(lst)
      # Will return the variance of the numeric dataset w/ Bessel's correction
      np.var(lst, ddof=1)
      # Will return the standard deviation of the dataset w/o Bessel's correction
      np.std(lst)
      # Will return the standard deviation of the dataset w/ Bessel's correction
      np.std(lst, ddof=1)
      ```
      * ddof: delta degrees of freedom

## Other Notes
  * Bernoulli trials
  * sigmoid function

[Top of Page](#Python--Stats-Overview)

[[Back to Main Menu]](/README.md)
