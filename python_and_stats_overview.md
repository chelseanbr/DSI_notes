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

**Python 3 Data Structures**
https://docs.python.org/3/tutorial/datastructures.html

  * list 
  * dictionary 
  * set
  * tuple

### Built-in Functions

**Python 3 Built-in Functions**
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
    * "x-bar" - **sample** mean
    * "x-bar" _capitalized_ - **sample** mean, _where X is a random variable_
    * population vs. sample
      * population - **all** of the possible data points or observations from a set of data
      * sample - does **not** represent every possible observation
   
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
  * boxplots
  * distribution visualizations
  
## Other Notes
  * Bernoulli trials
  * sigmoid function

[Top of Page](#Python--Stats-Overview)
[[Back to Main Menu]](/README.md)
