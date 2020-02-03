# Python & Stats Overview
1. [Python](#Python)
  * [Data Structures](#Data-Structures)
  * [Built-in Functions](#Built-in-Functions)
  * [Python Math Module](#Python-Math-Module)
  * [Other Useful Python Knowledge](#Other-Useful-Python-Knowledge)
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

1. abs(x)
  * return abs val of int or floating pt num x; if complex, returns magnitude 
2. _bool()_
  * class. Boolean val True or False
3. _chr()_
  * return string representing char, for example chr(97) returns 'a'
    * valid for i = 0 through 1,114,111 (0x10FFFF in base 16)
4. dict()
  * create a new dictionary
5. **enumerate**(iterable, start=0)
  * return enumerate obj given an iterable, for example, given a list, a list of tuples with counts will be returned
  ```python
  >>> seasons = ['Spring', 'Summer', 'Fall', 'Winter']
  >>> list(enumerate(seasons))
  [(0, 'Spring'), (1, 'Summer'), (2, 'Fall'), (3, 'Winter')]
  >>> list(enumerate(seasons, start=1))
  [(1, 'Spring'), (2, 'Summer'), (3, 'Fall'), (4, 'Winter')]
  ```
6. _float()_
  * class. 
7. _input()_
  * 
8. _int()_
  *
9. len()
10. list() 
11. max()
12. min()
13. ord()
14. print() 
15. **range(stop / start, stop[, step])**
```python
>>> list(range(10))
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
>>> list(range(0, -10, -1))
[0, -1, -2, -3, -4, -5, -6, -7, -8, -9]
 ```
16. **round(number[, ndigits])**
  * return num rounded to ndigits precision, unless if no ndigits, returns closest int
17. **set()**
  * returns a new set where there are no duplicate items
18. **sorted(iterable, *, key=None, reverse=False)
  * returns the iterable sorted, alternative to list.sort(), which returns None and is slightly more efficient
  ```python
  >>> sorted([5, 2, 3, 1, 4])
  [1, 2, 3, 4, 5]
  ```
19. str()
20. sum()
21. tuple()
22. type()

### Python Math Module
https://docs.python.org/3/library/math.html

### Other Useful Python Knowledge
* splitting a string (like a word) into a list of chars
  1. using list comprehension
    ```python
    def split(word): 
        return [char for char in word]  
    ```
  2. typecasting into list
    ```python
    def split(word): 
        return list(word)
    ```
* **be careful with floor division vs typecasting with int(), esp. for neg numbers with mod operations
* string formatting
  ```python
  # Option 1: Format method
  'Inserting {} into this string'.format(variable_to_insert)
  
  x = 1
  y = 3
  new_string = 'The result of {} divided by {} is {:.3f}'.format(x, y, x/y) # {:.3f} rounds float to 3rd decimal
  print(new_string)
  
  # Option 2: f strings
  x = 1
  y = 3
  new_string = f'The result of {x} divided by {y} is {x/y:.2f}'
  print(new_string)
  ```

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
    * **right-skewed**: mean > mode, _longer tail to the right_ (or "positive skewed")
    * **left-skewed**: mean < mode, _longer tail to the left_ (or "negative skewed")
  * boxplots
    * box represents IQR: interquartile range = Q_3 - Q_1
      * center of distribution, middle 50% of values
    * outliers: values below Q1 – 1.5×IQR or above Q3 + 1.5×IQR
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
10. logistic regression
  * false-positive
  * true-positive
  * false-negative
  * false-positive

## Other Notes
  * Bernoulli trials
  * sigmoid function

[Top of Page](#Python--Stats-Overview)

[[Back to Main Menu]](/README.md)
