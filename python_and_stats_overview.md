# Python & Stats Overview
## Python

### Data Structures
  * list 
  * dictionary 
  * set
  * tuple

Python 3 Data Structures
https://docs.python.org/3/tutorial/datastructures.html

**Python Math Module
https://docs.python.org/3/library/math.html**

### Built-in Functions

Python 3 Built-in Functions
https://docs.python.org/3/library/functions.html.

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


## Probability/Statistics

1. measures of central tendency
  * mean
    * μ - **population** mean
    * "x-bar" - **sample** mean
    * "x-bar" _capitalized_ - **sample** mean, _where X is a random variable_
    * population vs. sample
      * population - **all** of the possible data points or observations from a set of data
      * sample - does **not** represent every possible observation
   
    * calculating with python:
      ```python
      # 1: Create simple function
      def mean(lst):
          return sum(lst) / len(lst)
      # 2: OR use numpy function 
      import numpy as np
      np.mean(lst)
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
