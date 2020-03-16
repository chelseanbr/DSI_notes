# Mon, 3/16
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
  

  

