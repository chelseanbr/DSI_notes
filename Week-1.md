* [Mon-3.16](/Mon-3.16)
* [Tue-3.17](/Tue-3.17)

# Mon-3.16
## Unix

* pwd : print working directory
* ls : list all files/folders
  * ls -l : list with more details, permissions
  * ls -a : list hidden files
* mkdir : make new folder
* cd : change directory
  * cd .. : 1 dir upper
  * cd ../.. : 2 dirs upper
  * cd - : go back to previous dir
* *(TIP: Use tab to autocomplete)*
* nano : text editor
* cat : print out what's in a file
* less : show what's in a file, but page-by-page
* head : show top of file 
  * by deafult gives first 10 lines
  * add "-20" to show 20 lines instead
* tail : show bottom of file
* vim : test editor
  * i to insert
  * esc to enter command mode 
  * :wq to write out file & quit in cmd mode
* **grep** 'search-string' filename
  * --color to color search str
  * -w to get exact match
  * -E for regex
    * regex : can use '.*' wildcard
* sed 
  * sed 's/dog/cat/' filename : substitute everything 
  * -n : print only line where subsitutions made
  * > write to new file
  * >> 
* sort
  * sort contents of file
* echo >> : add lines if you don't want to go inside file
* uniq
* man : print instructions for all commands
  
### Permissions String
[drwx][rwx][rwx]
[user][grp][others]
* chmod 
 * 755 : user rwx, grp & others r-x
 * 400 : root r--, grp & others no permission
 * -R to change for all files in folder

* ps : processes
* jobs :
* top : all processes running on machine
* killall : kill certain processes

## Git
git clone

### Partner A
git checkout -b *(branch)*
git status
git add
git commit -m "*(message)*"
git push -u origin *(branch)*
* -u : upstream for the 1st time you push to new branch 

### Partner B
git remote add *(partner's name)* *(github clone link)*
git fetch *(partner's name)*
git status
git checkout --track file
git pull file
git push 

### Partner A
git merge -m "*(message)*"

## **TODO**
Register for AWS credit
Send Account ID + email to Hamid for AWS

# Tue-3.17
## Warmup
```
Given an unsorted list of some elements(may or may not be integers), Find the frequency of each distinct element in the list using a dictionary.
Example:
Input : [1, 1, 1, 5, 5, 3, 1, 3, 3, 1,
                  4, 4, 4, 2, 2, 2, 2]
Output : 1 : 5
         2 : 4
         3 : 3
         4 : 3
         5 : 2
Explanation : Here 1 occurs 5 times, 2 
              occurs 4 times and so on...
```
```python
# My Answer
lst = [1, 1, 1, 5, 5, 3, 1, 3, 3, 1,
                  4, 4, 4, 2, 2, 2, 2]
result = dict()
for num in sorted(lst):
  if num not in list(result):
    result[num] = 0
  result[num] += 1
for num in list(result):
  print(f'{num} : {result[num]}')
```

## Lecture: Numpy
### Arrays
* **Different from lists: must have fixed size with same datatype throughout**
* .copy() array to avoid modifying original
* Creating numpy arrays
 * np.zeros, np.ones
 * np.full
 * np.linspace
  * Good for plotting
 * np.arange
  * Like range()
#### Arrays from Distributions
* np.random.uniform
* np.random.normal
#### Broadcasting
* Apply arithmetic operations element by element on array(s, with matching 1 dimension)
* @ for matrix multiplication
* Can do with comparison operators (return boolean array)
* np.mean() same as mean(), but expects np array
#### Array Indexing
##### Fancy Indexing
* can index array with another array or list
##### Boolean Indexing
* np array x, x\[\[bool_list]]

